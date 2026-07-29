---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> High-priority user history includes fills, orders, funding, ledger updates, and delegation history.

# Historical query APIs

## Proposed pagination
Time-range methods accept inclusive `startTime`, exclusive `endTime`, and may return an opaque `nextCursor`. Results are ascending by event time and stable tie-breaker. This design avoids duplicate pagination when events share a timestamp.