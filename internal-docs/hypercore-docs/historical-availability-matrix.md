# HyperCore Historical Availability Matrix

No customer-facing historical-data surface is implementation-backed in the available workspace. Unknown values remain unknown; they are not inferred from architecture plans or provider capabilities.

| Dataset or method | Access mode | Earliest coverage | Retention | Freshness | Partitioning or pagination | Schema source | Launch status | Public doc |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| User fills and fills-by-time | Potential historical REST | Unknown | Unknown | Unknown | Unknown | None | Requirement/design only | No |
| Historical orders | Potential historical REST | Unknown | Unknown | Unknown | Unknown | None | Requirement/design only | No |
| User funding and non-funding ledger history | Potential historical REST | Unknown | Unknown | Unknown | Unknown | None | Requirement/design only | No |
| Builder fills and liquidation fills | Potential historical REST | Unknown | Unknown | Unknown | Unknown | None | Requirement/design only | No |
| Oracle-price, market-liquidity, and book-history queries | Potential historical REST | Unknown | Unknown | Unknown | Unknown | None | Unverified / provider reference only | No |
| Block lookup and batch block lookup | Potential JSON-RPC | Unknown | Unknown | Unknown | Proposed batch caps must not be published | None | Approved design, implementation incomplete | No |
| Batch user-state, portfolio-state, and open-order lookups | Potential JSON-RPC | Unknown | Unknown | Unknown | Proposed batch caps must not be published | None | Approved design, implementation incomplete | No |
| Raw blocks, fills, orders, actions, replica commands, book diffs, misc events, builder fills | Planned internal capture and Parquet archive | Not started or not evidenced | Unknown | Unknown | Planned day/hour/coin/table partitioning only | No raw schema or archive writer located | Internal capture plan | No |
| Object-storage historical exports | Planned archive delivery | Unknown | Unknown | Unknown | Unknown | None | P2 design only | No |
| Snowflake share | Planned warehouse share | Unknown | Unknown | Unknown | Unknown | None | P3 provisional | No |
| BigQuery and Databricks shares | Planned warehouse share | Unknown | Unknown | Unknown | Unknown | None | P4 expansion | No |
| SQL access and explorer | Planned interactive analytics | Unknown | Unknown | Unknown | Unknown | None | P4 expansion | No |

## Availability publication requirements

Historical documentation needs a dataset-level contract: earliest available data, retention, freshness target, late-data and correction policy, query or partition bounds, deduplication key, schema version, and access-control model. None of those facts is available for publication in the inspected artifacts.
