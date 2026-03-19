# 45 — VS Code / GitHub Copilot

> 🚧 **Work in Progress** — This folder is actively being developed. Current contents are a starting point and will be expanded.

---

## What Goes Here

Rules, instructions, and workflow guidance for AI-assisted development in **Visual Studio Code** using **GitHub Copilot**.

---

## Current Contents

| File | Status | Purpose |
|------|--------|---------|
| `rules/copilot-instructions.md` | ✅ Ready | Coding rules and Copilot-specific workflow guidance |

---

## Planned Additions

- [ ] **`.github/copilot-instructions.md` template** — drop-in workspace-level instructions file for any project
- [ ] **VS Code settings template** — recommended `settings.json` for AI-assisted development (Pylance, Biome, etc.)
- [ ] **Extensions list** — curated list of VS Code extensions that complement Copilot
- [ ] **Copilot agent / custom chat participant** — equivalent of the Claude `code-reviewer` agent for Copilot Chat
- [ ] **Keybindings and snippets** — productivity shortcuts for Copilot workflows

---

## How to Use `copilot-instructions.md`

Copy the contents of `rules/copilot-instructions.md` into your project at:

```
your-project/
└── .github/
    └── copilot-instructions.md
```

GitHub Copilot Chat will automatically read this file and apply the instructions to all workspace interactions.

---

## Related Files

- `47-generic/coding-rules.md` — the source-of-truth coding rules this file extends
- `44-claude/44.01-rules/CLAUDE.md` — equivalent rules file for Claude
- `46-codex/rules/AGENTS.md` — equivalent rules file for Codex