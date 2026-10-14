# Product Requirements — Career Marketplace MVP

**Status:** Draft — founder decisions required  
**Owner:** Product  
**Inputs:** [Discovery](discovery.md), [market research](market-research.md)  
**Feeds into:** Architecture, design, implementation planning, and tests

**Working baseline:** India-only launch; consultations, mock interviews, and resume reviews; Stripe Connect candidate; 15% proposed platform fee; 24-hour cancellation window proposed for review. Provider eligibility, currency, final fee, and policy details are not approved yet. See [decision register](decision-register.md).

## 1. Overview

A marketplace where software engineers and tech professionals publish structured paid services and seekers discover and book relevant experts. The MVP tests whether trusted profiles, focused discovery, and a reliable paid booking flow create value for both sides.

## 2. Goals and non-goals

**Goals:** validate paid demand and expert supply; support a seeker from expert discovery to confirmed session; support an expert from profile setup to receiving a booking; measure booking completion and satisfaction.

**Non-goals:** AI assessments or feedback, async video review, native apps, community, job board, courses, group sessions, corporate sales, proprietary video, cross-border payments, and formal background checks. The India launch currency still requires approval. Recurring mentorship subscriptions are deferred; MVP services are one-time bookings unless the founder explicitly changes scope.

## 3. Users and stories

| ID | User story | Priority |
|---|---|---|
| US-1 | As an expert, I can create a profile and publish a service so seekers can evaluate and book me. | P0 |
| US-2 | As a seeker, I can find and compare experts by service, experience, price, and availability. | P0 |
| US-3 | As a seeker, I can select an available time, pay, and receive a booking confirmation. | P0 |
| US-4 | As an expert, I can see confirmed bookings and receive the information needed to deliver the session. | P0 |
| US-5 | As a participant, I can submit a review after a completed session. | P1; policy decision required |
| US-6 | As an operator, I can resolve booking, payment, and abuse issues with an auditable support path. | P0 operational requirement; tooling TBD |

## 4. Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-1 | A seeker can browse published expert profiles without signing in; authentication is required before booking. | P0; validate OQ10 |
| FR-2 | An expert can create and edit a profile with name, professional summary, experience, links, services, price, and availability. | P0 |
| FR-3 | An expert can select from a limited service catalog: 30/60-minute consultation, mock interview, or resume review. | P0 |
| FR-4 | A seeker can filter and sort profiles by service, role/company background, price, rating, and availability where data exists. | P0; ranking rules TBD |
| FR-5 | A seeker can select a currently available slot and create a pending booking without double-booking the slot. | P0 |
| FR-6 | A seeker can pay by card using the founder-approved India payment and currency configuration; a booking becomes confirmed only after verified provider confirmation. | P0; Stripe Connect India eligibility and currency remain gates |
| FR-7 | A confirmed booking produces notifications to both participants and a session delivery instruction/link. | P0; integration approach unresolved |
| FR-8 | Booking state changes, cancellations, refunds, and payment events are recorded for support and reconciliation. | P0; draft 24-hour cancellation window is for review; refund consequences unresolved |
| FR-9 | A participant may review only an eligible completed booking; review visibility and moderation rules require founder decision. | P1 |
| FR-10 | An expert may connect a payout account through the selected marketplace payment provider before accepting paid bookings. | P0 |

## 5. Non-functional requirements

| Area | Requirement / open target |
|---|---|
| Reliability | Prevent duplicate confirmed bookings and reconcile asynchronous payment events. Numeric availability target is not yet approved. |
| Performance | Discovery and profile pages should feel responsive on common mobile connections; numerical SLO and measurement method TBD. |
| Security | Enforce role and resource ownership on every private operation; never store raw card data. |
| Privacy | Minimize profile and booking data; retention, deletion, and consent rules require geography-specific review. |
| Accessibility | Core browse, profile, and booking flow must be keyboard operable and have labeled controls; target standard to be approved. |
| Compatibility | Responsive web MVP; supported browser matrix TBD. |

## 6. Main flow

Expert creates account → completes profile and service → connects payout account → publishes availability. Seeker browses public profiles → signs in to book → chooses service and slot → payment is authorized/confirmed → booking confirmation and session instructions are sent → session occurs → booking is marked complete → eligible reviews may be submitted.

## 7. Edge cases

| Scenario | Expected behavior |
|---|---|
| Slot is booked by another seeker during checkout | Reject stale slot, do not create a confirmed booking, offer refreshed availability. |
| Payment is declined or provider response is delayed | Keep booking unconfirmed; show safe retry/status and reconcile provider event. |
| Duplicate payment webhook/event | Idempotently process once; preserve audit trail. |
| Expert disconnects payout account or is not eligible | Prevent new paid bookings and explain the action needed. |
| Participant cancels or disputes a session | Apply an approved policy; until defined, do not automate refund outcomes. |
| Review submitted by a nonparticipant or before completion | Reject submission. |
| Timezone or daylight-saving transition | Display explicit timezone and store an unambiguous instant; verify conversion at boundaries. |

## 8. Metrics

Use discovery targets as hypotheses, not guarantees: profile completion, time to first booking, profile-to-booking conversion, completed bookings, cancellation/no-show, post-session satisfaction, repeat booking, GMV, and net take rate. Define event semantics and cohort windows before using these for launch decisions.

## 9. Open product decisions

Resolve remaining discovery OQ1–OQ10: finalize fee/payout terms, vetting, credential claims, cancellation/refund consequences, minimum supply, session-link ownership, acquisition, and account gating. India and the initial service catalog are the working baseline; review moderation and operational/legal feasibility still need approval. No implementation should encode proposed policy as final until approved.

## 10. Acceptance criteria for the core booking slice

- A seeker can view a published expert profile and its service, price, and timezone-aware availability.
- Concurrent attempts to reserve one slot cannot produce two confirmed bookings.
- Payment success creates one confirmed booking; payment failure creates none.
- The seeker and expert receive consistent confirmation details for a confirmed booking.
- Unauthorized users cannot read private booking or payment details.
- Each criterion has corresponding automated tests and traceability in the test report.
