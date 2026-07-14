---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> Return non-funding ledger history for a user. The route choice, fields, pagination, and retention semantics are draft contracts unless supplied by a native-compatible implementation.

# userNonFundingLedgerUpdates

## Proposed request
> The values below are illustrative. The contract is a draft pending implementation validation.

```bash
curl --request POST '<HYPERCORE_HTTP_URL>/info' \
  --header 'Authorization: Bearer <ALCHEMY_API_KEY>' \
  --header 'Content-Type: application/json' \
  --data '{"type":"userNonFundingLedgerUpdates","user":"0x1111111111111111111111111111111111111111","startTime":1780000000000}'
```


## Proposed response
```json
{ "updates": [{"time":1780000000000,"hash":"0xabc","delta":{"type":"deposit","usdc":"100.00"}}], "nextCursor":"optional-cursor" }
```


## Contract notes

- Timestamps are proposed to use Unix milliseconds.
- Addresses are lower-case EVM-style addresses in examples; server-side normalization requires engineering confirmation.
- Time-range methods return data ordered by ascending event time and may return `nextCursor`; non-range methods retain native-compatible ordering where applicable.
- An empty result is an empty array. A malformed address is a JSON error; a valid address with no activity is not an error.
- <!-- ENGINEERING REVIEW: Confirm native field casing, method availability, maximum range, cursor opacity, finality, and rate/CU behavior. -->