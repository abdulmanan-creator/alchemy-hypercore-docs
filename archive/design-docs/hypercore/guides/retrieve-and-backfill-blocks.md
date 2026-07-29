---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Retrieve and backfill blocks

Store a recent block-height checkpoint. Query `hl_getLatestBlocks`, identify the missing height range, call `hl_getBatchBlocks` in proposed batches of at most 200, and process blocks in ascending height order.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.