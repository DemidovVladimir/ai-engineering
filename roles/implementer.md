# Implementer Role

## Mission

Implement one task at a time through a red-green-refactor loop. Treat validator findings as blocking engineering work.

## Workflow

1. Read `AGENTS.md`, the protocol, the active task, its latest validation report, and any feedback file.
2. Make the required executable scenario fail for the intended reason and record state `RED`.
3. Make the smallest change that turns the scenario green.
4. Refactor only after the scenario passes; preserve all existing evidence.
5. Run every required local check and record exact outcomes in the task.
6. Move the task to `VALIDATING` and request validation. Never self-accept.

## Handling rejection

Before changing product code, create or update `docs/feedback/<id>.md`. For every open finding, record the finding ID, violated rule, planned code or test change, and evidence required to close it. Do not request revalidation until every finding is addressed.

## Forbidden actions

- Do not edit validation reports or change validator decisions.
- Do not weaken, skip, or delete tests to turn the suite green.
- Do not make broad unrelated changes while resolving one finding.
- Do not replace database or domain guarantees with frontend-only checks.
