# AGENTS.md

# SendEGram AI Engineering Guide

This document defines the mandatory rules for any AI coding assistant working on the SendEGram project.

These rules are mandatory.

If documentation conflicts with generated assumptions, the documentation always wins.

---

# Project Overview

Project Name:

**SendEGram**

Tagline:

**Your Money. Total Control.**

SendEGram is an AI-powered fintech platform focused on secure international money transfers, bill payments, and intelligent financial management.

Primary users are Uzbek citizens living abroad and their families in Uzbekistan.

---

# Source of Truth

Before making any implementation decisions, read the following documents in order:

1. docs/product/Founder Principles.md
2. docs/product/Vision.md
3. docs/product/Product Definition.md
4. docs/product/MVP Scope.md
5. docs/product/BRD.md
6. docs/product/SRS.md
7. docs/engineering/Architecture.md
8. docs/engineering/Database.md
9. docs/engineering/API.md
10. docs/engineering/Security.md
11. docs/engineering/Development Standards.md
12. docs/engineering/Coding Standards.md
13. docs/engineering/Git Workflow.md
14. docs/engineering/Definition of Done.md
15. docs/engineering/Testing Strategy.md

Never invent business requirements.

---

# Engineering Principles

Always prioritize:

1. Security
2. Correctness
3. Simplicity
4. Maintainability
5. Performance
6. Scalability

---

# Architecture Rules

Respect the project architecture.

Business logic must remain independent from:

* HTTP
* UI
* Database implementation
* Third-party providers

Do not move business rules into controllers or repositories.

---

# Security Rules

Never:

* Skip authentication
* Skip authorization
* Skip validation
* Disable audit logging
* Store secrets in source code
* Log sensitive information

Financial operations must always require explicit user confirmation.

---

# AI Restrictions

Do not:

* Invent APIs
* Invent database tables
* Invent business rules
* Remove validation
* Remove tests
* Remove security checks

If required information is missing, stop and request clarification instead of guessing.

---

# Code Generation Rules

Generated code must:

* Compile successfully
* Follow Coding Standards
* Follow Development Standards
* Be formatted automatically
* Pass linting
* Include appropriate tests
* Be production-ready

---

# Testing Requirements

Every feature must include appropriate tests.

Business logic without tests is considered incomplete unless explicitly approved.

---

# Documentation Rules

Whenever implementation changes:

* Update API documentation if required.
* Update database documentation if required.
* Update changelog if required.
* Keep documentation synchronized with implementation.

Code and documentation must never diverge.

---

# Pull Request Expectations

Before considering work complete:

* Build succeeds
* Tests pass
* Formatter applied
* Linter passes
* Documentation updated
* Security reviewed
* Acceptance criteria satisfied

---

# Task Execution

For every task:

1. Read the relevant documentation.
2. Understand the business objective.
3. Identify affected modules.
4. Implement the smallest correct solution.
5. Add tests.
6. Verify formatting and linting.
7. Verify security implications.
8. Prepare a clean Pull Request.

Never skip steps.

---

# Communication Style

When reporting progress:

* Be concise.
* Explain important technical decisions.
* Mention assumptions explicitly.
* Identify risks.
* Never claim something works unless it has been verified.

---

# Final Principle

Do not optimize for writing more code.

Optimize for delivering secure, maintainable, well-tested software that aligns with the SendEGram architecture and engineering standards.

Quality is always more important than speed.

## CTO tavsiyasi

Bu hujjatni yozganimizdan keyin **Codex bilan ishlash sifati sezilarli darajada yaxshilanadi**, chunki u har safar loyiha qoidalariga tayanadi.

### Endi men yana bitta muhim tavsiya beraman

`PROJECT_CONTEXT.md` yozish o'rniga, men buni **`CLAUDE.md` yoki `CODEX.md`** kabi AI'ga xos fayllarga bo'lib tashlamasdim.

Buning o'rniga bitta umumiy fayl yarating:

```text
.ai/
├── TASK_TEMPLATE.md
├── PROMPTING_GUIDE.md
└── PROJECT_CONTEXT.md
```

Shu uchta fayl va `AGENTS.md` bilan sizda AI-assisted development uchun juda kuchli poydevor bo'ladi.

**Keyingi yozadigan faylimiz `TASK_TEMPLATE.md` bo'lsa, undan keyin Codex'ga beradigan barcha vazifalar bir xil professional formatda bo'ladi va sifat yanada oshadi.**
