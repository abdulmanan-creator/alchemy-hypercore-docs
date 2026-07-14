---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> The intended developer experience uses an Alchemy API key for each transport. Header names and gRPC metadata are proposed pending platform review.

# Authentication

## HTTP and WebSocket
Use `Authorization: Bearer <ALCHEMY_API_KEY>`. WebSocket clients that cannot set headers may use an implementation-approved token mechanism; do not assume query-string authentication.

## gRPC
The proposed metadata key is `authorization: Bearer <ALCHEMY_API_KEY>`. TLS is required in the production design.

<!-- ENGINEERING REVIEW: Confirm API-key format, project scoping, WebSocket handshake behavior, export credentials, and error response for invalid keys. -->