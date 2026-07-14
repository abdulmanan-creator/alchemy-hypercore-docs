# HyperCore Documentation Publication Checklist

**Current result: draft contract complete; production-publication gate remains open.** The draft tree is available at `docs/hypercore/`; this checklist governs the later implementation-validated publication pass.

## Workspace discovery

- [x] Inspected available repository and project structure.
- [x] Located benchmark HTTP and WebSocket clients and classified them as non-service evidence.
- [x] Searched available workspace for REST routes, JSON-RPC registration, WebSocket handlers, protobuf, OpenAPI, generated clients, envelopes, fixtures, errors, limits, gateways, and storage/export implementations.
- [x] Compared the local prioritized stream input and method inventory with current internal build maps.
- [x] Recorded source conflicts and unknown historical availability.

## Per-operation gate

- [ ] Approved public launch scope exists.
- [ ] Canonical Alchemy operation name is approved.
- [ ] Endpoint or transport URL is confirmed.
- [ ] Authentication mechanism is confirmed for the specific transport.
- [ ] Implemented request schema is available.
- [ ] Implemented response or event schema is available.
- [ ] Validated, sanitized example exists.
- [ ] Error behavior is available.
- [ ] Limits and metering are confirmed or intentionally omitted.
- [ ] Historical availability and correction behavior are confirmed where applicable.
- [ ] Page uses the target documentation repository's MDX and navigation conventions.

## Draft contract completion

- [x] Created the requested `docs/hypercore/` draft tree.
- [x] Added a status marker to every draft page.
- [x] Added complete illustrative wire examples to REST, WebSocket, JSON-RPC, and gRPC operation pages.
- [x] Used neutral endpoint and API-key placeholders rather than a fabricated production URL.
- [x] Recorded proposed choices and compatibility implications in `api-design-decisions.md`.

## Release validation once a docs repository is supplied

- [ ] Documentation build passes.
- [ ] Link checker passes.
- [ ] Navigation validation passes.
- [ ] MDX lint passes.
- [ ] Code-block validation passes.
- [ ] Schema-example validation passes.
- [ ] Search public docs for `Hydromancer` returns no matches.
- [ ] Search public docs for `QuickNode` returns no matches.
- [ ] Search public docs for `Dwellir` returns no matches.
- [ ] Search public docs for `Allium` returns no matches.
- [ ] Search public docs for `white-label` returns no matches.
- [ ] Search public docs for `TBD`, `TODO`, `PROPOSED`, and `NEEDS CONFIRMATION` returns no matches.

## Handoff required

Provide the target Alchemy docs repository plus implementation links for each launch-scope operation. Then create only the public pages that pass the per-operation gate; do not publish a placeholder tree.
