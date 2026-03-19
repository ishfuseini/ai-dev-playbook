# Documentation Tools

A curated reference of external tools for generating, publishing, and maintaining project documentation in AI-assisted workflows.

---

## Diagram & Architecture Visualization

| Tool | Link | Purpose |
|------|------|---------|
| **EraseR DiagramGPT** | https://www.eraser.io/diagramgpt | Generate architecture diagrams and flowcharts from natural language descriptions |
| **Mermaid** | https://mermaid.js.org | Text-based diagramming (flowcharts, ERDs, sequence diagrams) — renders in GitHub and most markdown tools |
| **Excalidraw** | https://excalidraw.com | Lightweight, collaborative whiteboard for quick architecture sketches |
| **DbDiagram** | https://dbdiagram.io | Design and document database schemas visually with a simple DSL |
| **Swimlane** | https://swimlane.com | Process and workflow diagrams with automation |

---

## README & Repo Documentation

| Tool | Link | Purpose |
|------|------|---------|
| **readme-ai** | https://github.com/eli64s/readme-ai | AI-generated README files from your codebase — good starting point to edit from |
| **Readme.so** | https://readme.so | Simple drag-and-drop README editor with pre-built sections |
| **Make a README** | https://www.makeareadme.com | Template and guidance for writing a good README manually |

---

## API Documentation

| Tool | Link | Purpose |
|------|------|---------|
| **Swagger / OpenAPI** | https://swagger.io | Industry standard for documenting REST APIs — generate interactive API explorers |
| **Redoc** | https://redocly.com | Render OpenAPI specs as clean, readable documentation |
| **Scalar** | https://scalar.com | Modern, beautiful API reference docs from OpenAPI specs |
| **Mintlify** | https://mintlify.com | Also excellent for API docs with built-in OpenAPI support |

---

## When to Use What

| Situation | Recommended Tool |
|-----------|-----------------|
| Need a diagram fast from a description | EraseR DiagramGPT or Mermaid |
| Setting up a developer docs portal | Mintlify (hosted) or Docusaurus (self-hosted) |
| Documenting a REST API | OpenAPI + Scalar or Redoc |
| Documenting UI components | Storybook |
| Auto-generating a README to start from | readme-ai |

---

## Related

- `20-documentation/21-component-documentation.md` — Prompt template for writing component docs with AI
- `20-documentation/22-adr-documentation.md` — Prompt template for Architecture Decision Records
- `30-project-setup/31-repo/31.01-documentation` — Layered documentation strategy for AI-assisted projects
