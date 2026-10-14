# Release Plan — Career Marketplace MVP

**Status:** Draft; no release authorized  
**Inputs:** [Implementation plan](implementation-plan.md), test evidence, review, security and provider decisions  
**Feeds into:** Human release approval and post-release learning

## Readiness blockers

- Founder-approved launch geography feasibility, payment provider and funds flow, currency, fee, refunds/cancellation, and expert trust policy. India is the working geography; Stripe Connect remains conditional on invitation/eligibility and the exact integration being supported.
- Completed security/privacy review and qualified review of applicable marketplace obligations.
- Passing tests for slot concurrency, payment idempotency/reconciliation, authorization, and timezone boundaries.
- Support owner and operational process for failed payments, disputes, cancellations, no-shows, and account reports.
- Production monitoring, backups/recovery, secrets management, and rollback rehearsed.

## Proposed staged launch

1. Internal sandbox with test accounts and provider test mode.
2. Invite-only expert cohort; verify profile setup and support workflow.
3. Limited seeker cohort in one approved geography; monitor every payment and booking manually.
4. Expand only after booking completion, support load, payment reconciliation, and satisfaction meet founder-approved thresholds.

Do not enable live payments or public marketplace access until all blockers are resolved and a human approves the release. No production deployment is performed by this document.

## Monitoring and recovery

Track booking attempts/confirmation, payment state mismatches, slot conflicts, provider webhook failures, notification delivery, cancellations/refunds, support incidents, profile-to-booking conversion, and service availability. Define thresholds, on-call ownership, watch period, data recovery targets, and rollback mechanics after provider and hosting choices are approved.

## Post-release review

Use `templates/post-release-learning.md` to compare observed supply, demand, satisfaction, GMV, take rate, and operational burden with the hypotheses in discovery. Feed results into the next product decision; do not scale on vanity counts alone.
