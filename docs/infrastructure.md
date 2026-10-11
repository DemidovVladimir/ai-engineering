# Infrastructure Constraints

## Hosting

- Deploy the application to Cloudflare.
- Prefer Cloudflare Workers for full-stack Next.js behaviour. Use Cloudflare Pages only if the implementation can remain a static export.
- Treat preview deployments as part of validation when a task changes user-visible behaviour.

## Database and BaaS

- Use Supabase as the managed PostgreSQL BaaS.
- The demo must remain viable on the Supabase Free Plan.
- Design for low data volume: store only booking records, slots, cancellation data, idempotency keys, and compact notification-event metadata.
- Do not store binary assets, verbose unbounded logs, raw request payload archives, or unnecessary duplicated data in Supabase.
- Add indexes only for verified query patterns and document retention or cleanup rules for event data.
- Include a migration path: the application must keep working with a standard PostgreSQL connection and must not put business rules exclusively in the frontend.

## Operational boundaries

- Keep secrets in the deployment platform’s environment configuration; never commit them.
- Use Supabase database constraints and transactions for integrity-critical booking behaviour.
- Record assumptions about free-tier limits and operational trade-offs in the README rather than presenting the demo as a production-scale service.
