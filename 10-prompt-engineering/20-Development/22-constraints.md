# Constraints

Always add constraints to your prompts — they are especially important at the start of multi-step or agentic tasks. Constraints prevent AI tools from making well-intentioned but unwanted changes outside the scope of your request.

---

## When to Use Constraints

- Before handing off a task to an AI agent that will make file edits
- When working in a shared or production codebase where unintended changes are costly
- When you want deterministic, scoped output (e.g. code only, no explanations)
- When continuing work across multiple prompt turns to maintain consistency

---

## Constraints Menu

Copy and paste the relevant constraints into your prompt. Mix and match as needed.

---

### 🔒 Scope Constraints
Limit what files or areas the AI is allowed to touch.

```
## Constraints for this task:
- Do NOT modify any files not explicitly mentioned in this prompt
- Do NOT refactor unrelated code
- Do NOT rename or move files
- ONLY work within the [folder/module] directory
- PRESERVE all existing functionality not related to this task
```

---

### 🧪 Test Constraints
Protect your test suite from unintended changes.

```
## Constraints for this task:
- Do NOT modify any existing tests
- Do NOT delete test files
- Do NOT change test IDs, names, or assertions
- Only ADD new tests — do not alter existing ones
```

---

### 🗄️ Data & Schema Constraints
Guard against destructive database or schema changes.

```
## Constraints for this task:
- Do NOT change the database schema
- Do NOT generate or modify migration files
- Do NOT drop, rename, or alter existing tables or columns
- Do NOT change seed data or fixtures
```

---

### 🎨 Style & Formatting Constraints
Keep code style consistent and reviewable.

```
## Constraints for this task:
- Do NOT reformat code outside the lines you are changing
- Do NOT change indentation style or quote style
- Do NOT rename variables or functions for stylistic reasons
- Follow the existing naming conventions in the file
```

---

### ⚙️ Output Format Constraints
Control what the AI returns — useful when feeding output into another tool or step.

```
## Constraints for this task:
- Respond with code only — no explanations or commentary
- Do NOT wrap the output in markdown code blocks
- Return only the modified file(s), not the entire codebase
- Output a single file at a time
```

---

### 🛡️ Safety Constraints
Prevent irreversible or dangerous operations.

```
## Constraints for this task:
- Do NOT delete any files
- Do NOT make destructive API calls (DELETE, DROP, TRUNCATE)
- Do NOT commit or push any changes
- Do NOT modify environment variables or config files
- Do NOT expose secrets, tokens, or credentials in output
```

---

### 🔗 Dependency Constraints
Control package and dependency management.

```
## Constraints for this task:
- Do NOT add new dependencies without flagging them first
- Do NOT upgrade or downgrade existing packages
- Use only libraries already present in the project
```

---

## Full Example

```
## Constraints for this task:
- Do NOT modify any existing tests
- Do NOT change the database schema
- Do NOT refactor unrelated code
- ONLY work on the files mentioned above
- PRESERVE all existing functionality
- Do NOT add new dependencies without flagging them first
- Respond with code only — no explanations
```

---

## Tips

- **Be explicit over implicit.** If something matters to you, state it as a constraint.
- **Negative instructions are powerful.** "Do NOT do X" is often more reliable than "Only do Y."
- **Repeat key constraints** across turns in a long agentic session — context windows can cause earlier instructions to fade.
- **Stack constraints with the S.C.A.F.F. framework** — add a Constraints block inside the Foundations section for maximum specificity.