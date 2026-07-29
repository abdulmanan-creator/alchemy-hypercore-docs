---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Return one normalized HyperCore block by height. This is a proposed named-parameter JSON-RPC 2.0 contract for backfill and reconciliation.

# hl_getBlock

## Request
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc":"2.0",
  "id":1,
  "method":"hl_getBlock",
  "params":{ "blockHeight": 123456, "include": ["metadata", "commands", "actions", "events", "fills"] }
}
```


## Result
```json
{
  "jsonrpc":"2.0",
  "id":1,
  "result":{ "block":{"metadata":{"blockHeight":123456,"blockTime":1780000000000,"isFinal":true},"commands":[],"actions":[],"events":[],"fills":[]} }
}
```


## Validation and consistency

- Not found returns JSON-RPC error code `-32004` in this proposed contract.
- Batch results are ordered by the input order unless a page states otherwise; missing valid identifiers are returned explicitly rather than silently dropped.
- `blockHeight` is a HyperCore height, not an EVM block number. `commands`, `actions`, `events`, and `fills` are separate arrays to avoid implying EVM transaction semantics.
- <!-- ENGINEERING REVIEW: Confirm JSON-RPC error codes, finality source, include-field set, and whether partial batch results are permitted. -->