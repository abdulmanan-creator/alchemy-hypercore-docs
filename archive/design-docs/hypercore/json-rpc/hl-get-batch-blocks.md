---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Return multiple blocks in ascending block-height order. This is a proposed named-parameter JSON-RPC 2.0 contract for backfill and reconciliation.

# hl_getBatchBlocks

## Request
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc":"2.0",
  "id":1,
  "method":"hl_getBatchBlocks",
  "params":{ "blockHeights": [123456, 123457], "include": ["metadata", "fills"] }
}
```


## Result
```json
{
  "jsonrpc":"2.0",
  "id":1,
  "result":{ "blocks":[{"metadata":{"blockHeight":123456,"blockTime":1780000000000,"isFinal":true},"fills":[]}],"missingBlockHeights":[] }
}
```


## Validation and consistency

- Proposed maximum: 200 block heights.
- Batch results are ordered by the input order unless a page states otherwise; missing valid identifiers are returned explicitly rather than silently dropped.
- `blockHeight` is a HyperCore height, not an EVM block number. `commands`, `actions`, `events`, and `fills` are separate arrays to avoid implying EVM transaction semantics.
- <!-- ENGINEERING REVIEW: Confirm JSON-RPC error codes, finality source, include-field set, and whether partial batch results are permitted. -->