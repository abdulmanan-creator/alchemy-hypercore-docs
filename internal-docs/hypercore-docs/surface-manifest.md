# HyperCore Documentation Surface Manifest

**Prepared:** 2026-07-14  
**Drafting decision:** `docs/hypercore/` now contains an implementation-oriented draft API contract. It is intentionally not a production-availability claim.

## Scope and evidence

This manifest records the implementation-backed surface, not a roadmap or provider comparison. The discovery pass examined:

| Required discovery area | Evidence located | Result |
| --- | --- | --- |
| Repository structure | `/Users/abdul.manan/hypercore-bench`, `/Users/abdul.manan/Downloads/Hyperliquid exchange support`, and adjacent project folders | No Alchemy HyperCore service repository or documentation site is present. |
| REST route registration | `hypercore-bench/src/transports/http.ts` | Benchmark client only. It sends provider `/info` requests; it does not register an Alchemy route. |
| JSON-RPC registration | Workspace-wide source search | None. |
| WebSocket connection and subscriptions | `hypercore-bench/src/transports/ws.ts`, `src/methods.ts` | Benchmark client and provider-specific probe definitions only. No Alchemy WebSocket server or subscription handler. |
| Protobuf and generated gRPC code | Workspace-wide search for `*.proto`, generated stubs, and gRPC services | None for HyperCore. |
| Event envelopes | Workspace-wide source search | None for an Alchemy HyperCore service. |
| Historical queries and storage | Current internal build maps describe planned ClickHouse, Parquet, and archive work | No implementation, schema, retention configuration, or customer delivery contract located. |
| Blocks and block parsers | Current internal build maps describe planned parsers and JSON-RPC batch methods | No parser, block schema, or endpoint implementation located. |
| Exports and data shares | Current internal build maps list Parquet, object storage, and warehouse shares by later phase | No exporter, dataset manifest, share definition, or availability configuration located. |
| Authentication, hosts, and gateway routing | No HyperCore configuration found | No public hostname or transport-specific authentication contract can be documented. |
| Limits, CU metering, errors, and feature gates | No HyperCore service configuration found | No limits, CU costs, error catalog, or release gate can be documented. |
| Fixtures and captured messages | Benchmark database and provider probes only | No validated Alchemy request/response or streaming fixture located. |

## Source hierarchy applied

1. No running Alchemy HyperCore service code, schemas, tests, or fixtures were available.
2. The newest planning source found is [hypercore-internal-buildmap-v4.md](../../hypercore-internal-buildmap-v4.md), dated 2026-06-02. It describes P0 passthrough, P1 capture, later indexed products, and a gated P4 gRPC surface.
3. [HyperCore_API_Method_Inventory.xlsx](../../HyperCore_API_Method_Inventory.xlsx), updated 2026-07-13, is an inventory and comparison artifact. It is not a public Alchemy contract.
4. [hypercore-streams-prioritized.csv](../../hypercore-streams-prioritized.csv) is the local copy of the vetted stream-prioritization input. P0-P2 entries are retained as product requirements, not request/response schemas.
5. [hypercore-bench/src/methods.ts](../../hydromancer-bench/src/methods.ts) and `/Users/abdul.manan/hypercore-bench/src/methods.ts` are benchmark definitions. They do not establish an Alchemy API.

## Implementation-backed public surface

| Transport | Public operations confirmed | Publication status |
| --- | --- | --- |
| REST | None with an endpoint, authentication contract, and exact Alchemy schema present in this workspace | Blocked |
| WebSocket | None with an Alchemy server handler, envelope, filters, limits, or recovery contract present in this workspace | Blocked |
| JSON-RPC | None | Blocked |
| gRPC | None | Blocked |
| Historical queries | None | Blocked |
| Block queries or streams | None | Blocked |
| Bulk exports or data shares | None | Blocked |
| Write APIs | None | Blocked |

One current engineering document says HyperCore `/info` support was completed. That assertion is insufficient to publish documentation: no Alchemy route, hostname, authentication behavior, supported method list, compatibility statement, schema, test, or fixture was supplied. It is recorded as **conflicted or unverified** in the coverage matrix until implementation evidence is linked.

## Planned or requirement surfaces

The following are intentionally kept out of public documentation:

- P0-P2 streaming requirements, including purpose-built fill, order, book, and market-data streams.
- Native passthrough `/info` and WebSocket plans.
- Indexed historical queries, enriched reads, replay, and JSON-RPC batch methods.
- Capture, archive, object-storage, and warehouse-share plans.
- gRPC, which the current build map gates behind a later customer-performance trigger.
- All write-path concepts, including signed actions and builder-fee workflows.

## Publication gate

Before a public page is created, attach all of the following to the relevant row in the coverage matrix:

1. Final launch-scope approval and canonical operation name.
2. Route or transport endpoint and transport-specific authentication contract.
3. Implemented request and response types, or generated OpenAPI/protobuf.
4. Passing conformance or integration test plus a sanitized validated example.
5. Error semantics and any documented limits; omit a limit rather than infer it.
6. For historical data, confirmed availability, retention, freshness, and correction behavior.

## Draft contract surface

The requested draft tree now exists at `docs/hypercore/`. Its frontmatter distinguishes `confirmed-scope`, `draft-contract`, and `reference-design`. It uses neutral endpoint placeholders and `ENGINEERING REVIEW` markers rather than inventing a production hostname, limit, retention claim, or availability date. See [api-design-decisions.md](api-design-decisions.md) for the deliberate contract choices.

The tree is an implementation input. A later production-publication pass must still satisfy the publication gate below.
