# TASK_TEMPLATE.md

# SendEGram AI Task Template

Use this template for every implementation request given to an AI coding assistant.

---

# Task

Provide a short and clear title.

Example:

Implement OTP Authentication

---

# Goal

Describe the business objective.

Example:

Allow users to securely authenticate using phone number verification through One-Time Password (OTP).

---

# Background

Explain why this feature exists.

Reference the relevant product documentation.

Example:

This feature is required by the MVP Scope and Authentication requirements defined in the BRD and SRS.

---

# Documentation

Read before implementation:

* docs/product/BRD.md
* docs/product/SRS.md
* docs/engineering/API.md
* docs/engineering/Architecture.md
* docs/engineering/Security.md
* docs/engineering/Coding Standards.md
* AGENTS.md

Do not begin implementation until these documents have been reviewed.

---

# Scope

Describe exactly what should be implemented.

Include:

* New functionality
* Updated functionality
* Refactoring (if applicable)

Do not implement features outside this scope.

---

# Out of Scope

Clearly list what must NOT be implemented.

Example:

* Social login
* Passkeys
* Email authentication
* Password login

---

# Technical Requirements

Specify technical expectations.

Examples:

* Follow project architecture.
* Follow coding standards.
* Use dependency injection where applicable.
* Keep business logic independent from infrastructure.
* No duplicated code.
* No hardcoded configuration.

---

# Files

List expected files.

Example:

backend/internal/auth/

backend/internal/users/

backend/internal/http/

apps/mobile/lib/features/auth/

Only modify files necessary for this task.

---

# Database Changes

If applicable:

* Migration required?
* New tables?
* New indexes?
* Existing schema updates?

If none:

State:

No database changes required.

---

# API Changes

If applicable:

List:

* New endpoints
* Updated endpoints
* Response changes
* Request validation

If none:

State:

No API changes required.

---

# Security Requirements

Verify:

* Authentication
* Authorization
* Input validation
* Secure error handling
* Audit logging
* Sensitive data protection

Never bypass security requirements.

---

# Testing Requirements

Required tests:

* Unit Tests
* Integration Tests
* API Tests (if applicable)

Critical user flows require automated tests.

---

# Acceptance Criteria

Provide measurable outcomes.

Example:

* User receives OTP.
* OTP can be verified.
* Invalid OTP is rejected.
* JWT tokens are generated.
* Refresh token works.
* Tests pass.

---

# Definition of Done

The task is complete only if:

* Code builds.
* Formatter passes.
* Linter passes.
* Tests pass.
* Documentation updated.
* Security verified.
* Acceptance criteria satisfied.

---

# Deliverables

Return:

1. Summary of changes
2. Files created
3. Files modified
4. Database migrations
5. API changes
6. Tests added
7. Remaining risks
8. Suggested next task

---

# Constraints

Do not:

* Invent business rules.
* Skip validation.
* Skip tests.
* Skip documentation.
* Introduce breaking changes unless explicitly requested.

When requirements are unclear, stop and request clarification.

---

# Quality Checklist

Before finishing, verify:

* Simplicity
* Readability
* Maintainability
* Security
* Performance
* Testability
* Compliance with AGENTS.md

---

# Final Instruction

Do not optimize for writing the most code.

Optimize for delivering the smallest correct, secure, maintainable, and production-ready implementation.
