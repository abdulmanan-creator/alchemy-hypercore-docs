---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Stream wallet fills

Subscribe to `userFills` with a wallet filter. Persist each cursor and trade identifier after processing. Use `userFillsByTime` to recover events if replay cannot satisfy the cursor.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.