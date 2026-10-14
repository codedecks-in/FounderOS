# FounderOS Completion Roadmap

**Status:** In progress
**Updated:** 2026-10-14

## What “complete” means

FounderOS is a reusable, tool-agnostic engineering operating system that a founder can apply to a real project from discovery through release. Completion means the repository contains a coherent workflow, usable agent instructions, canonical artifact templates, practical playbooks, and at least one end-to-end reference project. It does not require a CLI or a hosted product; the README describes those as future directions.

## Current baseline

- Vision, workflow, principles, and the agent role documents exist.
- The README inventory has been aligned: all seven engineering agent documents exist, and Phase 3 is marked complete.
- `templates/` contains starter templates for discovery, research, PRD, architecture, ADRs, domain, database, API, security, UI/UX, AI design, planning, testing, release, and post-release learning. The career marketplace walkthrough exercises these structures. `playbooks/` contains the initial operating procedures; project use and feedback should refine them.
- `examples/career-marketplace/` now contains linked draft artifacts from discovery and research planning through release planning. It demonstrates the design workflow, not validated demand, implemented software, executed tests, or a production release.
- The workflow and principles call for UI/UX, AI prompt design, testing, deployment, and improvement artifacts. The [agent catalog](agent-catalog.md) now identifies existing owners and gaps for those stages.

## Completion phases

### 1. Align the inventory

- Keep README status consistent with files that exist.
- Publish the agent catalog, with each role's inputs, outputs, handoffs, and quality gate. **Done:** [agent-catalog.md](agent-catalog.md).
- Resolve the scope gap between workflow stages and available agents. **Done:** interim ownership for market research, UI/UX, AI design, and continuous improvement is documented in the agent catalog. Dedicated agent guides are optional follow-up work, not a blocker for this milestone.
- Publish a quick start that applies the framework to a fresh project. **Done:** [quick-start.md](quick-start.md).

**Exit:** Every promised capability is either represented by a maintained artifact or clearly marked out of scope.

**Status: Complete for the current inventory.**

### 2. Add canonical templates

Create fill-in templates for the workflow's core handoffs: discovery, market research, PRD, architecture and ADR, domain model, database design, API, security, UI/UX, AI design, implementation plan, test strategy/report, release/rollback, and post-release learning. **Initial set created** in `templates/`; validate and refine through the reference project.

**Exit:** A new project can produce each required artifact without inventing its structure, and each template identifies its upstream inputs and downstream consumers.

**Status: Initial set complete; validation pending.**

### 3. Add operating playbooks

Document practical procedures for starting a project, changing an approved specification, implementing one module, evaluating AI behavior, reviewing security, shipping a release, handling an incident, and capturing lessons.

**Exit:** Playbooks give actionable steps, responsible roles, required artifacts, and stop/go criteria, and agree with `docs/workflow.md` and `docs/principles.md`.

**Status: Initial set created; review and refinement remain.**

### 4. Complete the reference project

Extend the career marketplace example beyond discovery with linked PRD, architecture, domain/database/API/security/UI artifacts, an implementation plan, validation approach, and release plan. **Draft design set created** in `examples/career-marketplace/`; founder decisions and market evidence remain open. Keep assumptions explicit and cross-reference decisions.

**Exit:** A reader can follow the example through all applicable workflow stages and see how each handoff changes the next artifact.

**Status: Draft design walkthrough complete; validation and implementation remain out of scope for this artifact set.**

### 5. Verify and publish

- Add a contribution guide and a lightweight repository consistency check for links, required template sections, and documented inventory.
- Review terminology, status labels, and cross-document references.
- Publish a quick start that applies the framework to a fresh project. **Done:** [quick-start.md](quick-start.md).

**Exit:** A first-time user can start with the quick start, follow the workflow, and locate the correct role, template, and quality gate at each step.

## Suggested order

Inventory, quick start, initial templates, playbooks, and a draft reference walkthrough are now documented. Continue by resolving reference-project decisions, refining these artifacts from use, and adding consistency checks. This produces a usable framework before investing in CLI automation.

## Non-goals for this completion milestone

- Building a FounderOS SaaS application or CLI.
- Prescribing one cloud, programming language, or AI vendor.
- Claiming that documentation alone guarantees production readiness; teams still apply judgment and verify deliverables in their project context.
