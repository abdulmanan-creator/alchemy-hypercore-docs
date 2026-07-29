---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> No production limits or CU costs are asserted. This draft defines the categories engineering must make explicit before release.

# Limits and metering

## Required limits
Document request rate, concurrent WebSocket connections, subscriptions per connection, users and markets per filter, replay window, message size, batch size, and export concurrency.

## Metering
Meter REST requests, streamed event volume or connection time, JSON-RPC batches, and bulk-delivery bytes only after product approves the pricing model. Clients must not depend on undocumented quotas.