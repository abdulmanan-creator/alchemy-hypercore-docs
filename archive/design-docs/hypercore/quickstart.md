---
status: confirmed-scope
product: HyperCore
---

> **Confirmed product scope**
> This draft quickstart subscribes to `userFills`, stores a cursor, and recovers with the same cursor after reconnect.

# Quickstart

## Connect
```ts
const ws = new WebSocket("<HYPERCORE_WEBSOCKET_URL>", {
  headers: { Authorization: "Bearer <ALCHEMY_API_KEY>" },
});
ws.onopen = () => ws.send(JSON.stringify({ jsonrpc: "2.0", id: 1, method: "hypercore_subscribe", params: { stream: "userFills", filters: { users: ["0x1111111111111111111111111111111111111111"] } } }));
```


## Persist progress
Store the event cursor only after durable processing. On reconnect, pass the last stored cursor. If replay is unavailable or a gap is reported, query the relevant history or block range before resuming.

## Next steps
Read the WebSocket lifecycle, replay, and wallet-fill guide before using the draft contract in production.