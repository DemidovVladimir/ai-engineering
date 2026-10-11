# Shared engineering contract

## Product goal

Build a booking MVP with Next.js, TypeScript, Supabase PostgreSQL, Tailwind CSS, Vitest, and Playwright.

## Non-negotiable invariants

- A slot has at most one active booking.
- A repeated request using the same idempotency key creates no second booking.
- Cancelling an active booking releases its slot.
- Notification failure never invalidates a confirmed booking.
- Domain logic does not import Supabase, HTTP, UI, or notification-provider code.

## Safety and scope

- Do not add real payment, email delivery, credentials, or private keys.
- Store time in UTC and render the timezone explicitly.
- Prefer small vertical slices over broad rewrites.
- Never delete or weaken a test merely to make the suite pass.

## Completion standard

No task is complete merely because code compiles. Run its required checks, capture the result in a validation report, and record unresolved risks.
