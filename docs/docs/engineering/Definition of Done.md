# Definition of Done

**Document ID:** SEG-ENG-004

**Project:** SendEGram

**Version:** 1.0

**Status:** Approved

---

# 1. Purpose

This document defines the minimum conditions required for a task, feature, bug fix, or improvement to be considered complete.

No work is considered "Done" unless all applicable criteria are satisfied.

---

# 2. General Principle

Writing code does not mean the work is complete.

A feature is complete only when it is:

* Correct
* Tested
* Secure
* Reviewed
* Documented
* Deployable

---

# 3. Definition of Ready

Before implementation begins, a task must have:

* A GitHub Issue
* A clear objective
* Acceptance criteria
* Identified dependencies
* Required documentation
* Technical approach (if needed)

If these are missing, implementation must not begin.

---

# 4. Implementation Checklist

The implementation must:

* Follow Coding Standards.
* Follow Development Standards.
* Follow Security requirements.
* Match the approved architecture.
* Avoid unnecessary complexity.
* Avoid duplicated logic.

---

# 5. Code Quality

Before completion:

* Code builds successfully.
* No compiler errors.
* No lint errors.
* Formatter applied.
* No debugging code.
* No commented-out code.
* No unused variables.
* No unused imports.

---

# 6. Testing

All applicable tests must pass.

Minimum expectations:

* Unit tests
* Integration tests (where applicable)
* Manual verification
* Regression checks for affected functionality

Critical financial workflows require automated testing.

---

# 7. Security Checklist

The implementation must verify:

* Authentication
* Authorization
* Input validation
* Output validation
* Error handling
* Audit logging

Sensitive information must never be exposed.

---

# 8. Documentation

Documentation must be updated when applicable.

Examples:

* API changes
* Database changes
* Configuration changes
* User-facing behavior

---

# 9. Code Review

Before merging:

* Self-review completed.
* Pull Request created.
* Review comments addressed.
* Approval received.

AI-generated code follows the same review process.

---

# 10. CI Requirements

The following checks must pass:

* Build
* Formatter
* Linter
* Unit Tests
* Security Scans (when configured)

No failing CI jobs are allowed.

---

# 11. Performance

The implementation must not introduce unnecessary performance regressions.

Performance-critical changes should be benchmarked where appropriate.

---

# 12. Database Changes

If the feature changes the database:

* Migration created.
* Migration tested.
* Rollback considered.
* Documentation updated.

---

# 13. API Changes

If the feature changes an API:

* API documentation updated.
* Request validation implemented.
* Response format verified.
* Backward compatibility considered.

---

# 14. UI Changes

If the feature affects the user interface:

* Responsive layout verified.
* Accessibility considered.
* Error states handled.
* Loading states handled.
* Empty states handled.

---

# 15. Logging

Appropriate logs must exist for:

* Errors
* Security events
* Important business events

Sensitive data must never appear in logs.

---

# 16. Deployment Readiness

The feature must be deployable without manual code modifications.

Environment-specific values must not be hardcoded.

---

# 17. Acceptance Criteria

Every acceptance criterion defined in the GitHub Issue must be satisfied.

Partial completion is not considered Done.

---

# 18. Final Checklist

A task is Done only if:

✅ Code implemented

✅ Tests passed

✅ Linter passed

✅ Formatter applied

✅ Security reviewed

✅ Documentation updated

✅ Pull Request approved

✅ CI passed

✅ Ready for production deployment

---

# 19. AI Definition of Done

When AI contributes code:

* The generated code has been reviewed by a human.
* Business rules are verified.
* Security requirements are verified.
* Tests are executed.
* Documentation is updated.

AI assistance does not replace engineering responsibility.

---

# 20. Final Principle

The goal is not to finish quickly.

The goal is to finish correctly.

Quality is not an optional step.

Quality is part of the definition of Done.

---

# Revision History

| Version | Date      | Author  | Description                |
| ------- | --------- | ------- | -------------------------- |
| 1.0     | July 2026 | Founder | Initial Definition of Done |

---

# End of Document
