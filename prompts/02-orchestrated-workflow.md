# Orchestrated TDD Prompt

Build the booking MVP described in `docs/specification.md` using the roles and protocol in this repository.

1. The Architect creates the smallest task and its acceptance criteria.
2. The Implementer creates the required failing executable scenario, then implements only enough to make it pass.
3. The Validator independently runs the required checks, reviews the diff, and writes an evidence-based report.
4. If rejected, the Orchestrator links the report from the task and returns it to the Implementer. Before editing product code, the Implementer must create `docs/feedback/<task-id>.md` addressing every finding.
5. The Validator rechecks every original finding and explicitly closes or reopens it. Start the next task only after acceptance.

Never let the Implementer accept its own task. Do not weaken tests or replace domain guarantees with UI-only checks. Start with the invariant that two active bookings cannot exist for the same slot.
