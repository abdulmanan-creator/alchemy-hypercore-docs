---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> P2 scope. Order-by-order book updates for markets selected by the consumer. The stream name, filter keys, data fields, and operational guarantees are proposed contracts for engineering review.

# l4BookUpdates stream

## Subscribe
> The values below are illustrative. The contract is a draft pending implementation validation.

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "hypercore_subscribe",
  "params": {
    "stream": "l4BookUpdates",
    "filters": { "markets": ["BTC"] },
    "cursor": "optional-cursor"
  }
}
```


## Acknowledgement
```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": { "subscriptionId": "sub_01", "stream": "l4BookUpdates" }
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
    "stream": "l4BookUpdates",
    "cursor": "cursor_000001",
    "blockHeight": 123456,
    "blockTime": 1780000000000,
    "data": { "market":"BTC", "orders":[{"orderId":"12345","side":"bid","price":"100000.0","size":"0.10","action":"upsert"}] }
  }
}
```


## Proposed filters and behavior

- `markets` selects the consumer's intended scope. Omitted filters request the stream's default market-wide scope, except user and builder streams, which require their identity filter.
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
