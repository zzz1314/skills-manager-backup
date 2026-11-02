# ToB Sales Coach

通用 ToB 复杂销售教练和客户推进工具。适用于客户背调、销售阶段判断、电话前准备、需求挖掘、会议复盘、报价前判断、proposal 跟进、谈判推进、价格异议处理、停滞客户唤醒和丢单复盘。

这个 skill 默认使用中文，输出风格直接、专业、可执行，目标是帮销售人员把客户推进到明确的下一步，而不是生成泛泛而谈的销售建议。

## 适用场景

- 分析 B2B 线索，判断客户阶段、等级、成交概率和下一步动作
- 根据客户资料生成电话前作战卡
- 对明确名称的大客户做公开信息背调，并区分事实和销售推断
- 复盘销售电话、会议纪要或聊天记录
- 判断是否适合提交 proposal 或报价
- 处理价格异议、采购流程、法务流程、拖延和沉默
- 训练销售追问能力，尤其是 `talk-a-little-bit-more` 式深挖
- 为首次使用者配置行业、产品、ICP、价格模型和交付边界

## 安装

把仓库放到 Codex skills 目录下：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/seven-xww/tob-sales-coach.git ~/.codex/skills/tob-sales-coach
```

如果已经克隆过，更新到最新版：

```bash
cd ~/.codex/skills/tob-sales-coach
git pull
```

## 使用方式

在 Codex 中直接调用：

```text
$tob-sales-coach
```

也可以把 skill 名称和销售材料放在同一条消息里，例如：

```text
用 $tob-sales-coach 分析这个客户：客户是某制造业集团，线索来自展会，采购负责人说今年要评估供应链系统，但还没有预算范围。
```

## 示例提示词

客户分析：

```text
用 $tob-sales-coach 分析这个线索，判断阶段、客户等级、成交概率和下一步动作：
客户来自朋友转介绍，是一家 800 人的软件公司，正在比较 3 家供应商，老板关注交付周期，IT 负责人关注安全和集成。
```

电话前准备：

```text
用 $tob-sales-coach 给我做电话前作战卡：
客户是某连锁零售品牌，计划升级会员系统，当前使用自研工具，联系人是市场部负责人，明天下午首次沟通。
```

会议复盘：

```text
用 $tob-sales-coach 复盘这次会议，并指出我下次只改一个动作：
客户说现在不是不想做，而是内部还没有统一优先级。财务负责人问过预算，但业务负责人更关心上线后门店是否愿意用。
```

报价和谈判：

```text
用 $tob-sales-coach 判断现在是否适合报价，并准备价格异议处理：
客户已经看过 demo，认可方案方向，但要求先给最低价，还说另一家供应商便宜 30%。
```

首次配置行业上下文：

```text
用 $tob-sales-coach 帮我配置行业上下文。我卖的是面向中大型企业的客户数据平台，客单价 20-80 万，主要客户是零售、消费品和连锁品牌。
```

## 输出特点

- 先判断销售阶段，再给推进建议
- 使用固定销售阶段，避免跳步推进
- 默认输出简洁的客户推进卡
- 对不适合报价、proposal、专家会或折扣的客户，会直接说明缺什么
- 电话和会议复盘会先提取客户事实，再评价销售表现
- 大客户公开背调必须列来源，并区分已验证事实和销售推断
- 不承诺收入、ROI、增长、合规审批或确定结果

## 目录结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── industry-context-template.md
    ├── negotiation-playbook.md
    ├── research-playbook.md
    ├── review-playbook.md
    └── sales-playbook.md
```

文件说明：

- `SKILL.md`：skill 入口，定义触发场景、核心流程和边界
- `agents/openai.yaml`：Codex 展示名称、简介和默认提示词
- `references/sales-playbook.md`：客户分析、推进卡、线索分层和阶段规则
- `references/research-playbook.md`：大客户公开背调规则和输出格式
- `references/negotiation-playbook.md`：proposal、报价、谈判、采购和法务处理
- `references/review-playbook.md`：会议复盘、销售表现评估和追问训练
- `references/industry-context-template.md`：首次行业配置和持续深挖模板

## 销售阶段

本 skill 使用以下阶段：

```text
新线索 / 已首触达 / 已完成初步诊断 / 已确认合格线索 / 已约方案会或专家会 / 已完成方案沟通 / 已报价或提交 proposal / 谈判中 / 采购法务合同流程中 / 已成交 / 已丢单或待唤醒
```

## 注意事项

- 用户提供的公司资料默认视为内部资料，除非明确说明可以对外发送
- 公开背调只使用公开来源，不编造私人信息
- MBTI 等标签只能作为临时沟通假设，不能当作事实
- 合作边界不清楚前，不建议交付完整策略、实施计划、源文件、架构细节或深度定制 proposal
