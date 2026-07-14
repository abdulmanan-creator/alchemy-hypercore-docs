---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Historical products must describe late partitions and corrections before launch.

# Data corrections

## Proposed correction contract
Exports should publish a manifest revision and immutable file identifier. Consumers deduplicate by dataset-defined primary key plus revision. REST and streaming clients should treat a finality change or correction notice as a reconciliation trigger. <!-- ENGINEERING REVIEW: Confirm finality and mutation policy. -->