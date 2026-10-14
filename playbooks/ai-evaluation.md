# Playbook: Evaluate an AI Feature

**Owner:** AI feature owner; product and security owners approve limits  
**Inputs:** Approved AI feature design, representative evaluation data, safety requirements  
**Outputs:** Versioned evaluation report, regression cases, ship/hold recommendation

## Procedure

1. Confirm the feature has a user-valued reason to use AI, a deterministic alternative assessment, a bounded output contract, and named human escalation/override behavior.
2. Define evaluation dimensions from requirements: task quality, factuality, refusal behavior, harmful output, privacy leakage, prompt injection, robustness, latency, and cost as applicable.
3. Build a representative, permissioned dataset with expected outcomes or scoring guidance. Remove secrets and unnecessary personal data; record sampling limits and known blind spots.
4. Version the dataset, prompt, model/provider configuration, and evaluator. Include adversarial and boundary cases; avoid relying on one aggregate score to hide critical failures.
5. Run evaluations against the proposed change and a baseline. Inspect failures qualitatively, record per-slice results, and add important failures as regression cases.
6. Compare results to pre-approved thresholds and budgets. Product owner accepts user impact; security/privacy owner accepts residual risk; release owner confirms monitoring and rollback.
7. Monitor sampled production outcomes and user reports within approved privacy boundaries. Re-evaluate after prompt, model, retrieval, or policy changes.

## Gate

Hold release for unbounded output, untested sensitive-data exposure, a critical safety failure, failed required threshold, or missing rollback/monitoring. Do not tune the evaluation set after seeing results without versioning and explaining the change.
