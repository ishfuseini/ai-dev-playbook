# Security Guidelines

## Mandatory Security Checks

Before ANY commit:
- [ ] No hardcoded secrets (API keys, passwords, tokens)
- [ ] All user inputs validated
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (sanitized HTML)
- [ ] CSRF protection enabled
- [ ] Authentication/authorization verified
- [ ] Rate limiting on all endpoints
- [ ] Error messages don't leak sensitive data

## Secret Management

- NEVER hardcode secrets in source code
- ALWAYS use environment variables or a secret manager
- Validate that required secrets are present at startup
- Rotate any secrets that may have been exposed

## Input Trust Hierarchy

Not all inputs carry the same risk. Apply validation proportional to trust level.

| Trust Level | Sources | Treatment |
|-------------|---------|-----------|
| ❌ Never trust | User input, query params, form fields, URL paths | Validate, sanitize, and reject anything unexpected |
| ❌ Never trust | External API responses, webhooks | Validate schema and types before using |
| ❌ Never trust | File content (uploads, disk reads) | Treat as hostile; validate format and content |
| ❌ Never trust | Environment-injected data (headers, cookies) | Validate presence and format at boundaries |
| ✅ Always trust | Internal constants defined in source code | Use directly |
| ✅ Always trust | Config validated at startup | Use directly after startup validation passes |

**Rule of thumb:** If it crossed a network boundary or came from outside the process, validate it. If it was defined in your own source code, trust it.

## Security Response Protocol

If a security issue is found:
1. STOP immediately
2. Use the **security-reviewer** agent
3. Fix CRITICAL issues before continuing
4. Rotate any exposed secrets
5. Review the entire codebase for similar issues