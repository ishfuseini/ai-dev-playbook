# Prompt: Generate an Architecture Decision Record (ADR)

Use this prompt with your AI tool to document an architectural decision.

**Mode A – Generate from a description:**
> "Here is context about an architectural decision we made: [your description]. Please fill in the ADR template below as completely as possible. Flag any sections where you need more information."

**Mode B – Review a draft ADR:**
> "Here is a draft ADR. Please review it for missing context, weak reasoning, unconsidered alternatives, and any consequences we may have overlooked."

---

# ADR-[NNN]: [Title]

## Status
[Proposed | Accepted | Deprecated | Superseded]

**Date:** [YYYY-MM-DD]

## Superseded By
[Link to new ADR — only fill in if Status is "Superseded". Otherwise remove this section.]

---

## Context
[Describe the problem, situation, or requirement that led to this decision. What forces are at play? What is the current state, and why is a decision needed now?]

## Decision Drivers
[The key factors that shaped this decision. Be honest about trade-offs.]
- **Performance:** [e.g. must handle X requests/sec]
- **Maintainability:** [e.g. team size, long-term ownership]
- **Cost:** [e.g. budget constraints, infra cost]
- **Team Skills:** [e.g. existing expertise, learning curve]
- **Time:** [e.g. deadline pressure]
- **Security / Compliance:** [e.g. regulatory requirements]
- **Reversibility:** [e.g. how hard is it to undo this?]

---

## Decision
[State the decision clearly and directly. Start with "We will..." or "We have decided to..."]

## AI Involvement
[Describe how AI was used in researching, evaluating, or implementing this decision. Include which tool was used and what role it played — e.g. generating options, writing implementation, reviewing trade-offs.]

---

## Consequences

> Consider impact across: performance, maintainability, team velocity, cost, security, testability, and reversibility.

### Positive
-
-

### Negative
-
-

### Neutral
-
-

### Validation
[How will we know this was the right decision? What does success look like at 30 / 60 / 90 days? What metrics or signals will we monitor?]

---

## Alternatives Considered

### Alternative 1: [Name]
**Description:** [Brief description of this option]
**Why considered:** [What made this a viable option?]
**Why rejected:** [What trade-offs or risks ruled it out?]

---

### Alternative 2: [Name]
**Description:**
**Why considered:**
**Why rejected:**

---

## Related Decisions
[Link to other ADRs that are related, influenced this decision, or are influenced by it.]
- [ADR-NNN: Title](link)