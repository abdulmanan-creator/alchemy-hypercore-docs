---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> Return order lifecycle history for a user. The route choice, fields, pagination, and retention semantics are draft contracts unless supplied by a native-compatible implementation.

# historicalOrders

## Proposed request
> The values below are illustrative. The contract is a draft pending implementation validation.

```bash
curl --request POST '<HYPERCORE_HTTP_URL>/info' \
  --header 'Authorization: Bearer <ALCHEMY_API_KEY>' \
  --header 'Content-Type: application/json' \
  --data '{"type":"historicalOrders","user":"0x1111111111111111111111111111111111111111"}'
```


## Proposed response
```json
{ "orders": [{"orderId":"54321","coin":"BTC","side":"B","limitPx":"100000.0","sz":"0.10","status":"filled","timestamp":1780000000000}] }
```


## Contract notes

- Timestamps are proposed to use Unix milliseconds.
- Addresses are lower-case EVM-style addresses in examples; server-side normalization requires engineering confirmation.
- Time-range methods return data ordered by ascending event time and may return `nextCursor`; non-range methods retain native-compatible ordering where applicable.
- An empty result is an empty array. A malformed address is a JSON error; a valid address with no activity is not an error.
- <!-- ENGINEERING REVIEW: Confirm native field casing, method availability, maximum range, cursor opacity, finality, and rate/CU behavior. -->