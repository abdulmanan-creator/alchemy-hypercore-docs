---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> REST combines native-compatible `/info` reads with purpose-built enriched endpoints. Request and response examples are draft contracts.

# REST API

## Proposed interfaces
Native-compatible methods use `POST <HYPERCORE_HTTP_URL>/info` and a `type` discriminator. Enriched endpoints use purpose-built `POST <HYPERCORE_HTTP_URL>/v1/hypercore/<operation>` routes.

## History
Time-range responses use millisecond bounds and an opaque `nextCursor` where pagination is required. Do not assume retention or range caps until the availability contract is approved.