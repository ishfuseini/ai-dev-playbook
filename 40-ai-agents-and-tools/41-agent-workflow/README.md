# 41 — Agent Workflow

> 🚧 **Work in Progress** — This folder is actively being built out.

Prompts and guides for structuring multi-agent AI workflows in software development.

## Contents

| File | Status | Description |
|------|--------|-------------|
| `41.01-multi-agent-setup.md` | ✅ Ready | Role definitions, model tiers, handoff protocol, and orchestration flow |

## Planned

- `41.02-agent-prompts.md` — Copy-paste system prompts for each role (Architect, Developer, Reviewer, Documenter)
- `41.03-human-in-the-loop.md` — Guidelines for where and how humans should checkpoint agentic runs
- `41.04-agent-memory.md` — Patterns for passing context between agents across turns and sessions

## Related

- `44-claude/44.02-agents/` — Concrete Claude sub-agent definitions
- `30-project-setup/31-repo/31.01-documentation` — Memory system and task log format used by agents
- `10-prompt-engineering/10-Dev-Spec/13-spec-taskcreation.md` — Task file format agents consume