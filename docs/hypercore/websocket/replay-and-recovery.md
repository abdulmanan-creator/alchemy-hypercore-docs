---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Replay is a proposed differentiated reliability contract layered over purpose-built streams.

# Replay and recovery

## Recovery algorithm
Store the cursor after durable handling. Reconnect with that cursor. If the server reports `cursor_unavailable`, pause live application, query historical data or blocks from the last checkpoint, rebuild state, and subscribe without a stale cursor.

## Dedupe
Use the stream cursor as the primary event checkpoint. Use domain identifiers such as `tradeId`, `orderId`, or block height only as secondary verification keys.