---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Query wallet trading history

Use `userFillsByTime` with bounded millisecond timestamps for fills, `historicalOrders` for lifecycle history, and funding or ledger methods for account movements. Page until `nextCursor` is absent.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.