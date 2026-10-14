# Founder Decision Register — Career Marketplace

**Status:** Founder working baseline captured; approval and feasibility checks remain  
**Owner:** Founder  
**Source:** [Discovery open questions](discovery.md#open-questions)

Use this register to resolve product assumptions before implementation. A proposed default is not approval. For each decision, record evidence, owner, date, rationale, affected artifact versions, and any review trigger.

| ID | Decision required | Why it blocks or shapes the product | Current state |
|---|---|---|---|
| D-01 | Launch geography and currency | Payment eligibility, support coverage, tax/privacy/consumer review, and market focus | India-only MVP selected; charge/settlement currency and operational/legal feasibility to confirm |
| D-02 | Platform take rate and expert payout terms | Expert acquisition, checkout display, payment configuration, unit economics | 15% platform fee is a proposed baseline for review; payout terms and unit economics remain open |
| D-03 | Self-serve vs. reviewed expert onboarding | Trust model, operations, launch speed, public profile claims | Open; discovery OQ2 |
| D-04 | Credential claim and verification level | User trust, liability, moderation process, UI wording | Open; discovery OQ3 |
| D-05 | Session link ownership/integration | Scheduling flow, provider access, privacy and reliability | Open; discovery OQ4 and OQ8 |
| D-06 | Cancellation, rescheduling, refund, no-show, and dispute policy | Booking state machine, user disclosures, payment/refund operations | Draft a 24-hour cancellation window for review; refund, late-cancel, expert-cancel, no-show, and dispute consequences remain open |
| D-07 | Minimum supply and seeker launch gate | Marketplace cold-start sequencing and release criteria | Open; discovery OQ6 |
| D-08 | Initial expert acquisition channel | Supply onboarding and operating effort | Open; discovery OQ7 |
| D-09 | Browse account requirement | Conversion, privacy, discovery analytics | Open; discovery OQ10 |
| D-10 | Initial service catalog; one-time vs. recurring | MVP scope, pricing, booking/domain complexity | Include consultations, mock interviews, and resume reviews; recurring mentorship remains deferred |
| D-11 | Review eligibility, moderation, and visibility | Trust, abuse handling, data model, launch operations | Open; not resolved in discovery |
| D-12 | Payment provider and payout model | Checkout, webhook contract, reconciliation, fees, supported geography | Stripe Connect is the preferred candidate, subject to India eligibility/invitation and integration review; assess fallback if unavailable |

## Required decision record

For each item: decision (`Approved`, `Rejected`, or `Deferred`), evidence reviewed, options, rationale, approver/date, impacted artifact links, follow-up owner, and condition for revisiting. The selections above capture the founder's requested design baseline; they do not claim legal, regulatory, or provider approval. Legal or payment-provider questions must be reviewed by qualified owners for the chosen geography; the register itself is not legal advice.
