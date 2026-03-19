# GitHub Copilot Instructions

> **Session Start:** At the start of each session, read `AI_CONTEXT.md` (project overview) and
> `Memory/Memory_Root.md` (current project state) before writing any code. Confirm your
> understanding of the current task before proceeding.

---

## Coding Principles
- Write clear, maintainable, and predictable code
- Prefer simplicity over cleverness
- Keep functions small and focused
- Avoid unnecessary abstractions
- Treat all generated code as a draft — review before accepting

## Structure & Organization
- Follow existing project conventions and patterns
- Keep files modular and easy to navigate
- Avoid large, multi-purpose files
- Avoid generic "utils" dumping grounds — group logic by feature or domain

## Interfaces & Types
- Use explicit inputs and outputs
- Use types where available (TypeScript, Python typing, etc.)
- Avoid hidden side effects
- Prefer immutable data — return new objects rather than mutating in place

## Error Handling
- Validate inputs at system boundaries
- Fail early with clear, actionable error messages
- Never silently swallow errors

## Development Guidelines
- Make minimal, targeted changes
- Do not refactor unrelated code
- Reuse existing utilities and patterns when possible
- Do not introduce new dependencies without flagging them

---

## Testing
- Ensure all important logic has test coverage
- Prefer deterministic, predictable functions that are easy to test
- Separate pure logic from side effects to simplify testing
- Cover happy path, edge cases, and error states
- Update or add tests whenever behaviour changes
- Use `#file` context to reference test files when generating new tests

---

## AI Usage — Copilot-Specific Guidance

### Inline Completions
- Use inline completions for boilerplate, repetitive patterns, and well-understood logic
- Always review completions before accepting — treat them as suggestions, not ground truth
- Reject completions that introduce unfamiliar patterns or dependencies not in the project

### Copilot Chat
- Use `#file` to attach specific files as context before asking questions
- Use `#selection` to focus Copilot on a specific block of code
- Use `#codebase` for project-wide questions (e.g. "where is auth handled?")
- Prefer Chat for explanation, refactoring proposals, and test generation
- Prefer inline completions for small, local edits

### Workspace Instructions (`.github/copilot-instructions.md`)
- Project-level instructions live in `.github/copilot-instructions.md`
- These apply automatically to all Copilot Chat interactions in the workspace
- Keep them concise — Copilot works best with focused, actionable rules

### Slash Commands
| Command | When to use |
|---------|-------------|
| `/explain` | Understand unfamiliar code before modifying it |
| `/fix` | Address a specific error or diagnostic |
| `/tests` | Generate test cases for a function or module |
| `/doc` | Generate inline documentation or JSDoc |

---

## Constraints
- Do not modify files outside the current task scope
- Do not change existing tests unless explicitly asked
- Do not alter the database schema or migration files
- Do not expose secrets, tokens, or credentials in output
- Preserve all existing functionality not related to the current change