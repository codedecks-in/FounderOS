# FounderOS Completion Roadmap

**Status:** Working definition  
**Updated:** 2026-10-14

## What “complete” means

FounderOS is a reusable, tool-agnostic engineering operating system that a founder can apply to a real project from discovery through release. Completion means the repository contains a coherent workflow, usable agent instructions, canonical artifact templates, practical playbooks, and at least one end-to-end reference project. It does not require a CLI or a hosted product; the README describes those as future directions.

## Current baseline

- Vision, workflow, principles, and the agent role documents exist.
- The README inventory has been aligned: all seven engineering agent documents exist, and Phase 3 is marked complete.
- The documented `templates/` and `playbooks/` directories do not exist yet.
- `examples/career-marketplace/` currently contains a discovery artifact only, so it does not demonstrate the complete workflow.
- The workflow and principles call for UI/UX, AI prompt design, testing, deployment, and improvement artifacts, but the current agent catalog does not cover all those stages explicitly.

## Completion phases

### 1. Align the inventory

- Keep README status consistent with files that exist.
- Publish the agent catalog, with each role's inputs, outputs, handoffs, and quality gate.
- Resolve the scope gap between workflow stages and available agents. Add or explicitly assign ownership for UI/UX specification, market research, and AI prompt design.

**Exit:** Every promised capability is either represented by a maintained artifact or clearly marked out of scope.

### 2. Add canonical templates

Create fill-in templates for the workflow's core handoffs: discovery, market research, PRD, architecture and ADR, domain model, database design, API, security, UI/UX, AI design, implementation plan, test strategy/report, release/rollback, and post-release learning.

**Exit:** A new project can produce each required artifact without inventing its structure, and each template identifies its upstream inputs and downstream consumers.

### 3. Add operating playbooks

Document practical procedures for starting a project, changing an approved specification, implementing one module, evaluating AI behavior, reviewing security, shipping a release, handling an incident, and capturing lessons.

**Exit:** Playbooks give actionable steps, responsible roles, required artifacts, and stop/go criteria, and agree with `docs/workflow.md` and `docs/principles.md`.

### 4. Complete the reference project

Extend the career marketplace example beyond discovery with linked PRD, architecture, domain/database/API/security/UI artifacts, an implementation plan, validation approach, and release plan. Keep assumptions explicit and cross-reference decisions.

**Exit:** A reader can follow the example through all applicable workflow stages and see how each handoff changes the next artifact.

### 5. Verify and publish

- Add a contribution guide and a lightweight repository consistency check for links, required template sections, and documented inventory.
- Review terminology, status labels, and cross-document references.
- Publish a quick start that applies the framework to a fresh project.

**Exit:** A first-time user can start with the quick start, follow the workflow, and locate the correct role, template, and quality gate at each step.

## Suggested order

Finish the inventory and quick start first, then create templates, playbooks, and the complete reference project. Add validation and polish after the structure settles. This produces a usable framework before investing in CLI automation.

## Non-goals for this completion milestone

- Building a FounderOS SaaS application or CLI.
- Prescribing one cloud, programming language, or AI vendor.
- Claiming that documentation alone guarantees production readiness; teams still apply judgment and verify deliverables in their project context.
