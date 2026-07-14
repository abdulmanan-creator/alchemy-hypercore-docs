---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Return recent normalized block metadata. This is a proposed named-parameter JSON-RPC 2.0 contract for backfill and reconciliation.

# hl_getLatestBlocks

## Request
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc":"2.0",
  "id":1,
  "method":"hl_getLatestBlocks",
  "params":{ "limit": 10 }
}
```


## Result
```json
{
  "jsonrpc":"2.0",
  "id":1,
  "result":{ "blocks":[{"blockHeight":123456,"blockTime":1780000000000,"isFinal":true}], "nextCursor":"optional-cursor" }
}
```


## Validation and consistency

- No proposed cap; use a small bounded limit until engineering sets a maximum.
- Batch results are ordered by the input order unless a page states otherwise; missing valid identifiers are returned explicitly rather than silently dropped.
- `blockHeight` is a HyperCore height, not an EVM block number. `commands`, `actions`, `events`, and `fills` are separate arrays to avoid implying EVM transaction semantics.
- <!-- ENGINEERING REVIEW: Confirm JSON-RPC error codes, finality source, include-field set, and whether partial batch results are permitted. -->