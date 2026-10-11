# Single-agent prompt

Build a production-minded MVP of a booking application.

Use Next.js with TypeScript and the App Router, Supabase for PostgreSQL and migrations, Tailwind CSS, Vitest, and Playwright. Users must be able to view available slots, reserve one with their name and email, cancel an existing booking, and see a confirmation. Record notification events but use a local adapter or log; do not send real email.

Use UTC internally. Add migrations and seed data. Validate every API input. Enforce at the database level that a slot has at most one active booking. Repeating a request with the same idempotency key must not create a second booking. Cancelling must release the slot. A notification failure must not invalidate a successful booking. Keep domain logic independent of Supabase, HTTP handlers, and UI.

After each milestone run formatting, type checking, linting, relevant tests, and the relevant Playwright test. Explain what was validated and what remains risky. Add tests for concurrent booking attempts, repeated requests, cancellation, invalid input, and notification failure. Do not claim a feature works without running the relevant validation. Start with a brief implementation plan, then execute it.
