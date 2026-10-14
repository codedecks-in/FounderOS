# Playbook: Implement a Module

**Owner:** Engineering lead / module implementer  
**Inputs:** Approved PRD, architecture/contracts, security requirements, implementation-plan task  
**Outputs:** Small implementation, tests, documentation, handoff evidence

## Procedure

1. Confirm the task has one clear outcome, requirement IDs, acceptance criteria, dependencies, and approved inputs. Record missing decisions and stop if they affect behavior or contracts.
2. Restate module scope, assumptions, files/interfaces likely affected, and validation approach. Have the task owner confirm scope before edits.
3. Implement in small increments. Preserve module boundaries, validate inputs, enforce authorization at the resource boundary, and avoid unrelated refactors.
4. Add tests derived from acceptance criteria and relevant failure/security cases. Keep tests deterministic and avoid live third-party dependencies.
5. Update API, architecture, operational notes, migrations, and user documentation when behavior changes. Record any proposed specification change separately.
6. Hand off the change summary, requirement mapping, test evidence, migrations, risks, and known gaps to the Testing Agent, then the Code Review Agent.

## Gate

Do not call the module complete until the acceptance criteria pass, tests and docs are updated, security implications are reviewed, and independent testing/review findings are resolved or explicitly accepted by the human owner.
