# FounderOS Playbooks

Playbooks turn the workflow and agent handoffs into repeatable project procedures. Adapt the steps to project risk; retain explicit owners, evidence, approvals, and stop conditions.

| Playbook | Use when |
|---|---|
| [Start a project](start-a-project.md) | A new product or major initiative begins |
| [Change an approved specification](specification-change.md) | New evidence or implementation constraints alter approved scope or contracts |
| [Implement a module](implement-a-module.md) | A small, approved feature increment is ready to build |
| [Evaluate an AI feature](ai-evaluation.md) | A product feature uses model-generated or model-ranked behavior |
| [Review security](security-review.md) | A design, dependency, or change affects trust, data, identity, or exposure |
| [Prepare and release](release.md) | A tested change is proposed for a target environment |
| [Respond to an incident](incident-response.md) | A live service has a suspected security, availability, data, or payment issue |
| [Capture post-release learning](post-release-learning.md) | A release or experiment has enough evidence for review |

The career marketplace example has open founder decisions in [its decision register](../examples/career-marketplace/decision-register.md). In particular, the India payment-provider path is conditional and must be verified before implementation or release.

## Shared operating rules

- Name a human owner for product, security, and release decisions.
- Mark artifacts `Draft`, `Reviewed`, or `Approved`; downstream work may rely only on approved inputs.
- Preserve assumptions, evidence, open questions, and decision dates in the project artifacts.
- Stop at a gate when a required input, owner, or approval is missing; record the blocker and next action.
- Keep changes small, traceable to requirements, and reversible where practical.
