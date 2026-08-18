# 平台适配器

**简体中文** | [English](./README.en.md)

核心协议保持平台无关；适配器只负责把它放进特定宿主支持的入口。

## 通用复制

- 普通问答、研究和可逆任务：复制 [`PROMPT.lite.zh-CN.md`](../PROMPT.lite.zh-CN.md)。
- 外部、不可逆、敏感、多主体或正式验收任务：复制 [`PROMPT.governed.zh-CN.md`](../PROMPT.governed.zh-CN.md)。

## Codex `AGENTS.md`

将 [`codex/AGENTS.md`](./codex/AGENTS.md) 复制到目标仓库根目录，再补充该项目真实的构建、测试和禁止事项。

`AGENTS.md` 是 Codex 的项目指令入口，不应被描述为所有 Agent 都会自动读取的通用标准。官方说明：[Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

## Codex / ChatGPT Skill

将完整的 [`codex-skill/universal-agent-workflow/`](./codex-skill/universal-agent-workflow/) 文件夹复制到目标仓库的：

```text
.agents/skills/universal-agent-workflow/
```

Skill 适合需要按任务自动加载工作流、又不想让完整 GOVERNED 提示词一直占用上下文的用户。官方说明：[Build skills](https://learn.chatgpt.com/docs/build-skills)。

## 能力限制

适配器不会：

- 提升 Agent 的工具权限；
- 让同一 Agent 的自审变成独立审查；
- 让不支持项目指令或 Skill 的宿主自动发现这些文件；
- 替代真实的权限控制、CI、备份、审计或人工验收。
