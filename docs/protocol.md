# Orchestrated workflow protocol

## States

`SPECIFIED → RED → IMPLEMENTING → VALIDATING → ACCEPTED | REJECTED`

Only the validator may move a task from `VALIDATING` to `ACCEPTED` or `REJECTED`.

## Artifacts

- `docs/tasks/<id>.md`: task, acceptance criteria, current state.
- `validation-reports/<id>.md`: commands, evidence, result, residual risk.

## Required checks

Formatting, type checking, linting, relevant unit/integration tests, architecture-boundary checks, migration validation after schema changes, and relevant Playwright tests after UI changes.
