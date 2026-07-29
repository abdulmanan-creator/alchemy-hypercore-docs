---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Historical data is a first-class HyperCore surface. Use REST for bounded user history, JSON-RPC for blocks and batches, and exports for research-scale datasets.

# Historical data

## Selection
Use an interactive time-range query for a small wallet history, block methods for a known checkpoint, a batch block call for bounded backfill, StreamBlocks plus block backfill for continuous processing, and exports for large research datasets.