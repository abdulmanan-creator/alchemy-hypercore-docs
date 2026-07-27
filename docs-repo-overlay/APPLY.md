# Apply HyperCore private-preview overlay

Copy this directory onto the target repository root, then apply the additive unified diff with `patch -p1 < content/docs.yml.patch`. Do not replace `content/docs.yml`.

Availability uses the shared `<Callout intent="launch">` notice included through `<Markdown src="..." />`. `DocPageFrontmatter` defines `tags` but no availability/badge field or rendering behavior; `docs.yml` rejects badge keys. `MDX_FEATURES.md` confirms `launch` and `Markdown` support.

`api-name` values are `hypercore` (REST) and `hypercore-chain` (OpenRPC). The indexer maps both REST and chain generated specs by JSON basename and throws on duplicate basenames (`src/content-indexer/utils/apiSpecs.ts:40-75`), so plain `hypercore` cannot be used for both.

The WebSocket envelope uses `subscribe`, `subscription`, and `unsubscribe`; purpose-built stream names are carried in `subscription.type`.
