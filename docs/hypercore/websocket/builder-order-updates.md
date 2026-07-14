---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> P1 scope. Order lifecycle updates for orders attributed to builder codes. The stream name, filter keys, data fields, and operational guarantees are proposed contracts for engineering review.

# builderOrderUpdates stream

## Subscribe
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "hypercore_subscribe",
  "params": {
    "stream": "builderOrderUpdates",
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
  "result": { "subscriptionId": "sub_01", "stream": "builderOrderUpdates" }
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
    "stream": "builderOrderUpdates",
    "cursor": "cursor_000001",
    "blockHeight": 123456,
    "blockTime": 1780000000000,
    "data": { "orders": [{"builder":"0x2222222222222222222222222222222222222222","orderId":"12345","market":"BTC","status":"filled","filledSize":"0.10"}] }
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
