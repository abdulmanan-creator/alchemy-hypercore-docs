---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Return normalized portfolio state for multiple users. This is a proposed named-parameter JSON-RPC 2.0 contract for backfill and reconciliation.

# hl_batchPortfolioStates

## Request
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc":"2.0",
  "id":1,
  "method":"hl_batchPortfolioStates",
  "params":{ "users": ["0x1111111111111111111111111111111111111111"] }
}
```


## Result
```json
{
  "jsonrpc":"2.0",
  "id":1,
  "result":{ "states":[{"user":"0x1111111111111111111111111111111111111111","portfolio":{"perpetual":{},"spot":{}}}],"missingUsers":[] }
}
```


## Validation and consistency

- Proposed maximum: 500 users.
- Batch results are ordered by the input order unless a page states otherwise; missing valid identifiers are returned explicitly rather than silently dropped.
- `blockHeight` is a HyperCore height, not an EVM block number. `commands`, `actions`, `events`, and `fills` are separate arrays to avoid implying EVM transaction semantics.
- <!-- ENGINEERING REVIEW: Confirm JSON-RPC error codes, finality source, include-field set, and whether partial batch results are permitted. -->