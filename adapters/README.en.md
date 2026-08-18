# Platform Adapters

**English** | [简体中文](./README.md)

The core protocol remains platform-neutral. Adapters only place it in a host-supported entry point.

## Generic Copy-and-Paste

- Questions, research, and reversible tasks: copy [`PROMPT.lite.en.md`](../PROMPT.lite.en.md).
- External, irreversible, sensitive, multi-actor, or formal acceptance work: copy [`PROMPT.governed.en.md`](../PROMPT.governed.en.md).

## Codex `AGENTS.md`

Copy [`codex/AGENTS.md`](./codex/AGENTS.md) to the target repository root, then add the project's real build, test, and prohibited-action rules.

`AGENTS.md` is a Codex project-instruction entry point. Do not present automatic discovery as a guarantee for every agent. Official guidance: [Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

## Codex / ChatGPT Skill

Copy the complete [`codex-skill/universal-agent-workflow/`](./codex-skill/universal-agent-workflow/) directory into the target repository at:

```text
.agents/skills/universal-agent-workflow/
```

The Skill is useful when users want task-based loading without keeping the entire GOVERNED prompt in every context. Official guidance: [Build skills](https://learn.chatgpt.com/docs/build-skills).

## Capability Limits

Adapters do not:

- grant tool permissions;
- make an implementer's self-review independent;
- make unsupported hosts discover project instructions or skills;
- replace access controls, CI, backups, audit systems, or human acceptance.
