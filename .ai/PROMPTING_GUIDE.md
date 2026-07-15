# PROMPTING_GUIDE.md

# SendEGram AI Development Playbook

This guide explains how AI coding assistants should be used throughout the SendEGram project.

It standardizes communication, improves code quality, and reduces unnecessary iterations.

---

# 1. Core Principle

AI is a software engineering assistant.

AI does not replace engineering judgment.

Every AI response must be reviewed by a human before it becomes part of the project.

---

# 2. Choose the Right Mode

## Architecture Mode

Use when:

* Designing new systems
* Making architectural decisions
* Planning integrations
* Defining data models

Expected output:

* Trade-offs
* Diagrams
* Alternatives
* Recommendations

Do not request implementation in this mode.

---

## Design Mode

Use when:

* Planning APIs
* Designing databases
* Defining workflows
* Creating specifications

Expected output:

* Documentation
* Interfaces
* Data contracts
* Technical plans

---

## Implementation Mode

Use when:

* Writing production code
* Refactoring
* Bug fixing
* Creating tests

Always provide:

* Context
* Scope
* Acceptance Criteria

---

## Review Mode

Use when:

* Reviewing Pull Requests
* Finding bugs
* Improving performance
* Improving readability
* Improving security

Expected output:

* Findings
* Risks
* Recommendations

Avoid unnecessary rewrites.

---

## Debug Mode

Use when:

* Errors occur
* Tests fail
* CI fails
* Production issues appear

Provide:

* Logs
* Stack traces
* Expected behavior
* Actual behavior

Never ask AI to guess missing information.

---

# 3. Standard Prompt Structure

Every implementation request should contain:

* Task
* Goal
* Background
* Documentation
* Scope
* Out of Scope
* Technical Requirements
* Acceptance Criteria
* Definition of Done

Refer to:

.ai/TASK_TEMPLATE.md

---

# 4. Provide Context

Always tell AI:

* What feature is being built
* Why it exists
* Which documents apply
* Which files may be modified
* Which files must not be modified

Never assume AI already knows the project.

---

# 5. One Task at a Time

Good:

Implement OTP verification.

Bad:

Implement authentication, payments, AI, notifications, Docker, and CI.

Keep tasks focused.

---

# 6. Request Explanations

When receiving implementation:

Ask AI to explain:

* Design decisions
* Security implications
* Trade-offs
* Potential risks

Understanding is mandatory.

---

# 7. Ask for Alternatives

For important decisions, request multiple approaches.

Example:

"Provide three implementation options with pros and cons."

Do not automatically choose the first solution.

---

# 8. Never Accept Assumptions

If AI invents:

* APIs
* Business rules
* Database schema
* Regulatory requirements

Reject the response.

Project documentation is the only source of truth.

---

# 9. Review Checklist

Before accepting AI-generated code:

* Compiles successfully
* Passes formatter
* Passes linter
* Passes tests
* Matches architecture
* Matches coding standards
* Meets security requirements

---

# 10. Refactoring Rules

Refactoring must:

* Preserve behavior
* Improve readability
* Reduce duplication
* Maintain tests

Never mix large refactoring with unrelated feature work.

---

# 11. Security Questions

For financial features always ask:

* Is authentication correct?
* Is authorization correct?
* Is validation complete?
* Is audit logging present?
* Can this create duplicate transactions?
* Can this expose sensitive information?

---

# 12. Testing Questions

Every implementation should answer:

* What unit tests were added?
* What integration tests were added?
* Which edge cases are covered?
* Which scenarios remain untested?

---

# 13. AI Limitations

AI may:

* Miss edge cases
* Misinterpret requirements
* Produce inefficient code
* Introduce subtle bugs

Always verify important logic independently.

---

# 14. Large Features

Split large work into small milestones.

Example:

Authentication

↓

Phone Registration

↓

OTP Verification

↓

JWT

↓

Refresh Token

↓

Session Management

↓

Biometric Login

Each milestone should be independently testable.

---

# 15. Preferred Workflow

1. Read documentation.
2. Plan implementation.
3. Review the plan.
4. Implement.
5. Add tests.
6. Self-review.
7. Run CI.
8. Open Pull Request.

Do not skip planning.

---

# 16. Communication Style

AI responses should be:

* Concise
* Structured
* Honest
* Technical
* Actionable

Avoid unnecessary repetition.

---

# 17. Continuous Improvement

When AI identifies recurring problems:

* Suggest documentation improvements.
* Suggest architecture improvements.
* Suggest automation opportunities.

Engineering documentation should evolve with the project.

---

# 18. Golden Rules

* Documentation before implementation.
* Security before convenience.
* Tests before merge.
* Small Pull Requests.
* Continuous review.
* Never guess.

---

# Final Principle

The objective is not to generate code quickly.

The objective is to build software that remains reliable, secure, maintainable, and understandable for years.

AI is a productivity multiplier.

Engineering discipline is what turns productivity into a successful product.
