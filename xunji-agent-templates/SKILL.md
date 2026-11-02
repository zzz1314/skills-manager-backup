---
name: xunji-agent-templates
description: Use when the user asks to read, create, or update Xunji Agent workout templates.
---

# 训记 Agent 个人模版 Skill

## 用途
- 只管理用户现有个人模版系统里的「Agent 模版」专属文件夹。
- 写入后的模版会直接出现在训记，可像普通个人模版一样开始训练、排期、复制或编辑。
- 用户明确确认后，Agent 可以自定义专属文件夹的显示名称；不得改变文件夹 ID、移动、分享或删除它。
- 用户只能在训记 App 内删除这个专属文件夹；该操作会同时删除内部全部模版。获取到 `folder_deleted` 后不得自行重建，除非用户之后明确要求新建 Agent 模版。

## 硬性容量限制
- Agent 只允许使用 1 个服务端 ID 固定、显示名称可自定义的专属文件夹；不得创建、请求或模拟第二个文件夹或子文件夹。
- 这个文件夹最多保存 14 个有效模版；更新已有模版不额外占用名额。
- 每个模版最多 15 个动作。
- 每个动作最多 20 组。
- 写入前必须检查全部四项限制。超限时应询问用户删减或替换哪项；不得静默截断、另建文件夹拆分，也不得未经确认删除已有模版。
- 14 个名额已满时，可以在同一次明确确认的 mutation 中删除 1 个旧模版并新建 1 个模版。

## 鉴权
- Base URL：`https://trains.xunjiapp.cn`
- Header：`Authorization: Bearer xjtpl_91b7f961635dd1f44a2c11cedf22d1b8cbe280a54e774c54`
- 本 Skill 使用独立的个人模版 Key。不得把 Key 放进 query/body、日志或展示给第三方。
- 同步和写入成功响应统一使用 gzip level 6；常见 HTTP 客户端会自动解压。

## 实时获取（v2）
- 接口：`POST /api_agent_templates_sync_for_llm_v2`
- 发送 `{}` 即可一次获取当前全部模版，不需要游标、分页或持久化同步状态。
- 有完整本地缓存时可传 `template_versions: { "模版ID": 3 }`，只返回版本不同的内容；内容缺失的模版不要报版本。
- 每次返回最新 `folder`、`limits` 和完整 `template_versions` 清单；`templates` 只包含新增或版本不同的完整模版。
- 替换变化的缓存模版，保留同版本内容；按 `deleted_template_ids` 清理该 Agent 文件夹缓存，不得删除已移到其他文件夹的模版。
- `folder_deleted: true` 且 `folder: null` 表示文件夹不存在或已删除，清理其缓存，不得自动重建。
- 每次读取或编辑模版前获取一次；写入成功后需要最新状态时再获取。不需要保存或回放变更日志。
- App 在模版界面启用自动刷新，用户不需要维护同步游标或手动点刷新。
```http
POST https://trains.xunjiapp.cn/api_agent_templates_sync_for_llm_v2
Authorization: Bearer xjtpl_91b7f961635dd1f44a2c11cedf22d1b8cbe280a54e774c54
Accept-Encoding: gzip
Content-Type: application/json

{ "template_versions": {} }
```

## 新建或更新模版
- 接口：`POST /api_agent_templates_mutate_for_llm_v1`
- 每次写入前，先向用户展示准确的文件夹改名和/或模版名、动作、组数、递增规则变更，等待明确确认。
- 确认后发送 `confirmed: true`，并使用重试时保持不变的唯一 `mutation_id`。
- 相关修改合并成一次请求（最多 14 个 upsert + 14 个 delete），减少流量。
- 新建时发送稳定 `client_id`，服务端据此生成幂等的模版 ID。
- 更新/删除时发送同步所得的 `template_id` 与最新 `base_version`。遇到 `version conflict`，先重新同步、展示冲突，再询问用户。
- 修改唯一文件夹名称时，发送 `folder_update: { name, base_version }`，版本取自同步所得的 folder。规范化后的名称不能为空且最多 32 个字符；不改名时省略 `folder_update`。
- 文件夹名和模版名只能包含中文、英文字母、数字和普通空格；禁止 emoji、标点、符号、换行、零宽/不可见字符和双向覆盖字符。
- Agent 写入的所有可见文本都会在训记服务器本地执行内容安全检查，不会发送给第三方审核服务。
- 文件夹改名可以是一次 mutation 的唯一操作，但仍必须带 `confirmed: true` 和唯一 `mutation_id`。
- 成功后用规范化的 `applied[].data` 更新缓存并应用返回的删除项，或重新获取 v2；忽略旧 `next_cursor`；相同 `mutation_id` 的重试会返回相同结果。
- 新建优先使用公开 `movements` 结构；编辑已有模版时，可把同步返回的原生 `movement` 和 `rules` 按需修改后原样写回。
```json
{
  "confirmed": true,
  "mutation_id": "agent-request-unique-id",
  "folder_update": { "name": "我的增肌模版", "base_version": 1 },
  "upserts": [{
    "client_id": "push-a-v1",
    "name": "推 A",
    "color": "#FF8A1F",
    "movements": [{
      "name": "杠铃卧推",
      "sets": [{ "weight": 60, "reps": 8, "unit": "kg" }],
      "progression": {
        "start_reps": 8, "reps_increment": 1, "target_reps": 12,
        "weight_increment": 2.5, "reset_reps": 8
      }
    }]
  }],
  "deletes": []
}
```

## 规则与安全
- 公开结构里的动作名必须使用训记官方中文名；动作、单位、组次或递增规则不确定时先问用户。
- 双重递增：先增加次数；所有工作组达到目标次数后再增加重量并重置次数。不要编造百分比或进度分。
- 绝不修改 Agent 文件夹之外的个人模版。
- `folder_name invalid` / `folder_base_version invalid`：询问一个非空且最多 32 个字符的名称，并使用最新同步得到的文件夹版本。
- `folder_name special characters not allowed` / `name special characters not allowed`：请用户改用仅包含中文、英文字母、数字和空格的名称；不得使用相似字形或不可见字符绕过。
- `content safety rejected`：说明文本未通过训记本地内容安全规则，请用户提供安全替代文案；不得混淆文字后自动重试。
- `template limit exceeded (max 14)`：重新同步并展示当前 14 个模版，询问用户替换或删除哪一个。
- `movements invalid` / `sets invalid`：把请求调整到每个模版最多 15 个动作、每个动作最多 20 组；不得静默截断。
- `user confirmation required`：先展示摘要，等用户确认，再带 `confirmed: true` 重试。
- `too frequent`：按提示等待，不要循环请求。
- `apikey missing` / `apikey invalid`：让用户回 App 重新申请，再复制并发送最新 Skill。
