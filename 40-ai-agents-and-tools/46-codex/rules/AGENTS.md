# AGENTS.md

## Purpose
This file defines how Codex should behave when working in this repository.

---

## Session Start

At the beginning of every run, before writing any code:
1. Read `AI_CONTEXT.md` — project overview, stack, conventions, and current focus
2. Read `Memory/Memory_Root.md` (if it exists) — current project state and active decisions
3. Read the relevant `AI_SUMMARY.md` for any module you will be working in
4. Confirm your understanding of the task before proceeding

If these files do not exist, proceed with available context but note their absence.

---

## Core Principles
- Write clear, simple, maintainable code
- Prefer readability over cleverness
- Keep functions small and focused
- Avoid unnecessary abstraction

---

## Code Structure
- Follow existing project patterns and conventions
- Keep files modular and cohesive
- Group related logic together
- Avoid generic "utils" dumping grounds

---

## Interfaces & Types
- Use explicit inputs and outputs
- Use types where available (TypeScript, Python typing, etc.)
- Avoid hidden side effects

---

## Error Handling
- Validate inputs at boundaries
- Fail early with clear, actionable errors
- Do not introduce silent failures

---

## Implementation Behavior
- Make minimal, targeted changes
- Do not refactor unrelated parts of the codebase
- Reuse existing utilities before creating new ones
- Preserve existing behavior unless explicitly changing it

---

## Testing & Reliability
- Ensure logic is deterministic and testable
- Separate pure logic from side effects where possible
- Add tests when behavior changes

---

## Observability
- Add logs where debugging would be difficult
- Avoid excessive or noisy logging

---

## Codex-Specific Behavior
- Act as an autonomous senior engineer:
  - Plan, implement, and verify changes end-to-end
  - Do not stop at partial solutions
- Bias toward action:
  - Make reasonable assumptions and proceed
  - Only ask questions if truly blocked
- Ensure all changes:
  - Pass type checks and builds
  - Integrate cleanly with the existing codebase

---

## Constraints
- Do not introduce unnecessary dependencies
- Do not overwrite unrelated changes
- Do not use destructive git commands unless explicitly requested

---

## Output Expectations
- Deliver complete, working solutions
- Keep explanations concise and relevant
- Ensure code is easy to read and modify
- **If a task cannot be completed fully:**
  - Clearly state what was completed and what files were changed
  - Describe what remains to be done and why you stopped
  - Do not leave the codebase in a broken or inconsistent state
  - Provide explicit next steps so work can be resumed cleanly