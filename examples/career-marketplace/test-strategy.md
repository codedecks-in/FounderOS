# Test Strategy — Career Marketplace MVP

**Status:** Draft  
**Inputs:** [PRD](prd.md), [domain model](domain-model.md), [API](api-specification.md), [security](security-architecture.md)  
**Feeds into:** Implementation validation and release decision

## Risk priorities

1. Duplicate booking or payment and inconsistent money state.
2. Unauthorized access to bookings, profiles, or payout-related actions.
3. Incorrect timezone/availability behavior.
4. Stale or misleading profile/service data at checkout.
5. Failed notifications or external provider outages.

## Requirement traceability

| Requirement | Test coverage required |
|---|---|
| FR-1–FR-4 discovery/profile | Public/private field contract, filters, pagination, empty and malformed queries |
| FR-5 slot reservation | Concurrent requests, expired holds, daylight-saving boundaries, stale availability |
| FR-6–FR-8 payments/bookings | Provider sandbox contract, success/failure/delay, duplicate and reordered events, reconciliation |
| FR-9 reviews | Eligibility, duplicate submission, moderation/visibility policy once approved |
| FR-10 payout onboarding | Incomplete/restricted provider account and payout-change authorization |
| Security requirements | Cross-user authorization matrix, webhook forgery/replay, injection/XSS, rate limiting, log redaction |

## Test levels

- Unit: business state transitions, money arithmetic, eligibility, timezone conversion.
- Integration: persistence constraints, transaction/locking, outbox, provider adapter with deterministic fakes.
- Contract: application API schemas and provider callback verification.
- End-to-end: expert setup → seeker booking → payment confirmation → participant confirmation → completion.
- Operational: reconciliation replay, backup/restore, alert and rollback rehearsal before launch.

Use fixed clocks and deterministic fixtures; no test should call live payment/calendar services. Exact coverage thresholds and supported timezone set require project decisions. Defects must map to requirement IDs and include reproduction evidence.
