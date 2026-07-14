---
status: draft-contract
product: HyperCore
---

> **Draft API contract**
> Block data is the authoritative recovery primitive in the draft design.

# Block data

## Proposed model
A normalized block has `blockHeight`, `blockTime`, and `isFinal`. Its optional raw material is separated into commands, actions, events, and fills. No EVM-style transaction hash or gas field is implied.