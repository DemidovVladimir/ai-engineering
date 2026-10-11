# Shared Engineering Contract

## Product goal

Build a booking MVP with Next.js, TypeScript, Supabase PostgreSQL, Tailwind CSS, Vitest, and Playwright.

## Non-negotiable invariants

- A slot has at most one active booking.
- A repeated request with the same idempotency key creates no second booking.
- Cancelling an active booking releases its slot.
- A notification failure never invalidates a confirmed booking.
- Domain logic does not import Supabase, HTTP, UI, or notification-provider code.

## Working agreement

- Read the shared contract, specification, architecture, protocol, and your role file before acting.
- Treat each acceptance criterion as an executable claim requiring evidence.
- Keep one task independently verifiable; do not hide unrelated refactors in it.
- Record explicit assumptions before implementation when a requirement is ambiguous.
- Never fabricate command output, test results, browser checks, or validation evidence.
- Never delete, weaken, or skip a test merely to make the suite pass.
- A role may write only the artifacts assigned to it by `docs/protocol.md`.

## Completion standard

Code compiling is not completion. A task is complete only after the Validator records reproducible evidence, marks it ACCEPTED, and the Orchestrator advances the workflow.
