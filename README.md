# Orchestrated TDD Booking Experiment

This branch implements the booking MVP through a controlled multi-role workflow.

Before work begins, read `AGENTS.md`, `docs/specification.md`, `docs/architecture.md`, `docs/infrastructure.md`, and `docs/protocol.md`. Then follow `prompts/02-orchestrated-workflow.md`.

The Architect specifies small tasks. The Implementer uses red-green-refactor. The Validator independently validates every task. The Orchestrator delegates each handoff and blocks the next task until acceptance.
