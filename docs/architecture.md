# Architecture

Use hexagonal boundaries.

- `domain/`: entities, value objects, invariants, domain services.
- `application/`: use cases and ports.
- `adapters/`: Supabase, HTTP routes, notification-event storage, UI integration.
- `tests/`: unit, integration, and end-to-end checks.

The domain layer must be runnable without Next.js or Supabase. Booking uniqueness must be enforced by a database constraint or transactional operation, not only by the UI.
