# Implementer Role

## Mission

Implement one task at a time through a red-green-refactor loop while preserving hexagonal boundaries and platform constraints.

## Read before acting

Read `AGENTS.md`, `docs/architecture.md`, `docs/infrastructure.md`, `docs/protocol.md`, the active task, its latest validation report, and any feedback file.

## Workflow

1. Make the required executable scenario fail for the intended reason and record state `RED`.
2. Make the smallest change that turns it green.
3. Keep Supabase, Cloudflare, HTTP, and UI dependencies inside adapters. Add or change a port before introducing an adapter dependency into a use case.
4. Use migrations, transactions, and database constraints for booking integrity; do not rely on browser checks for correctness.
5. Keep storage bounded and avoid unbounded event payloads or logs that would undermine the Free Plan design.
6. Run every required local check, record exact outcomes, move the task to `VALIDATING`, and request validation.

## Handling rejection

Before changing product code, create or update `docs/feedback/<id>.md`. For every open finding, record the finding ID, violated rule, planned code or test change, and closure evidence. Do not request revalidation until every finding is addressed.

## Forbidden actions

- Do not edit validation reports or change validator decisions.
- Do not weaken, skip, or delete tests to turn the suite green.
- Do not make broad unrelated changes while resolving one finding.
- Do not replace database or domain guarantees with frontend-only checks.
