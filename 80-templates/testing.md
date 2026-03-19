# Test Generation Prompt

Use this prompt to generate a comprehensive test suite for existing code.

Paste your code into the "Code to Test" section below, fill in the bracketed placeholders, then send the whole thing to your AI tool.

---

## The Prompt

SITUATION: I am working on a [language/framework] project. The codebase uses [testing framework] for testing, [mocking library if any] for mocks, and follows [testing conventions, e.g. "Arrange-Act-Assert", "Given-When-Then"]. Tests live in [test file location, e.g. `__tests__/` or alongside source files].

CHALLENGE: Write a comprehensive test suite for the code provided below. The suite should verify correct behaviour, cover edge cases, and confirm that all error states are handled as expected.

AUDIENCE: Tests will be maintained by developers who are familiar with [language] but may not have written the original code. Test names should be descriptive enough to understand what is being tested without reading the implementation.

FORMAT:
- Use [testing framework] syntax and conventions throughout
- Name tests descriptively: "[unit] should [expected behaviour] when [condition]"
- Organise tests into logical describe/context blocks grouped by function or behaviour
- Use beforeEach/afterEach for shared setup and teardown — do not repeat setup inside individual tests
- Mock all external dependencies (databases, APIs, file system, timers) — tests must run in isolation with no real I/O
- Use parameterised/data-driven tests for logic that varies only by input values

FOUNDATIONS:
- Cover the happy path thoroughly before adding edge cases
- Test every distinct error state and failure path explicitly
- Do NOT modify the source code — only write tests
- Do NOT test implementation details — test behaviour and outcomes
- All tests must be deterministic — no random values, no time-dependent logic unless mocked
- Aim for [X]% coverage of the code provided — typical targets: 90%+ for pure logic, 70–80% for integration-heavy code

---

## Code to Test

```
[Paste the function, class, module, or component you want tested here]
```

---

## Framework Quick Reference

Not sure what to put in the FORMAT section? Use one of these:

### Python — pytest
```
FORMAT:
- Use pytest with pytest-mock for mocking
- Use fixtures for shared setup
- Use @pytest.mark.parametrize for data-driven tests
- Place tests in a file named test_[module_name].py
- Use descriptive function names: test_[unit]_[condition]_[expected_result]
```

### JavaScript / TypeScript — Vitest
```
FORMAT:
- Use Vitest with vi.fn() and vi.mock() for mocking
- Use describe blocks to group related tests
- Use beforeEach for shared setup
- Import only from the public module interface — do not reach into internals
- Use test.each for parameterised cases
```

### JavaScript / TypeScript — Jest
```
FORMAT:
- Use Jest with jest.fn() and jest.mock() for mocking
- Use describe blocks to group related tests
- Use beforeEach/afterEach for setup and teardown
- Use jest.spyOn to mock specific methods without replacing the whole module
- Use test.each for parameterised cases
```

---

## Coverage Targets by Code Type

| Code Type | Target | Rationale |
|-----------|--------|-----------|
| Pure logic / utility functions | 95–100% | No I/O, easy to test exhaustively |
| Service / business logic layer | 85–95% | Core value — test thoroughly |
| Controllers / route handlers | 70–85% | Focus on happy path and error responses |
| UI components | 70–80% | Cover interactions and state changes |
| Integration / infrastructure code | 50–70% | I/O-heavy, mocking has limits |

---

## Iteration Guide

After the AI responds, use these follow-ups to deepen coverage:

| Goal | Follow-up Prompt |
|------|-----------------|
| Add edge cases | "What edge cases are not yet covered? Add tests for them." |
| Stress error handling | "Add tests that verify every error path — invalid input, null values, empty arrays, network failures." |
| Add parameterised tests | "Convert the repeated similar tests into a single parameterised test using test.each / @pytest.mark.parametrize." |
| Improve test names | "Rename all tests to follow the pattern: '[unit] should [expected behaviour] when [condition]'." |
| Check coverage gaps | "Review the source code. What lines or branches are not covered by the current test suite?" |
| Generate test data factories | "Write a factory function that generates valid [entity] test data with sensible defaults and optional overrides." |

---

## Related Files

- `10-prompt-engineering/20-Development/21-scaff-prompt.md` — S.C.A.F.F. framework this prompt uses
- `10-prompt-engineering/20-Development/22-constraints.md` — Add constraints to prevent the AI modifying source files
- `10-prompt-engineering/20-Development/23-code-review.md` — Review the generated tests before committing
- `42-ide-agnostic/42.01-python.md` — Python testing tool recommendations
- `42-ide-agnostic/42.02-js-ts.md` — JS/TS testing tool recommendations