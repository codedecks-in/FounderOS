# Engineering Principles

**Document Version:** 1.0

**Status:** Active

**Owner:** Founder

---

# Purpose

This document defines the engineering principles that every project built using FounderOS must follow.

These principles apply equally to:

- Human engineers
- AI coding assistants
- Code reviews
- Architecture decisions
- Documentation

Engineering discipline should remain consistent regardless of who (or what) writes the code.

---

# Guiding Philosophy

> Build software like a world-class engineering organization—even if you're a solo founder.

Every engineering decision should optimize for:

1. Customer Value
2. Simplicity
3. Maintainability
4. Reliability
5. Developer Experience
6. Scalability

Technology exists to solve product problems—not the other way around.

---

# Principle 1 — Product First

Engineering exists to solve customer problems.

Before implementing any feature, ask:

- Does it solve a real problem?
- Does it create measurable customer value?
- Can it be validated quickly?

Never build technology for its own sake.

---

# Principle 2 — Specification Before Implementation

No production code should be generated until the following artifacts are approved:

- Product Discovery
- Product Requirements (PRD)
- Architecture
- API Specification
- UI Specification (when applicable)

Specifications are the source of truth.

Implementation follows specifications—not the other way around.

---

# Principle 3 — AI as an Engineering Team

FounderOS treats AI as specialized engineering teammates.

## ChatGPT

Responsibilities:

- Product thinking
- Product discovery
- Architecture
- Design reviews
- Documentation

Never responsible for generating an entire production codebase.

---

## Kiro

Responsibilities:

- Specification-driven implementation
- Feature scaffolding
- Test generation
- Incremental feature development

Never responsible for product decisions.

---

## Cursor

Responsibilities:

- Daily development
- Boilerplate
- Pair programming
- Small refactors

---

## Claude Code

Responsibilities:

- Large-scale refactoring
- Architecture improvements
- Performance optimization
- Documentation generation
- Codebase reasoning

---

## Human Engineer

Responsible for:

- Product decisions
- Architecture approval
- Security
- Code review
- Final acceptance

AI assists.

Humans decide.

---

# Principle 4 — Engineering Standards

Every project should follow these engineering standards.

## Keep It Simple

Choose the simplest solution that satisfies today's requirements.

Avoid solving problems that do not yet exist.

---

## Incremental Development

Build software in small, reviewable increments.

Large pull requests increase risk.

---

## Single Responsibility

Every module should have one clear responsibility.

---

## Modular Design

Modules should be loosely coupled and highly cohesive.

---

## Readability First

Code is written for humans.

Computers are the secondary audience.

---

## Explicit Over Clever

Avoid clever implementations.

Prefer obvious code that is easy to maintain.

---

## Composition Over Inheritance

Favor composition unless inheritance clearly improves the design.

---

# Principle 5 — Architecture

FounderOS adopts the following architectural defaults.

## Modular Monolith First

Every new project starts as a modular monolith.

Microservices should only be introduced when justified by:

- Independent deployments
- Multiple engineering teams
- Proven scalability constraints

---

## Domain-Driven Design

Business capabilities define module boundaries.

Technology should never define module boundaries.

---

## Clean Architecture

Separate:

- Domain
- Application
- Infrastructure
- Presentation

Dependencies always point inward.

---

## API First

APIs should be designed before implementation.

Contracts are agreed upon before code generation.

---

## Database as a First-Class Citizen

Database design is architecture—not implementation.

Indexes, constraints, and migrations should be intentional.

---

# Principle 6 — Code Quality

Every feature should meet the following standards.

- Clear naming
- Constructor injection
- Immutable objects where practical
- Explicit validation
- Structured logging
- Meaningful exceptions
- No duplicated business logic
- Automated tests
- Secure by default

---

# Principle 7 — Testing

FounderOS follows the Testing Pyramid.

- Unit Tests
- Integration Tests
- End-to-End Tests

Rules:

- Every business rule has unit tests.
- Every API has integration tests.
- Critical user journeys have E2E tests.

---

# Principle 8 — Documentation

Documentation is part of the product.

Every feature should update documentation when required.

Examples include:

- PRD
- API Specification
- Architecture
- ADR
- README

Undocumented architecture changes are considered incomplete.

---

# Principle 9 — Git Workflow

Recommended branching strategy:

```text
main
│
develop
│
feature/*
```

Branch naming:

```text
feature/resume-upload

feature/mock-interview

bugfix/login

hotfix/payment
```

Every Pull Request should:

- Pass CI
- Include tests
- Update documentation (if applicable)
- Be reviewed before merging

---

# Principle 10 — Architecture Decision Records (ADR)

Every significant engineering decision should be documented.

Each ADR includes:

- Title
- Status
- Context
- Decision
- Alternatives Considered
- Consequences
- Owner
- Date

Examples:

- ADR-001: Modular Monolith
- ADR-002: PostgreSQL
- ADR-003: Spring Boot
- ADR-004: Next.js
- ADR-005: AI Provider Abstraction

---

# Principle 11 — AI Cost Optimization

AI usage is an engineering resource.

Optimize AI usage by:

- Writing reusable specifications
- Keeping prompts modular
- Preferring targeted edits over regeneration
- Versioning prompt libraries
- Reviewing before regenerating
- Tracking AI costs

AI should reduce engineering effort—not increase it.

---

# Definition of Done

A feature is complete only when it includes:

- Approved specification
- Production-ready implementation
- Automated tests
- Documentation
- Logging
- Security validation
- Code review
- Deployment readiness

If any item is missing, the feature is not considered complete.

---

# Engineering Checklist

Before merging any feature, verify:

- Requirements satisfied
- Architecture respected
- Tests passing
- Documentation updated
- No duplicated business logic
- Security reviewed
- Performance acceptable
- AI-generated code reviewed by a human

---

# FounderOS Manifesto

> Build simple software.

> Build maintainable software.

> Build software that solves real customer problems.

> Use AI to accelerate engineering—not replace engineering discipline.

> Every project should leave FounderOS better than it found it.
