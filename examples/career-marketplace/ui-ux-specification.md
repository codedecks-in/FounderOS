# UI/UX Specification — Career Marketplace MVP

**Status:** Draft  
**Inputs:** [Discovery](discovery.md), [PRD](prd.md)  
**Feeds into:** Frontend implementation and usability testing

## Primary journeys

**Seeker:** land on browse → filter/search experts → inspect profile, service, price, and timezone → select a slot → sign in/create account → review booking → pay → see confirmation and session instructions.

**Expert:** create account → complete profile → create a service → configure availability → connect payout account → preview public profile → publish → manage bookings.

## Pages

| Page | Main content/actions | Access |
|---|---|---|
| Expert discovery | Search, service filters, price/availability filters, result cards | Public |
| Expert profile | Bio, experience, linked credentials, services, reviews, availability | Public allowlisted fields |
| Sign-in / account | Authentication and account recovery | Public |
| Booking checkout | Service, timezone-explicit slot, price/fee summary, policy acknowledgement, payment handoff | Authenticated seeker |
| Booking confirmation/detail | State, time in participant timezone, session instructions, cancellation/support path | Participants |
| Expert setup | Profile, service, availability, payout onboarding status, publish preview | Authenticated expert |
| Expert bookings | Upcoming/past bookings and permitted participant details | Authenticated expert |

## States and accessibility

Every search and booking step needs loading, empty, validation, payment-pending, payment-failed, success, and recoverable-error states. Show timezone labels and avoid ambiguous local times. Use keyboard-accessible controls, visible focus, semantic headings, labeled form fields, clear errors, and status announcements. Mobile layout is required; design system and formal accessibility target need product approval.

## Unresolved product decisions

Whether browsing requires an account; exact cancellation/refund disclosure; what profile fields are verified vs self-asserted; review visibility/moderation; exact fees and tax display; session-link ownership and delivery; service catalog. Do not imply a credential was verified when only a LinkedIn/GitHub URL is present.
