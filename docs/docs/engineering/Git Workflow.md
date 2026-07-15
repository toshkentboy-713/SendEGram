# Git Workflow

**Document ID:** SEG-ENG-003

**Project:** SendEGram

**Version:** 1.0

**Status:** Approved

---

# 1. Purpose

This document defines the Git workflow for the SendEGram project.

All contributors, including AI coding assistants, must follow this workflow.

---

# 2. Branch Strategy

The repository uses the following long-lived branches:

* `main`
* `develop`

Short-lived branches are created from `develop`.

---

# 3. Branch Responsibilities

## main

* Production-ready code only.
* Protected branch.
* Direct commits are prohibited.

---

## develop

* Integration branch.
* Features are merged here after review.
* Used for testing before release.

---

# 4. Branch Naming

Use lowercase with hyphens.

Feature:

```text
feature/auth-login
feature/payment-history
feature/ai-insights
```

Bug Fix:

```text
fix/duplicate-transfer
fix/profile-update
```

Hotfix:

```text
hotfix/security-patch
```

Documentation:

```text
docs/api-update
docs/security-policy
```

Refactor:

```text
refactor/payment-service
```

Chore:

```text
chore/dependency-update
```

---

# 5. Issue First

Every implementation starts with a GitHub Issue.

Workflow:

Issue

↓

Branch

↓

Implementation

↓

Pull Request

↓

Review

↓

Merge

---

# 6. Commit Convention

Use Conventional Commits.

Examples:

```text
feat(auth): implement OTP verification

fix(payment): prevent duplicate processing

docs(api): update transfer endpoints

refactor(user): simplify profile service

test(auth): add OTP tests

chore(deps): update dependencies
```

---

# 7. Pull Requests

Each Pull Request must:

* Reference an issue.
* Include a clear description.
* Explain why the change is needed.
* List affected modules.
* Pass all CI checks.

---

# 8. Merge Policy

Merge requirements:

* CI passes.
* Code review approved.
* No merge conflicts.
* Documentation updated (if required).

Preferred merge strategy:

**Squash and Merge**

unless preserving commit history provides clear value.

---

# 9. Protected Branch Rules

The following actions are prohibited on `main`:

* Force push
* Direct commits
* Skipping reviews
* Skipping CI

---

# 10. Release Process

Release flow:

```text
feature/*

↓

develop

↓

Release Validation

↓

main

↓

Tag Release
```

Example tag:

```text
v1.0.0
```

Versioning follows Semantic Versioning.

Examples:

```text
v1.0.0
v1.1.0
v1.1.1
v2.0.0
```

---

# 11. Rollback Policy

Every release must be reversible.

Production deployments must support rollback to the previous stable version.

---

# 12. Branch Lifetime

Feature branches should be short-lived.

Recommended lifetime:

* 1–5 working days

Avoid long-running branches whenever possible.

---

# 13. AI Development Workflow

When using AI coding assistants:

1. Read relevant documentation.
2. Create an issue.
3. Create a feature branch.
4. Generate code.
5. Review manually.
6. Run tests.
7. Open Pull Request.

AI-generated code follows the same review process as human-written code.

---

# 14. Git Principles

* Small Pull Requests are preferred.
* Merge frequently.
* Resolve conflicts early.
* Keep history clean.
* Never bypass review.

---

# Revision History

| Version | Date      | Author  | Description          |
| ------- | --------- | ------- | -------------------- |
| 1.0     | July 2026 | Founder | Initial Git Workflow |

---

# End of Document
