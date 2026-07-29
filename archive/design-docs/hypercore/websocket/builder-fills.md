---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> P1 scope. Executed fills attributed to builder-routed orders. The stream name, filter keys, data fields, and operational guarantees are proposed contracts for engineering review.

# builderFills stream

## Subscribe
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "hypercore_subscribe",
  "params": {
    "stream": "builderFills",
    "filters": { "builders": ["0x2222222222222222222222222222222222222222"] },
    "cursor": "optional-cursor"
  }
}
```


## Acknowledgement
```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": { "subscriptionId": "sub_01", "stream": "builderFills" }
}
```


## Event envelope
Every event is ordered within a subscription by `cursor`. `blockHeight` and `blockTime` identify the source block when available; consumers should persist the cursor only after processing the event.

```json
{
  "jsonrpc": "2.0",
  "method": "hypercore_subscription",
  "params": {
    "subscriptionId": "sub_01",
    "stream": "builderFills",
    "cursor": "cursor_000001",
    "blockHeight": 123456,
    "blockTime": 1780000000000,
    "data": { "fills": [{"builder":"0x2222222222222222222222222222222222222222","market":"BTC","price":"100000.0","size":"0.01","tradeId":"trade_03"}] }
  }
}
```


## Proposed filters and behavior

- `builders` selects the consumer's intended scope. Omitted filters request the stream's default market-wide scope, except user and builder streams, which require their identity filter.
- A supplied `cursor` requests replay after that cursor. Cursor format, retention, and replay window require engineering confirmation.
- Snapshot-capable streams emit an initial snapshot before deltas. For `l2BookDiff`, consumers must begin from a compatible `l2Book` snapshot.
- <!-- ENGINEERING REVIEW: Confirm filter cardinality, authorization, ordering scope, replay retention, and slow-consumer policy. -->

## Unsubscribe
```json
{
  "jsonrpc": "2.0",
  "id": 2,
  "method": "hypercore_unsubscribe",
  "params": { "subscriptionId": "sub_01" }
}
```
