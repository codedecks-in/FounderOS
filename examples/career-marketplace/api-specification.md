# API Specification — Career Marketplace

**Status:** Draft; provider and auth contracts undecided  
**Inputs:** [PRD](prd.md), [domain model](domain-model.md), [security](security-architecture.md)  
**Feeds into:** Backend/frontend implementation and contract tests

## Conventions

Versioned JSON API is a candidate, not an approved technology choice. Public endpoints expose only published profile fields. Private endpoints require authenticated identity and resource-level authorization. Use stable error codes, pagination, request correlation IDs, and idempotency for booking/payment mutations.

## Candidate endpoint catalog

| Method / path | Purpose | Auth |
|---|---|---|
| GET /experts | Search published experts; filters and cursor pagination | Public |
| GET /experts/{expertId} | View public profile and active services | Public |
| POST /expert/profile | Create/update own profile | Expert |
| POST /expert/services | Create/update own service | Expert |
| PUT /expert/availability | Update own availability | Expert |
| GET /experts/{expertId}/slots | Retrieve bookable slots with timezone context | Public |
| POST /bookings | Hold slot and create pending booking; idempotency required | Seeker |
| POST /bookings/{bookingId}/checkout | Start provider checkout for own pending booking | Seeker |
| GET /bookings/{bookingId} | View booking if participant or authorized operator | Participant / operator |
| POST /provider-events/{provider} | Verify and process payment provider event | Provider signature; allowlisted endpoint |
| POST /bookings/{bookingId}/reviews | Submit eligible review | Booking participant |

Paths are illustrative. Confirm authentication, request schemas, pagination, rate limits, provider signatures, event ordering, and error contracts before implementation. Do not treat the endpoint list as a final OpenAPI contract.

## Common failure cases

`400` invalid input; `401` unauthenticated; `403` not authorized; `404` absent or intentionally concealed resource; `409` slot unavailable or invalid state transition; `422` business validation failure; `429` rate limit; `5xx` unexpected failure. Payment provider callbacks must be authenticated and idempotently processed.
