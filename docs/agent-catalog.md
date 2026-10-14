# FounderOS Agent Catalog

This catalog maps the workflow to the agent instructions currently in the repository. “Human owner” means a founder or project team member makes and approves the decision; an AI agent may help prepare the artifact.

| Workflow stage | Current owner / agent | Main handoff | Coverage |
|---|---|---|---|
| Idea and market research | Founder; Product Discovery Agent organizes evidence | Evidence, assumptions, opportunity assessment → discovery | No dedicated research agent; starter template available |
| Product discovery | [Product Discovery Agent](../agents/product/product-discovery-agent.md) | Discovery document → PRD | Agent available |
| Requirements | [PRD Agent](../agents/product/prd-agent.md) | Approved PRD → architecture and planning | Agent and starter template available |
| Solution architecture | [Solution Architecture Agent](../agents/architecture/solution-architecture-agent.md) | System boundaries and decisions → specialist design | Agent available |
| Domain model | [Domain Modeling Agent](../agents/architecture/domain-modeling-agent.md) | Business concepts and rules → database and API | Agent available |
| Database design | [Database Design Agent](../agents/architecture/database-design-agent.md) | Schema and migration strategy → implementation | Agent available |
| API specification | [API Specification Agent](../agents/architecture/api-specification-agent.md) | Contracts → backend, frontend, and tests | Agent available |
| Security architecture | [Security Architecture Agent](../agents/architecture/security-architecture-agent.md) | Threat model and controls → design, implementation, tests, release | Agent available |
| UI/UX specification | Founder / product team; Frontend Module Implementation Agent consumes the approved design | Flows, pages, states, accessibility → frontend implementation | Starter template available; no dedicated specification agent |
| AI behavior and prompt design | Founder / product owner approves behavior; Solution Architecture Agent records system constraints; AI Module Implementation Agent implements | AI contract, data rules, eval criteria → AI implementation | Starter template available; no dedicated AI design agent |
| Implementation planning | [Implementation Planning Agent](../agents/engineering/implementation-planning-agent.md) | Sequenced module plan → implementation | Agent available |
| Backend implementation | [Backend Module Implementation Agent](../agents/engineering/backend-module-implementation-agent.md) | Increment → Testing Agent | Agent available |
| Frontend implementation | [Frontend Module Implementation Agent](../agents/engineering/frontend-module-implementation-agent.md) | Increment → Testing Agent | Agent available; depends on approved UI/UX decisions |
| AI implementation | [AI Module Implementation Agent](../agents/ai/ai-module-implementation-agent.md) | AI module and evaluation evidence → Testing Agent | Agent available; a longer engineering guide also exists at `agents/engineering/ai-module-implementation-agent.md` |
| Testing | [Testing Agent](../agents/engineering/testing-agent.md) | Test evidence and defects → Code Review Agent | Agent available |
| Code review | [Code Review Agent](../agents/engineering/code-review-agent.md) | Review decision and findings → Release Agent | Agent available |
| Release and deployment | [Release Agent](../agents/engineering/release-agent.md) | Release evidence and learnings → team | Agent available; human retains production approval |
| Growth and continuous improvement | Founder / product team, with Release Agent handing off observations | Outcomes and learnings → next discovery cycle | Starter learning template available; no dedicated agent |

## Agent document conventions

The long-form engineering and architecture guides generally include dependencies, a detailed output artifact, quality gates, a definition of done, and a prompt. Some newer concise guides use a shorter structure. Treat the role's explicit inputs and quality gates as the handoff contract, and surface missing inputs before work begins.

## Duplicate AI implementation guides

Two AI implementation guides currently exist: the concise guide in `agents/ai/` and the detailed guide in `agents/engineering/`. They describe the same role at different levels of detail. Use the concise guide as the quick entry point and the engineering guide for its full workflow and output structure until the repository consolidates them.
