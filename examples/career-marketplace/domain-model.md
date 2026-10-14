# Domain Model — Career Marketplace

**Status:** Draft  
**Inputs:** [PRD](prd.md), [architecture](architecture.md)  
**Feeds into:** Database design, API, implementation

## Ubiquitous language

| Term | Definition |
|---|---|
| Seeker | User looking for a paid career service. |
| Expert | User offering one or more services. |
| Service | A bookable offering with type, duration, price, and delivery instructions. |
| Availability | Expert-defined windows from which bookable slots are derived. |
| Booking | A seeker's request to reserve a service slot, linked to payment and session delivery. |
| Payment | Internal record of provider checkout, collection, refund, and payout references. |
| Review | Feedback by an eligible booking participant under an approved policy. |

## Contexts and aggregates

Identity; Expert Profile (profile and services); Availability (windows and slot holds); Booking (participants, service snapshot, slot, lifecycle); Payment (provider references and state); Review (booking-linked feedback); Operations (audit and support actions).

Booking is the consistency boundary for slot reservation and booking lifecycle. Payment provider state is external; store verified references and reconcile rather than assuming a callback always arrives once or in order.

## Core invariants

- Only a published and eligible expert service is bookable.
- A slot can have at most one active hold or confirmed booking.
- A booking has one seeker, one expert, one service snapshot, and one reserved time interval.
- A booking is not confirmed until payment success is verified according to the provider contract.
- Payment event handling is idempotent and preserves an audit trail.
- Only participants of an eligible completed booking may submit a review; review policy and whether both parties can review remain open.
- A user's role does not by itself grant access to another user's private booking details.

## Lifecycle proposals (confirm with provider/policy)

Booking: `pending` → `awaiting_payment` → `confirmed` → `completed`; alternatives include `expired`, `cancelled`, `refunded`, `disputed`, and `no_show`. Exact transitions and refund behavior are not approved. Payment: `created` → provider-defined processing / succeeded / failed, with separate refund and payout references.

## Open decisions

Slot hold duration, recurring service exclusion, cancellation/no-show/refund rules, review visibility/moderation, account suspension effects, and provider-specific payment state mapping.
