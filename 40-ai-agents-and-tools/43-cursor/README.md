# 43 — Cursor Rules

> 🚧 **Work in Progress** — This folder currently contains a baseline coding rules file. Cursor-specific agent definitions, composer workflows, and additional rule files are planned.

## What's Here

| File | Purpose |
|------|---------|
| `rules/coding-rules.mdc` | Core coding rules applied to all `.ts`, `.tsx`, `.js`, `.jsx`, and `.py` files |

## Planned Additions

- [ ] `rules/documentation-rules.mdc` — Rules for generating and maintaining documentation
- [ ] `rules/testing-rules.mdc` — Rules for writing and updating tests
- [ ] `rules/security-rules.mdc` — Security-focused rules applied to sensitive files
- [ ] `agents/` — Cursor agent definitions (e.g. code reviewer, scaffolder)

## How to Use

Copy the contents of `rules/coding-rules.mdc` into your project's `.cursor/rules/` directory.

The rule uses `alwaysApply: true` and will automatically apply to all matching file types across the codebase.

## Related
- `47-generic/coding-rules.md` — The source of truth these rules extend
- `44-claude/44.01-rules/` — More complete rule set to use as a reference for expanding this folder