---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> HyperCore is Alchemy's planned developer data and streaming product for Hyperliquid's native exchange engine. This draft defines the intended product and API contracts; it does not describe a production endpoint.

# Alchemy HyperCore

## Product shape
HyperCore combines purpose-built real-time streams, native-compatible reads, historical queries, normalized block data, and recovery workflows. P0-P2 streams are confirmed product scope. Exact wire contracts on this site are proposed unless marked otherwise.

## Choose a surface
Use WebSocket for live books, fills, orders, and market context. Use REST for user and historical reads. Use JSON-RPC block methods for deterministic checkpointing and bounded backfills. Use bulk exports for research-scale ingestion.

## Contract notation
Use `<HYPERCORE_HTTP_URL>`, `<HYPERCORE_WEBSOCKET_URL>`, `<HYPERCORE_GRPC_HOST>`, and `<ALCHEMY_API_KEY>` until platform configuration is finalized.