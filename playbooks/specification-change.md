# Playbook: Change an Approved Specification

**Owner:** Product owner; affected engineering/security owners review  
**Inputs:** Approved artifact, new evidence or constraint, affected requirements  
**Outputs:** Reviewed change record, updated artifacts, impact and re-approval

## Procedure

1. Open a change record describing the trigger, evidence, proposed change, and urgency. Link the original decision and requirements.
2. Identify affected user behavior, APIs, domain rules, data, security/privacy controls, UI, tests, operations, and release plans.
3. Ask relevant artifact owners to assess scope, compatibility, risks, migration, and alternatives. Keep unaffected requirements stable.
4. Product owner accepts, rejects, or defers the proposal. Security, data, or architecture owners review changes in their areas; record dissent and residual risk.
5. Update the source specification first. Mark its version/date and summarize changes. Update dependent artifacts and test traceability.
6. Re-approve downstream implementation tasks against the new version. Pause implementation if the current code plan conflicts with the approved contract.

## Gate

Do not silently change behavior through code. A change is ready when decision ownership, artifact links, impact assessment, acceptance criteria, and required approvals are recorded.
