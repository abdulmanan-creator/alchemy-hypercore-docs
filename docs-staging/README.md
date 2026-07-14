# HyperCore Docs Staging Package

This directory is a pre-migration staging package. It is not the official Alchemy documentation repository and must not be copied as a drop-in production contribution.

- Chain API content is staged under `content/chains/hyperliquid/hypercore/`.
- Data API content is staged under `content/data/hypercore/`.
- REST references are candidate OpenAPI 3.1 under `src/openapi/hypercore/`.
- JSON-RPC references are candidate OpenRPC under `src/openrpc/hypercore/`.
- WebSocket and gRPC references are canonical staging MDX.
- Hostnames, authentication, limits, availability, and implementation details still require engineering confirmation.

## Visibility and confidentiality

`hidden: true` removes a section or page from normal public navigation, but it does not make the source confidential. The official Alchemy docs repository is public, and unlisted pages may remain accessible through direct links. Sensitive or embargoed information must not be committed until approved for public exposure.

## Later migration checklist

1. Review product scope, public-repository safety, and all engineering-review annotations.
2. Adapt frontmatter, navigation, and callouts to the actual `alchemyplatform/docs` conventions.
3. Validate OpenAPI and OpenRPC against implemented schemas and examples.
4. Replace placeholders and proposed fields only with implementation-approved values.
5. Decide launch visibility after product, engineering, and docs review.
6. Run the official repository build, lint, navigation, and link checks.
