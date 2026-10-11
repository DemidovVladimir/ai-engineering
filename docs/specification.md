# Product specification

## User journey

1. A visitor sees available appointment slots.
2. The visitor enters a name and email, then reserves one slot.
3. The visitor can cancel the reservation.
4. The system records a confirmation-notification event without delivering real email.

## Acceptance criteria

- Two concurrent requests for the same slot cannot both succeed.
- Retrying a request with the same idempotency key returns the existing booking outcome.
- A cancelled booking makes the slot available again.
- A failed notification event does not roll back a successful booking.
- Invalid input returns a clear client error without exposing internals.
