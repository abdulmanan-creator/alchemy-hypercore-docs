# HyperCore Documentation Open Questions

These questions block public documentation. The owning team should answer with implementation links, not prose-only confirmations.

| Priority | Question | Evidence reviewed | Likely owner | Blocks |
| --- | --- | --- | --- | --- |
| P0 | Where is the HyperCore service repository, and which commit/release is the documentation target? | Workspace-wide source, schemas, and configuration search found benchmark clients and plans only. | Engineering lead | All public pages |
| P0 | What public hostname, network matrix, and authentication scheme apply separately to REST, WebSocket, JSON-RPC, gRPC, exports, and data shares? | No gateway, hostname, or auth configuration located. | Platform/API gateway | Quickstart, authentication, endpoint, and transport pages |
| P0 | Which `/info` methods are actually public, and does Alchemy preserve native request/response behavior or wrap it? | A schedule reports `/info` support complete, but no implementation artifact exists. | REST owner | All REST references |
| P0 | Which P0 streams are public first: native passthrough only, purpose-built streams, or both? | Vetted sheet and newest build map use materially different P0 framings. | Streaming product + engineering | WebSocket overview and stream pages |
| P0 | What are the exact WebSocket subscribe, acknowledgement, data, error, unsubscribe, heartbeat, and reconnect envelopes? | No handler, fixture, or event-envelope type found. | Streaming engineering | Every WebSocket page and guide |
| P0 | Are l2 book updates snapshots, deltas, or both? What ordering, sequence, replay, dedupe, and gap guarantees are public? | Plans describe future replay and maintained-book work but no implementation. | Streaming/data engineering | Book and recovery guides |
| P0 | What are confirmed limits: requests, CU metering, subscriptions, filters, addresses, batch sizes, message sizes, and idle timeouts? | No configuration found. Planned batch caps are not public evidence. | Platform + product | Limits page and reference pages |
| P0 | What errors and status codes are part of each transport contract? | No HyperCore error definitions found. | API engineering | Errors page and examples |
| P1 | Are purpose-built `userFills`, `builderFills`, `liquidationFills`, `userOrderUpdates`, and `builderOrderUpdates` canonical public names? | Vetted intent exists; no final schema or registration exists. | Streaming product | Stream reference names |
| P1 | Is `allFills` a purpose-built Alchemy stream, an alias, or a native trade stream? | Vetted sheet and current native-passthrough list differ. | Streaming product | Fill-stream documentation |
| P1 | Is `webData2` or `webData3` the intended subscription, and is `outcomeMetaUpdates` real? | Inventory identifies both as conflicts; newest build map rejects the latter. | Hyperliquid integration owner | Subscription inventory |
| P1 | Is any gRPC API launching? If yes, where are the final `.proto` files, generated clients, endpoint, TLS/auth metadata, size limits, and replay semantics? | Current map gates gRPC at P4; no proto exists. | gRPC/data-platform owner | gRPC section |
| P1 | Are block queries and `StreamBlocks` customer-facing? | Plans disagree on phase and no schema exists. | Data-platform owner | Block and backfill documentation |
| P1 | Has raw capture started? What source files are persisted, when did capture begin, and what data-quality/reconciliation guarantees exist? | Current map labels node file writing and retention as a gating unknown. | Data engineering | Historical availability page |
| P2 | Which historical APIs, exports, and datasets are approved for launch, and what is their availability matrix? | Only planning phase lists exist. | Data product + engineering | Historical-data section |
| P2 | What is the public correction and late-arrival policy for data, blocks, and streams? | No policy or fixtures located. | Data engineering | Historical and recovery guides |
| P2 | Are writes publicly launching? If so, provide signing, API-wallet, preflight, idempotency, builder-fee, and regional/compliance contracts. | P0 prototype and P2 GA plans conflict with P3 inventory classification; no implementation is available. | Trading API owner + legal/compliance | Any write reference |
| P2 | Which documentation repository, MDX components, navigation definition, and validation commands should receive the final public pages? | No Alchemy docs repository was available. | Docs platform | Publication and CI validation |
