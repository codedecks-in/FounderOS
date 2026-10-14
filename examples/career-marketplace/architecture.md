# Solution Architecture — Career Marketplace MVP

**Status:** Draft — technology and policy decisions unapproved  
**Owner:** Engineering  
**Inputs:** [PRD](prd.md), discovery, security draft  
**Feeds into:** Domain, database, API, implementation plan

## Goals and constraints

Prove a narrow marketplace booking flow with reliable slot reservation and payment reconciliation. Start with a modular monolith unless team or deployment constraints justify separation. Stack, hosting, identity provider, payment provider, scheduling integration, and launch geography remain undecided.

## System context

Actors: seeker, expert, support/operator, payment provider, notification provider, and optional calendar/session provider. The application owns marketplace profiles, service catalog, availability, booking state, review state, and provider references. Card data and payout onboarding are delegated to a qualified payment provider; the application must not store raw card data.

## Logical modules

| Module | Responsibility | Owns |
|---|---|---|
| Identity and access | Authentication, roles, account state | Application user identity and role assignments |
| Expert profiles | Profile, public visibility, service listings | Expert profile and service data |
| Discovery | Public search, filters, profile presentation | Search query behavior; source data remains in profile/booking modules |
| Availability | Expert availability and slot reservation | Availability rules and slot holds |
| Booking | Booking lifecycle and participant access | Booking state and timestamps |
| Payments | Provider checkout, webhook verification, reconciliation, fee/payout references | Internal payment ledger/reference state, not card credentials |
| Reviews | Eligibility and publication/moderation | Review records |
| Notifications | Booking and lifecycle notices | Delivery status and retry metadata |
| Operations | Support actions, audit trail, configuration | Administrative audit events |

## Critical flow and consistency

1. Discovery reads only published profiles and currently bookable services.
2. Booking atomically claims a slot or creates a short-lived hold to prevent concurrent allocation.
3. Payment is initiated with an idempotency key and internal booking reference.
4. A verified provider callback or reconciliation job advances payment state; only then does booking become confirmed.
5. Notification delivery is asynchronous and retryable; notification failure does not reverse a paid booking.
6. Cancellation/refund transitions follow a founder-approved policy and remain auditable.

Exact transaction model, hold expiry, provider event semantics, and reconciliation schedule require selection of the payment and data-store technologies.

## Quality attributes

Correctness of slot allocation and money-state reconciliation outranks search sophistication. Enforce authorization at module/API boundaries. Log correlation IDs and state transitions without payment secrets or unnecessary personal data. Establish numerical performance, availability, retention, and recovery targets before production design approval.

## Deployment and decisions

Deployment topology, database, queue, observability stack, backup RPO/RTO, and CI/CD are undecided. Stripe Connect is the preferred payment candidate, but Stripe's current India guidance says platform availability is invite-only and Connect integrations have use-case and funds-flow restrictions. Confirm Stripe acceptance, connected-account model, charge/payout flows, and supported legal entity before designing against it; retain a fallback provider evaluation. Proposed ADRs: modular monolith; payment marketplace provider/geography; availability representation; notification/session-link integrations; review and cancellation policy. Record each decision only after evidence and owner approval.

## Risks and open questions

- Payment provider support, marketplace eligibility, fees, disputes, tax reporting, and geography.
- Timezone and daylight-saving correctness; external calendar synchronization behavior.
- Cold-start supply and operational burden of manual trust review.
- Consumer, privacy, and marketplace obligations by launch location.

Approval required from founder/product and engineering before implementation planning is treated as final.

## Payment feasibility references

- [Stripe India marketplace support](https://support.stripe.com/questions/stripe-india-support-for-marketplaces?locale=en-GB) — India services are invite-only; Connect restrictions vary by integration and funds flow.
- [Stripe Connect India onboarding requirements](https://support.stripe.com/questions/onboarding-requirements-for-stripe-connect-in-india) — requirements vary with connected-account country, business type, and requested capabilities.
