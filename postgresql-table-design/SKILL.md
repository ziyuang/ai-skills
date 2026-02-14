---
name: postgresql-table-design
description: Design PostgreSQL schemas with explicit constraints and migration safety across language stacks. Use when changing tables, indexes, and relational contracts.
---

# PostgreSQL Table Design First Principles

## Design order
1. Real query/write paths first.
2. Schema invariants second.
3. Indexes third (only for measured paths).

## Rules
- Encode invariants in DB constraints: PK, FK, unique, check.
- Nullability must reflect real optionality.
- Do not encode domain meaning with sentinels.
- Keep migrations additive unless a breaking change is explicit and planned.
- Keep app-level types/models aligned with schema changes in the same change set.

## Anti-patterns
- Generic "status" text fields replacing typed state.
- Wide nullable tables used as dump bins.
- Indexing everything "just in case."
- Data migrations without rollback or verification plan.
