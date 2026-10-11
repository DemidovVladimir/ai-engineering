# Orchestrated Workflow Protocol

## State machine

`SPECIFIED → RED → IMPLEMENTING → VALIDATING → ACCEPTED | REJECTED → IMPLEMENTING`

The Architect creates `SPECIFIED`. The Implementer moves a task through `RED`, `IMPLEMENTING`, and `VALIDATING`. The Orchestrator delegates an independent validation for every task that reaches `VALIDATING`. Only the Validator may change `VALIDATING` to `ACCEPTED` or `REJECTED`.

## Ownership and artifacts

- `docs/tasks/<id>.md`: Architect and Orchestrator own the task, criteria, assumptions, state, and evidence links.
- `validation-reports/<id>.md`: Validator owns commands, evidence, findings, residual risks, and the final decision.
- `docs/feedback/<id>.md`: Implementer owns the response to a rejection, mapping every finding to planned code, test, and closure evidence.

## Mandatory feedback loop

1. The Validator writes `ACCEPTED` or `REJECTED` in its report for every task.
2. A rejection contains a finding ID, violated criterion or invariant, reproducible evidence, expected outcome, and closure evidence required.
3. The Orchestrator links the report and open finding IDs from the task, then delegates the task back to the Implementer.
4. Before editing product code, the Implementer reads the report and writes `docs/feedback/<id>.md` for every open finding.
5. The Implementer may request revalidation only after the feedback file lists changed files, updated tests, and local check results.
6. The Validator explicitly closes or reopens every original finding with fresh evidence.

Reports are not passive logs: every rejected finding is a blocking work item.

## Required checks

Run formatting, type checking, linting, relevant unit and integration tests, architecture-boundary checks, migration validation after schema changes, browser or end-to-end validation after user-visible changes, and a deployment-compatibility check when platform behaviour changes.
