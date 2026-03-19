# S.C.A.F.F. Prompt Structure

A structured framework for writing high-quality prompts for AI-assisted development.
Each letter represents a required section that gives the AI the context it needs to produce accurate, usable output.

| Letter | Section | Purpose |
|--------|---------|---------|
| **S** | Situation | The current technical context |
| **C** | Challenge | The specific task to complete |
| **A** | Audience | Who will read, use, or maintain the output |
| **F** | Format | How the output should be structured and styled |
| **F** | Foundations | Non-negotiable requirements, rules, and constraints |

---

## Template

```
SITUATION: [Describe the current technical environment — stack, architecture, relevant patterns, and any existing code or systems involved.]

CHALLENGE: [Describe the specific task. Be precise about what needs to be built, changed, or fixed. Include inputs, outputs, and any known edge cases.]

AUDIENCE: [Who will use or maintain this output? Describe their skill level, background, and how long they will own this code.]

FORMAT: [Specify language, framework, style guide, file structure, naming conventions, and any output format requirements (e.g. tests, comments, types).]

FOUNDATIONS: [List the hard requirements — security rules, accessibility standards, error handling expectations, performance constraints, and any explicit DO NOTs.]
```

---

## Example 1 — React / Django (Web App Feature)

**SITUATION:** I'm building a Django e-commerce application with a React frontend. The application uses token-based authentication and follows a microservices architecture. The current codebase follows the repository pattern and uses Django REST Framework for API endpoints.

**CHALLENGE:** Create a user profile management component that allows users to update their personal information (name, email, shipping addresses) with proper validation. The component should handle form submission, display appropriate error messages, and securely communicate with the backend API.

**AUDIENCE:** The code will be maintained by a team of mid-level developers with Django experience but limited React knowledge. The codebase is expected to be maintained for at least 3 years and will eventually be handed over to the client's in-house team.

**FORMAT:** Use functional React components with hooks. Follow Airbnb style guide standards. Include PropTypes for all components. Write JSDoc comments for functions. Organize code into smaller, reusable components. Include unit tests using Jest and React Testing Library.

**FOUNDATIONS:** Implement proper input validation and sanitization. Handle all potential error states gracefully. Ensure all user interactions have appropriate loading states. Make the form accessible according to WCAG 2.1 AA standards. Implement rate limiting on submission attempts. Ensure profile updates require current password verification before saving changes.

---

## Example 2 — Python CLI Tool (Backend / Scripting)

**SITUATION:** I have a Python monorepo used by a data engineering team. We use Poetry for dependency management, follow PEP 8 strictly, and use `click` for CLI tooling. There is an existing `./scripts/` directory where utility scripts live.

**CHALLENGE:** Build a CLI command called `db-snapshot` that connects to a PostgreSQL database, dumps the specified table to a timestamped `.csv` file in a `/snapshots` directory, and logs the operation (rows exported, duration, file path) to a structured JSON log file.

**AUDIENCE:** This script will be run by data engineers and used in automated pipelines. It needs to be readable by someone unfamiliar with the project and safe to run in production environments.

**FORMAT:** Use `click` for the CLI interface. Use `psycopg2` for the database connection. Include type hints throughout. Write a `--help` description for every flag. Include a `test_db_snapshot.py` file using `pytest` with mocked DB calls.

**FOUNDATIONS:** Never log or print database credentials. Fail loudly with a clear error message if the DB connection fails — do not silently continue. All file writes must be atomic (write to a temp file, then rename). Do not use `SELECT *` — require an explicit column list argument.

---

## Variations

### ➕ Add an Example
Provide a concrete input/output example inside the Challenge section to eliminate ambiguity.

```
CHALLENGE: ... [task description] ...

Example:
  Input:  { "name": "Jane Doe", "email": "jane@example.com" }
  Output: Updated profile object returned with 200 OK, or a 422 with field-level errors.
```

---

### 🔒 Add Constraints
Append an explicit constraints block to the Foundations section to prevent unintended changes.

```
FOUNDATIONS: ... [existing foundations] ...

Constraints:
- Do NOT modify any existing tests
- Do NOT change the database schema
- Do NOT refactor unrelated code
- ONLY work on the files mentioned above
- PRESERVE all existing functionality
```

See `22-constraints.md` for a full constraints menu.

---

### 🧪 Test-Driven Prompting
Lead with the tests rather than the implementation. Include expected test cases in the Challenge section.

```
CHALLENGE: Write the implementation to make the following tests pass. Do not modify the tests.

[paste test file or test cases here]
```

---

### 🔁 Feedback & Iteration Loop

After the AI responds, use these follow-up prompts to refine and deepen the output:

| Goal | Follow-up Prompt |
|------|-----------------|
| Add tests | "Now write unit tests for the code you just produced. Cover happy path, edge cases, and error states." |
| Alternative approach | "Give me an alternative implementation with different tradeoffs. Explain what you changed and why." |
| Self-critique | "Review your own output. What are the weakest parts? What would you improve with more time?" |
| Tighten scope | "The output is too broad. Focus only on [specific part] and keep everything else unchanged." |
| Explain a decision | "Why did you choose [pattern/approach]? What alternatives did you consider?" |