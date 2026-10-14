# Playbook: Review Security

**Owner:** Security owner / designated engineer  
**Inputs:** Current design or change, data inventory, trust boundaries, threat model  
**Outputs:** Findings with severity, remediation owners, residual-risk decision

## Procedure

1. Set review scope: changed components, data, entry points, integrations, privileges, and environments. Identify whether the review is design-level or code-level.
2. Confirm assets and data classifications. Trace authentication, authorization, secret use, storage, transfer, logs, retention, deletion, and administrative access.
3. Threat model abuse cases: unauthorized access, injection, account takeover, replay, fraud, data leakage, denial of service, supply-chain risk, and unsafe failure behavior as relevant.
4. Verify controls in design and code. Derive tests or evidence for each high-risk control; do not treat a documented control as proof it works.
5. Record findings with impact, likelihood rationale, reproduction/evidence, affected requirements, owner, and remediation date. Separate verified fact from inferred risk.
6. Re-review fixes. A named human risk owner may accept residual risk with scope, rationale, expiry/review date, and compensating controls.

## Gate

Block release for unresolved critical/high findings under project policy, exposed secrets, broken access control, or an unowned material risk. Escalate suspected compromise through incident response rather than routine review.
