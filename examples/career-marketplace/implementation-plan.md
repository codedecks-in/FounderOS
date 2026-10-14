# Implementation Plan — Career Marketplace MVP

**Status:** Draft pending founder approval of open product choices  
**Inputs:** [PRD](prd.md), [architecture](architecture.md), domain/API/security/UI drafts  
**Feeds into:** Incremental implementation and test planning

## Before implementation

Confirm feasibility of the India launch, identity approach, payment provider and supported funds flow, currency, final fee, cancellation/refund policy, session delivery, and data retention. Confirm the logical architecture and numeric operational targets. The service scope is consultations, mock interviews, and resume reviews. These choices materially affect contracts and cannot be safely inferred by implementers.

## Proposed increments

| Order | Increment | Dependencies | Exit evidence |
|---|---|---|---|
| 0 | Project foundation, identity, environments, audit conventions | Technology and geography decisions | Build/deploy path; auth and threat model reviewed |
| 1 | Expert profile and one-time service catalog | Identity, UI decisions | Expert can publish; public fields allowlisted |
| 2 | Availability and race-safe slot reservation | Persistence/concurrency decision | Concurrent booking tests show one reservation maximum |
| 3 | Seeker discovery and profile browsing | Published profile data | Search/filter acceptance criteria and usability review |
| 4 | Payment onboarding, checkout, webhook reconciliation | Provider, geography, fee, refund decisions | Sandbox payment lifecycle and idempotency evidence |
| 5 | Booking notifications and session delivery | Notification/session integration decision | Both parties receive correct timezone-aware booking details |
| 6 | Cancellation, support, and review slice | Approved policies | Auditable policy transitions and eligibility tests |
| 7 | Operational hardening and limited launch | All previous increments | Security, recovery, monitoring, support, and release gates pass |

## Risks and sequencing

Payment and scheduling integration are the largest external dependencies. Test payment event retries, duplicate events, slot races, timezone transitions, and partial failures early. Start with one service/geography if research supports it; do not build recurring plans or AI scope in this MVP.

## Definition of ready

The founder has approved unresolved product/policy decisions; contracts have owners; security and privacy requirements are reviewed; the first increment has testable acceptance criteria.
