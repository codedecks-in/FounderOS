# Workflow

**Document Version:** 1.0

**Status:** Draft

**Owner:** Founder

---

## Purpose

This document defines the standard workflow followed by every project built using FounderOS.

FounderOS follows **Specification-Driven AI Engineering (SDAE)**, where software is developed from approved specifications instead of directly generating code.

The objective is to create a repeatable engineering process that enables solo founders and small teams to build production-grade software with AI.

---

## Workflow Philosophy

FounderOS believes that software development begins with understanding the problem—not writing code.

Every engineering decision should be guided by clear specifications.

The workflow emphasizes:

- Thinking before building
- Specifications before implementation
- Incremental delivery
- Continuous validation
- Reusable engineering knowledge

---

## FounderOS Lifecycle

```text
Idea
   │
   ▼
Market Research
   │
   ▼
Product Discovery
   │
   ▼
Product Requirements (PRD)
   │
   ▼
Architecture Design
   │
   ▼
Domain Modeling
   │
   ▼
Database Design
   │
   ▼
API Specification
   │
   ▼
UI/UX Specification
   │
   ▼
AI Prompt Design
   │
   ▼
Implementation
   │
   ▼
Testing
   │
   ▼
Deployment
   │
   ▼
Growth & Analytics
   │
   ▼
Continuous Improvement
```

Every stage produces an artifact that becomes the input for the next stage.

---

## Stage 1 — Idea

### Goal

Identify a meaningful customer problem.

### Deliverables

- Vision
- Problem Statement
- Initial Product Hypothesis

---

## Stage 2 — Market Research

### Goal

Validate the opportunity before building.

### Activities

- Competitor Analysis
- Customer Research
- Market Sizing
- Pricing Research

### Deliverables

- Research Report
- Opportunity Assessment

---

## Stage 3 — Product Discovery

### Goal

Clearly define the product.

### Deliverables

- Personas
- User Journeys
- Value Proposition
- Success Metrics
- Non-Goals

---

## Stage 4 — Product Requirements (PRD)

### Goal

Translate ideas into engineering requirements.

### Deliverables

- Functional Requirements
- Non-Functional Requirements
- User Stories
- Acceptance Criteria
- Edge Cases

No implementation decisions belong in the PRD.

---

## Stage 5 — Architecture Design

### Goal

Design the system before implementation.

### Deliverables

- High-Level Architecture
- Technology Decisions
- Module Boundaries
- Security Design
- Scalability Considerations
- Architecture Decision Records (ADRs)

---

## Stage 6 — Domain Modeling

### Goal

Model the business domain.

### Deliverables

- Aggregates
- Entities
- Value Objects
- Domain Services
- Repositories
- Bounded Contexts

---

## Stage 7 — Database Design

### Goal

Design a database that supports the domain model.

### Deliverables

- ER Diagram
- Table Definitions
- Relationships
- Index Strategy
- Migration Plan

---

## Stage 8 — API Specification

### Goal

Define contracts before implementation.

### Deliverables

- REST Endpoints
- Request Models
- Response Models
- Error Codes
- Authentication Rules
- Pagination Strategy

---

## Stage 9 — UI/UX Specification

### Goal

Design the complete user experience.

### Deliverables

- Navigation Flow
- Page Specifications
- Component Library
- Responsive Design
- Loading States
- Empty States
- Error States

---

## Stage 10 — AI Prompt Design

### Goal

Create reusable prompts for AI-assisted development.

Every prompt should define:

- Purpose
- Inputs
- Expected Outputs
- Constraints
- Validation Rules
- Example Usage

Prompt libraries should be version-controlled.

---

## Stage 11 — Implementation

### Goal

Generate production-ready software from approved specifications.

### Rules

- Build one feature at a time.
- Keep changes small and reviewable.
- Never bypass approved specifications.
- Every feature includes automated tests.

---

## Stage 12 — Testing

FounderOS follows the Testing Pyramid.

1. Unit Tests
2. Integration Tests
3. End-to-End Tests

Critical user journeys should always include E2E validation.

---

## Stage 13 — Deployment

Every release should include:

- Automated Build
- Security Checks
- Database Migration
- Monitoring
- Rollback Plan
- Release Notes

---

## Stage 14 — Growth & Analytics

Launching is the beginning.

Track:

- User Activation
- Feature Adoption
- Retention
- Conversion
- AI Usage
- Infrastructure Cost

Product decisions should be driven by measurable outcomes.

---

## Stage 15 — Continuous Improvement

Every project should improve FounderOS itself.

Examples:

- Better prompts
- Better templates
- Better playbooks
- Better engineering standards

Knowledge is treated as a reusable engineering asset.

---

## AI Responsibilities

| Tool | Responsibility |
|------|----------------|
| ChatGPT | Product thinking, architecture, reviews |
| Kiro | Specification-driven implementation |
| Cursor | Daily development |
| Claude Code | Large-scale refactoring and optimization |

---

## Exit Criteria

A stage is complete only when:

- Deliverables are complete
- Artifacts are reviewed
- Documentation is committed
- Approval is received

Only then should the project move to the next stage.

---

## Guiding Principle

> Every stage should produce a reusable artifact that accelerates every future project.
