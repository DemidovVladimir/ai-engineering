# Orchestrated Workflow Protocol

## State machine

`SPECIFIED → RED → IMPLEMENTING → VALIDATING → ACCEPTED | REJECTED → IMPLEMENTING`

The Architect creates `SPECIFIED`. The Implementer moves a task through `RED`, `IMPLEMENTING`, and `VALIDATING`. Only the Validator may change `VALIDATING` to `ACCEPTED` or `REJECTED`. The Orchestrator controls the active task and starts no new implementation while the current one is unresolved.

## Ownership and artifacts

- `docs/tasks/<id>.md`: Architect and Orchestrator own the task, criteria, assumptions, state, and evidence links.
- `validation-reports/<id>.md`: Validator owns commands, evidence, findings, residual risks, and the final decision.
- `docs/feedback/<id>.md`: Implementer owns the response to a rejection, mapping every finding to planned code, test, and closure evidence.

## Mandatory feedback loop

1. The Validator records `ACCEPTED` or `REJECTED` in its report.
2. A rejection contains a finding ID, violated criterion or invariant, reproducible evidence, expected outcome, and closure evidence required.
3. The Orchestrator links the report and open finding IDs from the task, then returns it to `IMPLEMENTING`.
4. Before editing product code, the Implementer reads the report and creates `docs/feedback/<id>.md` for every open finding.
5. The Implementer may request revalidation only after the feedback file lists changed files, updated tests, and local check results.
6. The Validator explicitly closes or reopens each original finding with fresh evidence.

Reports are not passive logs: every rejected finding is a blocking work item.

## Required checks

Run formatting, type checking, linting, relevant unit and integration tests, architecture-boundary checks, migration validation after schema changes, and relevant Playwright tests after UI changes.

## Validation report format

Include task ID, reviewed revision or diff, environment, commands, pass/fail outcomes, numbered findings, residual risks, and a final `ACCEPTED` or `REJECTED` decision.
