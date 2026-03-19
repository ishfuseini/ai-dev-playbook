# Coding Rules
> This is the source of truth for coding rules across all AI tools and IDEs.
> Tool-specific rule files (Cursor, Copilot, Codex, etc.) extend this baseline
> and should only add what is unique to that tool — not duplicate what is here.

---

## Core Principles
- Write clear, simple, maintainable code
- Prefer readability over cleverness
- Keep functions small and single-purpose

## Design
- Use explicit interfaces and predictable behavior
- Avoid unnecessary abstraction
- Prefer standard, well-known solutions over custom implementations
- Avoid hidden state and side effects

## Structure
- Keep files focused and well-organized
- Group related logic together
- Avoid generic utility dumping grounds
- High cohesion, low coupling between modules

## Reliability
- Validate inputs at system boundaries and fail early
- Provide clear, actionable error messages
- Never silently swallow errors
- Handle all expected error states explicitly

## Maintainability
- Follow existing project conventions and patterns
- Make small, targeted changes
- Do not refactor unrelated code
- Write code that is easy to modify or remove
- Do not introduce new patterns without clear justification

## Observability
- Add logging where it meaningfully improves debugging
- Avoid excessive or noisy logs
- Ensure errors include enough context to diagnose the problem

## Testing & Reliability
- Write deterministic, testable code
- Separate pure logic from side effects where possible
- Add or update tests when behavior changes
- Ensure important logic has test coverage

## AI Collaboration
- Treat all generated code as a draft — review and verify before accepting
- Prefer solutions that are easy to understand, modify, and extend
- Make minimal, targeted changes — do not over-engineer
- Reuse existing utilities and patterns before creating new ones
- Preserve existing behavior unless explicitly asked to change it
- Do not introduce unnecessary dependencies
- If a task cannot be completed fully, state clearly what was done, what remains, and why