---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> This page defines a minimal proposed error model so clients can distinguish validation failures, authorization failures, misses, and replay gaps.

# Errors

## HTTP errors
Use normal HTTP statuses: `400` invalid parameters, `401` unauthenticated, `403` unauthorized, `404` resource not found, `429` rate limited, and `5xx` transient service errors.

## JSON-RPC errors
Proposed codes: `-32600` invalid request, `-32601` method not found, `-32602` invalid params, `-32004` resource not found, `-32009` cursor unavailable, and `-32029` rate limited.

## WebSocket errors
A subscription error uses the JSON-RPC error object with the original request id. A replay gap is a subscription notification with `data.reason: cursor_unavailable`. <!-- ENGINEERING REVIEW: Confirm code ownership and retryability. -->