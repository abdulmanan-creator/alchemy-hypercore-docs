---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> The `hl_*` namespace is the proposed reconciliation and backfill API. Named parameters are canonical in this draft.

# JSON-RPC block and batch API

## Why JSON-RPC
Block and batch requests need one endpoint, a stable method namespace, predictable error semantics, and ordered partial results. Use this surface after a live-stream gap or when rebuilding from a checkpoint.