---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This page specifies the intended client lifecycle for the proposed WebSocket contract.

# Connection lifecycle

## Lifecycle
1. Open a TLS WebSocket connection. 2. Authenticate during the handshake. 3. Send one or more subscriptions. 4. Wait for each acknowledgement. 5. Persist each processed cursor. 6. Reconnect with exponential backoff after a close. 7. Replay from durable cursors or backfill after a gap.

## Heartbeats and backpressure
The server should use WebSocket ping/pong. Clients should respond promptly and apply bounded queues. A slow consumer may receive a structured error before disconnect. <!-- ENGINEERING REVIEW: Confirm intervals, timeout, and maximum message size. -->