---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This guide uses the proposed HyperCore contract and should be revalidated against implementation fixtures before publication.

# Ingest historical exports

Poll the proposed export manifest, download only unseen Parquet objects, validate schema version and checksum, load partitions idempotently, and retain revision metadata so later corrections can be reconciled.

## Checkpoint rule
Advance a durable checkpoint only after downstream storage succeeds. Treat a gap, correction, or finality change as a reason to backfill and reconcile.