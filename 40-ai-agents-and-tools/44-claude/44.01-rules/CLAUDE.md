# Claude Project Instructions

## Session Start
At the start of every session, before writing any code:
1. Read `AI_CONTEXT.md` — project overview, stack, conventions, and current focus
2. Read `Memory/Memory_Root.md` — current project state, active decisions, and next steps
3. Confirm your understanding of the current task before proceeding
4. Flag any gaps or ambiguities in the context before writing code

---

## Principles
You are working in a codebase that prioritizes clarity, simplicity, and maintainability.

- Prefer readable code over clever or compact solutions
- Keep functions small and focused
- Avoid unnecessary abstraction
- Use explicit inputs, outputs, and types
- Minimize hidden state and side effects

## Implementation Guidelines
- Follow existing patterns and conventions in the repository
- Do not introduce new architectural patterns without strong justification
- Keep changes minimal and scoped to the task
- Validate inputs and fail with clear, actionable errors
- Use standard libraries and well-known solutions over custom implementations

## Code Organization
- Keep files small and cohesive
- Avoid generic "utils" dumping grounds
- Group related logic together

## Observability
- Add logging where it improves debugging clarity
- Ensure errors include useful context

## Testing & Reliability
- Write deterministic, testable code
- Separate pure logic from side effects when possible
- Ensure tests exist or are updated for any changed behaviour

## When Making Changes
- Preserve existing structure unless improving it is necessary
- Do not refactor unrelated parts of the codebase
- Optimize for maintainability over cleverness

## AI Behavior
- Treat all generated code as a draft
- Verify correctness before finalizing
- Prefer solutions that are easy to understand and modify