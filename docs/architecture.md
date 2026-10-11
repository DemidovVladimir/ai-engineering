# Architecture

Use **hexagonal architecture** (ports and adapters).

- `domain/`: entities, value objects, invariants, and domain services.
- `application/`: use cases and ports that express required capabilities.
- `adapters/`: Supabase persistence, HTTP routes, notification-event storage, and UI integration.
- `tests/`: unit, integration, architecture-boundary, and end-to-end checks.

The domain layer must be runnable without Next.js, Cloudflare, or Supabase. Infrastructure is replaceable at adapter boundaries. Booking uniqueness must be enforced by a database constraint or transactional operation, never only by the UI.

The Architect must identify each new dependency as a port or adapter before it is introduced. The Validator must reject direct infrastructure imports into the domain layer.
