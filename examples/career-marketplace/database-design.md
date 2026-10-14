# Database Design — Career Marketplace

**Status:** Logical draft; database vendor not selected  
**Inputs:** [Domain model](domain-model.md), architecture, security draft  
**Feeds into:** Schema migrations and implementation

## Logical tables

| Table | Main fields (logical) | Notes |
|---|---|---|
| users | id, email_ref, status, created_at | Identity provider may own credentials; minimize local copies. |
| expert_profiles | user_id, display_name, headline, bio, experience, links, publish_state | Public fields must be explicitly allowlisted. |
| services | id, expert_id, type, title, duration, price_minor, currency, status | Snapshot service terms into booking at purchase. |
| availability_rules | id, expert_id, timezone, rule_payload, active | Representation and calendar sync TBD. |
| slot_holds | id, expert_id, service_id, starts_at, ends_at, expires_at, state | Enforce no overlapping active reservation using chosen DB capabilities/locking strategy. |
| bookings | id, seeker_id, expert_id, service_snapshot, starts_at, ends_at, state, created_at | Private participant data; state transitions audited. |
| payment_records | id, booking_id, provider_ref, amount_minor, currency, state, idempotency_ref | Never store PAN/CVV or provider secrets. |
| reviews | id, booking_id, author_id, rating, text, visibility, created_at | Unique eligibility constraints and moderation state. |
| audit_events | id, actor_id, subject_type, subject_id, action, occurred_at, correlation_id | Avoid sensitive payloads; retention policy TBD. |
| notification_outbox | id, booking_id, event_type, destination_ref, state, retry_at | Outbox/retry pattern candidate; avoid storing unnecessary message content. |

## Integrity and indexes

Use foreign keys for ownership; unique provider event/idempotency references; indexes for published expert discovery, service filters, expert time-window lookup, seeker booking history, and provider reconciliation. Exact search strategy and overlap constraints depend on selected database and query volumes. Use integer minor units and explicit ISO currency codes for money values.

## Migrations and recovery

Prefer backward-compatible expand/migrate/contract changes. Define backups, restore drills, retention/deletion, payment reconciliation, and recovery objectives before production. No SQL schema or index DDL is approved until database selection and concurrency design are reviewed.
