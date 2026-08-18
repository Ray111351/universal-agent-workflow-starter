# Changelog

All notable behavior and packaging changes are documented here.

## [1.1.0-rc.1] — 2026-08-18

### Added

- platform-neutral CORE in Chinese and English;
- default LITE prompts for ordinary reversible work;
- GOVERNED prompts for external, irreversible, sensitive, and formal workflows;
- separate orchestration, duty, stage, complexity, and action-risk models;
- untrusted-content, prompt-injection, secret, privacy, and data-minimization rules;
- just-in-time confirmation and `STALE_APPROVAL` after material baseline drift;
- Codex `AGENTS.md` and portable Skill adapters;
- bilingual behavioral evals and multi-domain examples;
- explicit limitations and a copy-ready attribution statement.

### Changed

- approval, evidence, and execution states are now independent;
- a bare “Yes” no longer authorizes high-risk actions;
- multiple options are required only for real tradeoffs;
- simple reversible tasks use a three-line kickoff;
- acceptance is separated from review and from implementer self-checks.

### Compatibility

- V1.0 prompts remain at `PROMPT.zh-CN.md` and `PROMPT.en.md`.
- New users should start with `PROMPT.lite.*.md`.

## [1.0.0] — 2026-08-18

- initial bilingual master prompt;
- SOLO, PLANNER, EXECUTOR, REVIEWER, and ACCEPTOR roles;
- S/M/L task classification;
- kickoff, work-order, handoff, and completion templates.
