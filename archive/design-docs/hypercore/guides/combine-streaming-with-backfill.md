---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Combine streaming with backfill

Run a live subscription and persist cursor plus block height. On reconnect, request replay. If replay fails, backfill the missing block range, dedupe domain events, update the checkpoint, then resume live delivery.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.