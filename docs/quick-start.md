# FounderOS Quick Start

Use this guide to start a project with the repository's current workflow, templates, and agent instructions. FounderOS is a documentation framework; this process does not scaffold application code.

## 1. Create a project workspace

Create a folder for your product and keep its working artifacts together, for example:

```text
my-product/
└── docs/
    ├── discovery.md
    ├── prd.md
    ├── decisions/
    └── modules/
```

Copy a template from `templates/` into the project workspace before filling it in. Keep the FounderOS repository as the source of reusable guidance; keep project-specific decisions and specifications in the project workspace.

## 2. Start with discovery

Copy `templates/product-discovery-document.md` to `docs/discovery.md`. Record evidence separately from assumptions, define the target user and problem, and make a proceed / pause recommendation. If market evidence is missing, list the research needed rather than presenting guesses as facts.

Use [`agents/product/product-discovery-agent.md`](../agents/product/product-discovery-agent.md) to structure discovery. The founder owns market research for now; the Discovery Agent can organize findings and identify evidence gaps, but it does not replace customer interviews or source verification.

## 3. Write and approve the PRD

When discovery supports proceeding, copy `templates/prd.md` to `docs/prd.md`. Give each requirement an ID and make acceptance criteria observable and testable. Keep product behavior here; defer technology and implementation choices to architecture.

Use [`agents/product/prd-agent.md`](../agents/product/prd-agent.md). The founder reviews and approves the PRD before architecture work starts.

## 4. Design the system and experience

Use the solution, domain, database, API, and security architecture agents for the applicable artifacts. Record material decisions with the ADR structure in the relevant architecture agent or a project-local decision record.

There is not yet a dedicated UI/UX specification agent. Use `templates/ui-ux-specification.md`; the founder and product team own navigation, page behavior, accessibility needs, and interaction states, while the Frontend Module Implementation Agent consumes those decisions and raises missing requirements before implementation. For AI features, use `templates/ai-feature-design.md` to approve behavior, data boundaries, evaluation criteria, and provider constraints before handing implementation to the AI Module Implementation Agent.

## 5. Plan one small increment

Use the Implementation Planning Agent to break approved scope into modules with dependencies, acceptance criteria, risks, and a clear first increment. Do not ask an implementation agent to fill gaps in product decisions by guessing.

## 6. Implement, test, review, release

For one planned module at a time:

1. Give the relevant backend, frontend, or AI implementation agent the approved specifications and the module task.
2. Ask the Testing Agent to derive checks from the requirements and report traceability and defects.
3. Ask the Code Review Agent for an independent review against the approved artifacts.
4. Ask the Release Agent for release and rollback plans. A human approves and performs production release.

Follow the module-level quality gates and stop if required inputs are missing or a change would alter an approved contract. Update the specification through an explicit review before changing implementation scope.

## 7. Learn and update

After release, record outcomes against the discovery metrics, incidents, user feedback, and new assumptions. Feed validated learnings into the next discovery or planning cycle and contribute reusable improvements back to FounderOS.

## Handoff rule

At every stage, pass forward the approved artifact, unresolved questions, assumptions, and explicit approval state. A downstream agent should not treat a draft or an unanswered question as an approved decision.

## Current coverage limits

This quick start uses the current starter template set. Templates and playbooks are working aids; tailor them to project risk and context. Playbooks and a full end-to-end reference project remain to be completed. See the [completion roadmap](completion-roadmap.md) and [agent catalog](agent-catalog.md).
