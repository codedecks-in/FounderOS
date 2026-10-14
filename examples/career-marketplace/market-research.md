# Market Research — Career Marketplace

**Status:** Draft — evidence collection required  
**Owner:** Founder  
**Inputs:** [Product discovery](discovery.md)  
**Feeds into:** Discovery validation and PRD decisions

## Research questions

1. Will credible tech experts join a new marketplace and accept a 15–20% fee in exchange for incremental discovery and booking infrastructure?
2. Which initial buyer segment and service type generates paid bookings: mock interviews, system design, resume reviews, or career coaching?
3. Which launch geography can be served with available payment, support, and compliance capacity?
4. What trust signal is sufficient for a first booking when formal credential verification is out of scope?

## Evidence currently in discovery

The discovery document names Topmate, MentorCruise, ADPList, Calendly + Stripe, Pramp, and Interviewing.io as alternatives, and records product hypotheses and target metrics. It does not include dated source links, customer interview transcripts, competitor pricing captures, or observed booking data. Treat its competitor descriptions and market timing claims as hypotheses until sourced.

## Evidence plan

| Method | Sample / coverage | Questions or measures | Evidence to retain |
|---|---|---|---|
| Expert interviews | 12–15 tech professionals across target segments | Current acquisition, willingness to list, fee sensitivity, availability, trust concerns | Consent-based notes; anonymize quotes |
| Seeker interviews | 12–15 people with a recent interview or career transition need | Current alternatives, urgency, service choice, booking trust, price reaction | Consent-based notes; anonymize quotes |
| Competitor review | Current alternatives in the chosen geography | Current onboarding, services, fees, cancellation, payout, trust signals | Dated URLs and screenshots/notes |
| Concierge booking test | Small manually recruited supply and demand cohort | Conversion from profile view to paid booking; fulfillment and support effort | Funnel counts, issue log, feedback |

## Findings and confidence

No primary research findings have been added yet. Do not convert the hypotheses in `discovery.md` into facts. Record each finding with source/date, sample, limitations, confidence, and the product decision it affects.

## Decision gates

- Confirm a launch geography and payment provider capability before committing to payment implementation.
- Test expert willingness to list and accept the proposed fee before treating supply targets as achievable.
- Validate demand for one initial service type before supporting a broad catalog.
- Have qualified counsel review marketplace, consumer, tax, privacy, and refund obligations for the selected launch geography; this document is not legal advice.

## Founder direction and remaining validation

The founder selected India as the MVP geography and consultations, mock interviews, and resume reviews as the initial catalog. Stripe Connect is the preferred candidate, not an approved provider. Official Stripe guidance currently describes India platform access as invite-only and documents Connect restrictions; validate business eligibility, connected-account type, and the exact funds flow before relying on this integration. Currency and final fee remain unresolved.

## Recommendation

Proceed with customer and competitor research in the India launch context. Keep the product PRD as a draft until payment eligibility, currency, fee, refund policy, and high-risk marketplace assumptions are reviewed by the founder.

## Provider references (checked 2026-10-14)

- [Stripe India marketplace support](https://support.stripe.com/questions/stripe-india-support-for-marketplaces?locale=en-GB)
- [Stripe Connect India onboarding requirements](https://support.stripe.com/questions/onboarding-requirements-for-stripe-connect-in-india)
