# Security Architecture — Career Marketplace

**Status:** Draft; geography and provider controls require review  
**Inputs:** [PRD](prd.md), [architecture](architecture.md), data model  
**Feeds into:** Implementation, testing, release

## Assets and data

Account identifiers and contact details; expert profile and external professional links; booking schedules and participant details; payment and payout references; reviews; operator actions; provider credentials and webhook secrets. Card data must remain with the payment provider.

## Threats and controls

| Threat | Required control / verification |
|---|---|
| Seeker accesses another user's booking | Resource-level authorization on every read/write; test cross-account access. |
| Expert alters another profile or availability | Derive owner from authenticated identity; reject client-supplied owner mismatch. |
| Fake payment callback confirms booking | Verify provider signature, timestamp/replay protections where supported, and reconcile event against provider API/state. |
| Duplicate/reordered payment events | Idempotent event handling and explicit state transition validation. |
| Slot race or booking abuse | Atomic reservation, rate limits, abuse monitoring, and concurrency tests. |
| Malicious profile/review content | Validate and safely render user content; define report/moderation path. |
| Credential or PII leakage in logs | Secret management, output redaction, access controls, retention limits, and log review. |
| Account takeover or payout redirection | Strong account security, step-up controls for payout changes, provider-hosted onboarding, and notifications. |

## Access and data handling

Public profile fields are an explicit allowlist. Booking, payment, contact, and operator data are private. Separate seeker, expert, and operator permissions; use least privilege for staff and service credentials. Encrypt transport and storage using platform-supported mechanisms; define deletion, retention, export, and incident processes for the selected launch geography.

## Residual decisions

Launch geography and applicable privacy/consumer/tax obligations; authentication provider and MFA policy; payout-change verification; review moderation; fraud/dispute handling; audit retention; vendor security review. Obtain qualified legal and payment-provider review before launch; this draft is not a compliance determination.
