# Security Tools

A curated reference of external tools for securing AI-assisted development workflows. Organised by category — use this alongside `44-claude/44.01-rules/security.md` which covers security rules and checklists for your AI tools.

---

## Static Analysis (SAST)

Scan source code for vulnerabilities without running it.

| Tool | Link | Purpose |
|------|------|---------|
| **Semgrep** | https://semgrep.dev | Fast, customisable static analysis — large rule library, runs in CI |
| **SonarQube / SonarCloud** | https://sonarcloud.io | Broad SAST coverage — bugs, vulnerabilities, code smells |
| **CodeQL** | https://codeql.github.com | GitHub's semantic analysis engine — deep vulnerability detection |
| **Snyk Code** | https://snyk.io/product/snyk-code | AI-assisted SAST with inline IDE feedback |
| **Bandit** | https://github.com/PyCQA/bandit | Python-specific security linter — finds common issues fast |
| **ESLint Security Plugin** | https://github.com/eslint-community/eslint-plugin-security | JS/TS security rules for ESLint |

**When to use:** Semgrep is the default choice — fast, CI-friendly, and has rules for most stacks. Add CodeQL for deeper analysis on critical repos via GitHub Actions.

---

## Secret Scanning

Detect accidentally committed credentials, tokens, and API keys.

| Tool | Link | Purpose |
|------|------|---------|
| **Gitleaks** | https://github.com/gitleaks/gitleaks | Scan git history and working directory for secrets — run pre-commit and in CI |
| **TruffleHog** | https://github.com/trufflesecurity/trufflehog | Deep git history secret scanning with entropy analysis |
| **GitHub Secret Scanning** | https://docs.github.com/en/code-security/secret-scanning | Built-in GitHub secret detection — enables automatically on public repos |
| **detect-secrets** | https://github.com/Yelp/detect-secrets | Yelp's pre-commit secret detector — good for baseline + drift detection |

**When to use:** Run Gitleaks as a pre-commit hook on every project. Enable GitHub Secret Scanning for all repos. Use TruffleHog when auditing existing repos with long histories.

---

## Dependency Auditing (SCA)

Identify known vulnerabilities in third-party packages.

| Tool | Link | Purpose |
|------|------|---------|
| **Snyk** | https://snyk.io | Dependency scanning, license checks, and fix PRs — broad language support |
| **Dependabot** | https://github.com/dependabot | GitHub-native automated dependency update PRs |
| **OWASP Dependency-Check** | https://owasp.org/www-project-dependency-check | Open-source SCA — checks against NVD CVE database |
| **pip-audit** | https://github.com/pypa/pip-audit | Python dependency vulnerability scanner (PyPA official) |
| **npm audit** | https://docs.npmjs.com/cli/commands/npm-audit | Built-in Node.js dependency vulnerability check |
| **Socket** | https://socket.dev | Detects supply chain attacks and malicious packages before install |

**When to use:** Enable Dependabot on all repos as a baseline. Add Snyk or Socket for teams that need richer reporting or supply chain protection.

---

## Authentication & Secrets Management

| Tool | Link | Purpose |
|------|------|---------|
| **HashiCorp Vault** | https://www.vaultproject.io | Secret storage, dynamic credentials, and encryption as a service |
| **Doppler** | https://www.doppler.com | Developer-friendly secrets manager with environment syncing |
| **1Password Secrets Automation** | https://developer.1password.com | Team secrets management with CI/CD integration |
| **AWS Secrets Manager** | https://aws.amazon.com/secrets-manager | Managed secrets for AWS workloads |

---

## Related

- `44-claude/44.01-rules/security.md` — Security rules, checklists, and AI behaviour guidelines
- `10-prompt-engineering/20-Development/23-code-review.md` — Code review prompt with security checklist
- `44-claude/44.02-agents/code-reviewer.md` — Claude agent that cross-references security rules on every review
