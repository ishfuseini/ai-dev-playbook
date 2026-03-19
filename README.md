# ishDev AI Playbook

My AI learning and process to date — a personal collection of prompts, rules, templates, and tool references that I've built up while figuring out how to work effectively with AI in software development. It's a living document, not a finished product. Take what's useful, ignore what isn't.

---

## 📁 Structure

```
ai-dev-playbook/
├── 10-prompt-engineering/     # Core prompts for the dev lifecycle
├── 20-documentation/          # Prompts for generating project documentation
├── 30-project-setup/          # Repo and project initialization helpers
├── 40-ai-agents-and-tools/    # Rules & configs for AI tools and IDEs
├── 80-templates/              # Reusable prompt templates and frameworks
└── 90-tools/                  # External tool references for the AI dev ecosystem
```

---

## 📂 Contents

### `10-prompt-engineering/` — Dev Lifecycle Prompts

Prompts organized around the software development lifecycle.

#### `10-Dev-Spec/` — Specification
| File | Purpose |
|------|---------|
| `11-spec-intent.md` | Define the intent and goals of a feature or project |
| `12-spec-roadmap.md` | Generate a development roadmap from a spec |
| `13-spec-taskcreation.md` | Break a spec down into actionable tasks |

#### `20-Development/` — Active Development
| File | Purpose |
|------|---------|
| `21-scaff-prompt.md` | Scaffold a new feature or project |
| `22-constraints.md` | Define technical and architectural constraints |
| `23-code-review.md` | Prompt-driven code review |

---

### `20-documentation/` — Documentation Prompts

| File | Purpose |
|------|---------|
| `21-component-documentation.md` | Document a component's API, props, and usage |
| `22-adr-documentation.md` | Write an Architecture Decision Record (ADR) |

---

### `30-project-setup/` — Project Setup

Helpers for bootstrapping repos and project scaffolding.

> `31-repo/31.01-documentation/` — *(in progress)*

---

### `40-ai-agents-and-tools/` — AI Tool Configurations

Rules, instructions, and prompts tailored to specific AI coding tools and IDEs.

#### `41-agent-workflow/` — Multi-Agent
| File | Purpose |
|------|---------|
| `41.01-multi-agent-setup.md` | Configure and coordinate multi-agent workflows |

#### `42-ide-agnostic/` — Language-Specific Rules
| File | Language / Topic |
|------|-----------------|
| `42.01-python.md` | Python coding rules |
| `42.02-js-ts.md` | JavaScript / TypeScript coding rules |
| `42.03-css-ui.md` | CSS and UI styling rules |
| `42.04-mcp-servers.md` | MCP server setup and usage |

#### `43-cursor/` — Cursor Rules
| File | Purpose |
|------|---------|
| `rules/coding-rules.mdc` | Cursor-specific coding rules (`.mdc` format) |

#### `44-claude/` — Claude Configuration
| File | Purpose |
|------|---------|
| `44.01-rules/CLAUDE.md` | Top-level Claude project instructions |
| `44.01-rules/coding-style.md` | Coding style guidelines for Claude |
| `44.01-rules/patterns.md` | Preferred design patterns |
| `44.01-rules/security.md` | Security rules and guidelines |
| `44.02-agents/code-reviewer.md` | Claude sub-agent for code review |

#### `45-vscode/` — VS Code / GitHub Copilot
| File | Purpose |
|------|---------|
| `rules/copilot-instructions.md` | Custom instructions for GitHub Copilot |

#### `46-codex/` — OpenAI Codex
| File | Purpose |
|------|---------|
| `rules/AGENTS.md` | Agent instructions for Codex |

#### `47-generic/` — Tool-Agnostic Rules
| File | Purpose |
|------|---------|
| `coding-rules.md` | General coding rules applicable to any AI tool |

---

### `80-templates/` — Templates & Frameworks

| File | Purpose |
|------|---------|
| `testing.md` | Template for writing tests with AI assistance |
| `81-frameworks/81.01-new-prompt-template.md` | Template for documenting and packaging a new prompt for this library |

---

### `90-tools/` — Utility Prompts

| File | Purpose |
|------|---------|
| `documentation.md` | General-purpose documentation generation |
| `planning.md` | Project and sprint planning assistance |
| `security.md` | Security review and threat modelling |

---

## 🚀 Usage

1. **Browse** the relevant category for your current task.
2. **Copy** the prompt into your AI tool of choice (Claude, Cursor, Copilot, etc.).
3. **Adapt** the placeholders and context to your specific project.
4. **Iterate** — prompts are starting points, not final answers.

---
