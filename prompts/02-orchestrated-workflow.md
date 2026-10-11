# Orchestrated TDD prompt

Build the booking MVP described in `docs/specification.md` using the roles and protocol in this repository.

1. The Architect creates the smallest task and its acceptance criteria.
2. The Implementer first makes the corresponding executable scenario fail, then implements only enough to make it pass.
3. The Validator independently runs the required checks, reviews the diff, and writes an evidence-based report.
4. If rejected, return only the specific findings to the Implementer. If accepted, begin the next task.

Never let the Implementer accept its own task. Do not weaken tests or replace domain guarantees with UI-only checks. Start with the invariant that two active bookings cannot exist for the same slot.
