# Prompt: Generate Component Documentation

Use this prompt to generate documentation for an existing component.

Paste the component's source code below, then send this to your AI:
> "Here is the source code for [ComponentName]. Generate complete component documentation using the structure below. Where information cannot be inferred from the code, mark the field as [NEEDS REVIEW] rather than guessing."

---

# Component: [Name]

## Overview
Brief description of the component's purpose, what problem it solves, and where it fits in the system.

---

## Props / API

| Prop | Type | Default | Required | Description |
|------|------|---------|----------|-------------|
| `propName` | `string` | `undefined` | ✅ | Description of what this prop does |
| `propName` | `boolean` | `false` | ❌ | Description of what this prop does |
| `propName` | `function` | `undefined` | ❌ | Callback signature: `(value: T) => void` |

---

## Events / Callbacks

| Event | Payload | Description |
|-------|---------|-------------|
| `onChange` | `{ value: T }` | Fired when the value changes |
| `onError` | `{ message: string, code: number }` | Fired when an error occurs |

---

## Slots / Children
_(Remove this section if not applicable)_

| Slot | Description |
|------|-------------|
| `default` | Main content rendered inside the component |
| `header` | Optional header override |

---

## Usage Examples

### Basic Usage
```javascript
// Minimal working example
```

### Advanced Usage
```javascript
// Full example showing all key props and callbacks
```

### Anti-patterns
```javascript
// ❌ Don't do this — explain why
```

---

## Design Constraints
Why the component is built the way it is. This captures intent and prevents future developers from "fixing" deliberate decisions.

- [e.g. Stateless by design — state is managed by the parent to keep this component reusable across contexts]
- [e.g. No direct API calls — data is passed in via props to keep this component testable]

---

## Key Design Decisions
Important architectural and implementation choices, with rationale.

- **[Decision]:** [Why it was made and what was considered]
- **[Decision]:** [Why it was made and what was considered]

---

## Dependencies

- **External packages:** [e.g. `react-query@5`, `zod@3`]
- **Internal dependencies:** [Components or utilities this depends on]
- **Dependents:** [Components or modules that depend on this one]

---

## Accessibility

- **ARIA roles used:** [e.g. `role="dialog"`, `aria-live="polite"`]
- **Keyboard navigation:** [e.g. Tab to focus, Enter to confirm, Escape to dismiss]
- **Screen reader behaviour:** [What is announced and when]
- **Compliance target:** [e.g. WCAG 2.1 AA]

---

## Testing

- **Test file location:** `[path/to/ComponentName.test.ts]`
- **How to run:** `[e.g. pnpm test ComponentName]`
- **Coverage:**
  - [ ] Happy path
  - [ ] Edge cases (empty state, max input, etc.)
  - [ ] Error states
  - [ ] Accessibility (e.g. axe, jest-axe)

---

## Changelog

| Version | Date | Change | Author |
|---------|------|--------|--------|
| `1.0.0` | [date] | Initial implementation | [name] |

---

## AI Generation Metadata
_Tracking how this component was built._

**Date Created:** [Creation date]
**AI Tool Used:** [Tool name and version]
**Prompt Reference:** [Link to prompt in library]
**Developer:** [Name of developer who worked with AI]