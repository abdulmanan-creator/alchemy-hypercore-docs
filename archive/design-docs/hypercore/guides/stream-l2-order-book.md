---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Stream an L2 order book

Subscribe to `l2Book` for the market, wait for the initial snapshot, store its cursor, and render price levels. Use `l2BookDiff` only after the snapshot is installed.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.