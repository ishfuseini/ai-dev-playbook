# 47-generic — Generic Coding Rules

> 🚧 **Work in Progress** — This folder contains the baseline coding rules shared across all AI tools. Additional generic prompts and rules will be added here over time.

---

## Purpose

This folder is the **single source of truth** for coding rules that apply regardless of which AI tool or IDE you are using.

Tool-specific rule files (Cursor, Copilot, Codex, etc.) should extend this baseline — not duplicate it. If a rule applies everywhere, it belongs here.

---

## Contents

| File | Purpose |
|------|---------|
| `coding-rules.md` | Core coding rules: principles, structure, reliability, maintainability, observability, testing, and AI collaboration guidelines |

---

## Planned Additions

- [ ] Generic system prompt template (tool-agnostic)
- [ ] Generic agent instructions template
- [ ] Prompt chaining guide (how to pass output from one prompt to the next)
- [ ] Anti-patterns reference (common AI-assisted coding mistakes to avoid)

---

## Related
- `43-cursor/rules/coding-rules.mdc` — Cursor-specific extension of these rules
- `45-vscode/rules/copilot-instructions.md` — Copilot-specific extension
- `46-codex/rules/AGENTS.md` — Codex-specific extension