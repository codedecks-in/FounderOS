# Playbook: Respond to an Incident

**Owner:** Incident lead designated by the team  
**Inputs:** Alert, report, or suspected production impact  
**Outputs:** Containment, recovery, communications, incident record, follow-up actions

## Procedure

1. Acknowledge and assign an incident lead. Open a time-stamped record and set an incident channel appropriate to the organization's approved tools.
2. Triage user impact, affected systems/data, severity, start time, and whether security, privacy, payments, or safety may be involved. State uncertainty clearly.
3. Contain safely: disable affected functionality, revoke credentials, isolate components, or pause processing as warranted. Preserve evidence and avoid destructive investigation.
4. Restore service using the safest known mitigation. Verify recovery with user-facing and system indicators; monitor for recurrence.
5. Communicate status to affected internal owners and, when required, users, providers, regulators, or other parties through the responsible owner and approved process. Do not speculate or expose sensitive data.
6. After stabilization, preserve logs and timeline, determine contributing factors, and distinguish confirmed facts from hypotheses.
7. Hold a blameless review. Create owned, dated actions for prevention, detection, response, and documentation; track them to closure.

## Gate

Escalate suspected data exposure, account compromise, payment fraud, or legal notification requirements immediately to designated security/privacy/legal owners. Do not delay containment while waiting for a complete root cause.
