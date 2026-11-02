# 中文写作 AI 痕迹去除

一份针对中文写作的极简规则清单。把它交给 Agent，让 Agent 在写作或润色时识别并删掉常见的 AI 腔。

## 用法

### 方法一：作为 Skill 使用（推荐）

在 Codex 中调用内置的 Skill 安装器：

```text
$skill-installer 请从 https://github.com/Wechat-ggGitHub/chinese-ai-humanizer 安装这个 Skill
```

也可以手动安装到个人 Skill 目录：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/Wechat-ggGitHub/chinese-ai-humanizer.git ~/.agents/skills/chinese-ai-humanizer
```

安装后，Codex 会根据 [`SKILL.md`](./SKILL.md) 中的 `description` 自动匹配。直接提出类似请求即可：

```text
帮我去除下面这段文字的 AI 味：……
```

```text
请把下面的中文润色得自然、直接、简洁：……
```

也可以显式指定 Skill：

```text
$chinese-ai-humanizer 帮我润色下面的中文：……
```

如果安装后没有立即出现，重启 Codex。更多说明见 [Codex Skill 官方文档](https://developers.openai.com/codex/skills)。

### 方法二：加入 Agent 指令文件

复制 [`SKILL.md`](./SKILL.md) 的正文内容（不含开头的 YAML frontmatter），放入对应的指令文件：

> 写作或润色中文时，检查并去除以下 AI 痕迹，保持表达自然、直接、简洁。

- Codex：单个项目使用项目根目录下的 `AGENTS.md`，全局使用 `~/.codex/AGENTS.md`。
- Claude Code：单个项目使用项目根目录下的 `CLAUDE.md`，全局使用 `~/.claude/CLAUDE.md`。

如果已有指令文件，追加内容即可，不要覆盖原有规则。具体加载方式可查看 [Codex AGENTS.md 官方文档](https://learn.chatgpt.com/docs/agent-configuration/agents-md) 和 [Claude Code 官方文档](https://code.claude.com/docs/zh-CN/memory)。

## 设计原则

提示词也有成本。规则越短，占用的 token 越少，也越容易维护。这个项目只保留能稳定复现、能直接改写的特征，用尽可能少的文字改善中文表达。

## 效果边界

这些规则用于减少常见的中文 AI 腔。项目不提供 AI 检测功能，也不保证绕过检测工具。

## 贡献

发现新的稳定特征时，欢迎提交 Issue 或 PR，并附上原句和更自然的改法。

## 许可

作者：Awesome-GitHub（[@Wechat-ggGitHub](https://github.com/Wechat-ggGitHub)）。

项目内容使用 [Creative Commons Attribution 4.0 International](./LICENSE) 许可。复制、修改或发布时，请保留署名并链接本仓库。
