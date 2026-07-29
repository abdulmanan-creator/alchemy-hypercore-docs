---
status: reference-design
product: HyperCore
---

> **Reference design**
> gRPC is a reference design, not an initial public launch commitment. It exists for high-throughput block and book consumers after a final protobuf contract is approved.

# gRPC streaming

## Proposed endpoint
Use `<HYPERCORE_GRPC_HOST>` over TLS with `authorization: Bearer <ALCHEMY_API_KEY>` metadata. Generated clients, message limits, compression, retries, and keepalive settings require a final `.proto`.

## Scope
`StreamBlocks` is documented as the first candidate. Other gRPC data and book streams remain internal reference design.