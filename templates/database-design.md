# Database Design

**Status:** Draft / Reviewed / Approved  
**Owner:**  
**Inputs:** Domain model, architecture, data classification  
**Feeds into:** Migrations, backend implementation, operations

## Storage decisions
- Database / version (if decided):
- Rationale and alternatives:
- Data residency / retention constraints:

## Entity and table catalog
| Table | Purpose | Source domain concept | Sensitive fields |
|---|---|---|---|

## Schema
For each table, document columns, types, nullability, defaults, primary keys, foreign keys, and constraints.

## Relationships and cardinality
Describe important relationships and delete/update behavior.

## Indexes and query patterns
| Query / access pattern | Index | Expected volume / rationale |
|---|---|---|

## Integrity and concurrency
- Invariants enforced in database:
- Transaction boundaries / isolation:
- Idempotency and concurrency controls:

## Migrations and recovery
- Migration sequence:
- Backfill plan:
- Rollback / forward-fix plan:
- Backup and restore assumptions:

## Open questions and approval
-
