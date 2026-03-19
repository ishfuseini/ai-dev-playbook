# Common Patterns

> This is a living document. Add patterns here as they are established in your projects. Two patterns is a starting point — not a complete picture.

---

## Skeleton Projects

When implementing new functionality, prefer proven foundations over building from scratch.

### With Multi-Agent Setup
1. Search for battle-tested skeleton projects
2. Use parallel agents to evaluate options:
   - Security assessment
   - Extensibility analysis
   - Relevance scoring
   - Implementation planning
3. Clone best match as foundation
4. Iterate within proven structure

### Solo / Single-Agent Fallback
1. Search for well-maintained starter templates (GitHub, official docs, community)
2. Evaluate 2–3 options against these criteria:
   - Active maintenance (recent commits, open issues addressed)
   - Matches your stack and architecture style
   - Not over-engineered for your use case
3. Clone the best match and strip what you don't need
4. Document why you chose it in an ADR

---

## Design Patterns

### Repository Pattern

Encapsulate data access behind a consistent interface so business logic never talks directly to storage.

**Rules:**
- Define standard operations: `findAll`, `findById`, `create`, `update`, `delete`
- Concrete implementations handle storage details (database, API, file, cache, etc.)
- Business logic depends on the abstract interface, not the storage mechanism
- Enables easy swapping of data sources and simplifies testing with mocks

**Structure:**
```
interface UserRepository {
  findAll(): Promise<User[]>
  findById(id: string): Promise<User | null>
  create(data: CreateUserInput): Promise<User>
  update(id: string, data: UpdateUserInput): Promise<User>
  delete(id: string): Promise<void>
}

// Concrete implementation (e.g. Postgres, in-memory mock, etc.)
class PostgresUserRepository implements UserRepository { ... }
```

---

### API Response Envelope

Use a consistent response shape for all API endpoints. Never return raw data directly — always wrap it.

```typescript
// Success response
{
  "success": true,
  "data": { ... },       // The payload — null on error
  "error": null,         // Error message — null on success
  "meta": null           // Pagination or extra context — null if not needed
}

// Error response
{
  "success": false,
  "data": null,
  "error": "Resource not found",
  "meta": null
}

// Paginated success response
{
  "success": true,
  "data": [ ... ],
  "error": null,
  "meta": {
    "total": 142,
    "page": 2,
    "limit": 20
  }
}
```

**Rules:**
- Always include `success` as a boolean — never infer it from HTTP status alone
- `data` is `null` on error; `error` is `null` on success — never both populated
- Use `meta` for pagination, request IDs, or supplementary context
- Keep HTTP status codes consistent with `success`: 2xx = true, 4xx/5xx = false

---

### Service Layer

Keep controllers/routes thin by pushing all business logic into a service layer.

**Rules:**
- Controllers handle request/response only — no business logic
- Services contain all business rules and orchestration
- Services do not import from controllers or route files
- Services may call repositories, other services, or external clients

**Structure:**
```
route/controller  →  service  →  repository / external client
```

---

### Error Boundary Pattern

Catch and handle errors at defined boundaries rather than letting them propagate unpredictably.

**Rules:**
- Define explicit error types (e.g. `ValidationError`, `NotFoundError`, `AuthError`)
- Catch at the outermost layer (route handler, agent loop, CLI entry point)
- Log full error context server-side; return safe, user-friendly messages client-side
- Never let unhandled errors reach the user silently

```typescript
// Define typed errors
class NotFoundError extends Error {
  constructor(resource: string, id: string) {
    super(`${resource} with id "${id}" not found`)
    this.name = 'NotFoundError'
  }
}

// Catch at boundary
try {
  const user = await userService.getById(id)
  return res.json({ success: true, data: user, error: null, meta: null })
} catch (err) {
  if (err instanceof NotFoundError) {
    return res.status(404).json({ success: false, data: null, error: err.message, meta: null })
  }
  logger.error('Unexpected error', { err, id })
  return res.status(500).json({ success: false, data: null, error: 'Internal server error', meta: null })
}
```

---

## Patterns To Add

Use this section to track patterns worth documenting as the project matures:

- [ ] Command / Query separation (CQRS)
- [ ] Factory pattern for object creation
- [ ] Event-driven / pub-sub within a service
- [ ] Optimistic UI updates
- [ ] Background job / queue pattern