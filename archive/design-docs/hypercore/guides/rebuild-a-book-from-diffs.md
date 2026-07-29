---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Rebuild a book from diffs

Start from a durable L2 snapshot. Apply ordered diffs one cursor at a time. On a cursor discontinuity, discard local state, fetch a new snapshot or historical checkpoint, then resume.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.