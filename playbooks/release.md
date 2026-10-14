# Playbook: Prepare and Release

**Owner:** Release owner; human release approver  
**Inputs:** Approved implementation, test and review reports, deployment and rollback details  
**Outputs:** Approved release plan, deployment evidence, post-release review

## Procedure

1. Confirm scope, version, target environment, change owner, and user-visible release notes.
2. Verify required CI, test traceability, security/dependency checks, code review, and migration checks. List accepted risks and confirm an owner.
3. Prepare ordered deployment steps, configuration/secrets, migration strategy, rollout method, health checks, monitoring, and explicit stop conditions.
4. Prepare and, where practical, rehearse rollback or forward-fix. Confirm backups, recovery owner, and data compatibility; rollback code alone may not reverse data changes.
5. Obtain human approval for the target environment. Deploy to staging first when available and run smoke checks.
6. Deploy in the approved window and rollout steps. Monitor agreed indicators and stop/rollback when a trigger is met.
7. Record actual versions, times, migration result, verification, incidents, deviations, and release decision.
8. Schedule a post-release review and feed learnings into product and engineering artifacts.

## Gate

Do not release with missing approval, failed critical checks, unknown migration behavior, no viable recovery plan, or absent monitoring/ownership for material risk.
