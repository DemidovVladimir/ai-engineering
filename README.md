# AI Engineering Booking Demo

This repository supports a video demonstration: the same booking service is built in two different ways.

1. `prompts/01-single-agent.md` asks one agent to build the application from a detailed request.
2. `prompts/02-orchestrated-workflow.md` runs an explicit TDD workflow with an Architect, Implementer, Validator, and Orchestrator.

## How to use it

Build the first version on `single-agent` using the first prompt. Return to `main`, then build the second version on `orchestrated-tdd`, one accepted task at a time. Do not mix both approaches in one branch: the comparison must remain fair.

Before implementation, read `AGENTS.md`, `docs/specification.md`, `docs/architecture.md`, and `docs/protocol.md`.

## Product

The product is an appointment-booking service: users browse available slots, create or cancel a booking, and produce a notification event. The demo deliberately excludes real payments, email delivery, and secrets.
