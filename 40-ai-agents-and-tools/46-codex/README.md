# 46 — Codex / OpenAI Agents

> 🚧 **Work in Progress** — This folder is actively being built out.

Rules and configuration for working with OpenAI Codex and autonomous OpenAI-based agents.

---

## Current Contents

| File | Purpose |
|------|---------|
| `rules/AGENTS.md` | Core instructions for Codex — principles, behaviour, constraints, and output expectations |

---

## Planned Additions

- [ ] `agents/` — Specialised Codex agent definitions (e.g. code reviewer, scaffolder, documenter)
- [ ] `rules/coding-style.md` — Language and style conventions mirroring the Claude equivalent
- [ ] `rules/security.md` — Security rules for autonomous Codex runs
- [ ] `rules/patterns.md` — Established patterns to follow during implementation

---

## How to Use `AGENTS.md`

Place `AGENTS.md` in the root of your project repository. OpenAI Codex will automatically read it at the start of each run to understand project conventions, behaviour rules, and constraints.

Keep it concise and actionable — Codex works best with explicit, unambiguous instructions.

---

## Related
- `47-generic/coding-rules.md` — Baseline rules that `AGENTS.md` extends
- `41-agent-workflow/41.01-multi-agent-setup.md` — How Codex fits into a multi-agent pipeline
- `44-claude/` — The most fully built-out tool configuration — use as a reference for what to add here