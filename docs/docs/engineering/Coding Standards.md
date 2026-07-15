# Coding Standards

**Document ID:** SEG-ENG-002

**Project:** SendEGram

**Version:** 1.0

**Status:** Approved

---

# 1. Purpose

This document defines coding conventions for the SendEGram project.

Every contributor, including AI coding assistants, must follow these standards.

Consistency is more important than personal preference.

---

# 2. General Principles

* Write code for humans first.
* Readability is more important than cleverness.
* Explicit is better than implicit.
* Small modules are better than large modules.
* Every file should have a single responsibility.
* Prefer simple solutions.

---

# 3. Naming Conventions

## Variables

Use descriptive names.

Good:

```text
userId
paymentAmount
exchangeRate
```

Bad:

```text
x
tmp
value
```

---

## Functions

Functions must describe an action.

Examples:

```text
createTransfer()
calculateFee()
verifyOTP()
sendNotification()
```

Avoid:

```text
doWork()
handle()
process()
```

unless the context is very clear.

---

## Classes / Structs

Use PascalCase.

Examples:

```text
UserService
TransferController
PaymentRepository
ExchangeRateProvider
```

---

## Interfaces

Use descriptive names.

Examples:

```text
TransferProvider
NotificationSender
AuditLogger
```

Avoid unnecessary prefixes such as:

```text
ITransferProvider
```

unless required by the language or existing ecosystem.

---

## Constants

Use UPPER_SNAKE_CASE.

Example:

```text
MAX_LOGIN_ATTEMPTS
JWT_EXPIRATION_MINUTES
```

---

# 4. Folder Naming

Use lowercase with hyphens.

Example:

```text
payment-service
user-profile
partner-integration
```

---

# 5. File Naming

Follow the conventions of the language and framework.

General preference:

```text
transfer_service.go
payment_controller.go
user_repository.go
```

Flutter/Dart:

```text
transfer_screen.dart
auth_provider.dart
user_model.dart
```

---

# 6. Project Layers

Business logic must remain independent.

Recommended flow:

```text
Presentation

↓

Application

↓

Domain

↓

Infrastructure
```

Infrastructure must never contain business rules.

---

# 7. Function Size

Functions should generally remain under **40 lines**.

If a function becomes difficult to understand, split it into smaller functions.

---

# 8. Function Parameters

Prefer a request object when more than four parameters are required.

Good:

```text
CreateTransferRequest
```

Avoid:

```text
createTransfer(
    sender,
    receiver,
    amount,
    currency,
    country,
    ...
)
```

---

# 9. Error Handling

Always return meaningful errors.

Never swallow exceptions.

Never expose internal implementation details.

Example:

Good

```text
Transfer failed.
Please try again.
```

Bad

```text
NullReferenceException at line 381
```

---

# 10. Logging

Every log entry should include:

* Timestamp
* Service
* Request ID
* Severity

Never log:

* Passwords
* PINs
* OTPs
* Tokens
* Personal identity numbers

---

# 11. Comments

Write comments only when necessary.

Explain **why**, not **what**.

Good:

```text
Retry is limited to prevent duplicate financial operations.
```

Bad:

```text
Increment i.
```

---

# 12. TODO Policy

Allowed:

```text
TODO:
```

Only when linked to an issue.

Example:

```text
TODO(SEG-124): Replace temporary exchange rate provider.
```

Never leave anonymous TODOs.

---

# 13. Dependency Rules

High-level modules must not depend directly on low-level implementation.

Depend on abstractions.

---

# 14. API Rules

Controllers should:

* Validate requests
* Authenticate users
* Authorize access
* Call services
* Return responses

Controllers must never contain business logic.

---

# 15. Service Rules

Services contain business rules.

Services must never know:

* HTTP
* UI
* Database implementation details

---

# 16. Repository Rules

Repositories are responsible only for persistence.

They must never contain business rules.

---

# 17. DTO Rules

DTOs transport data.

They must not contain business logic.

---

# 18. Entity Rules

Entities represent business concepts.

They may contain domain behavior but must remain independent of frameworks.

---

# 19. Testing Standards

Every critical business function must have automated tests.

Recommended naming:

```text
shouldCreateTransfer()

shouldRejectInvalidOTP()

shouldCalculateTransferFee()
```

---

# 20. Formatting

All projects must use automatic formatters.

Manual formatting is prohibited.

Examples:

* Go → `gofmt`
* Dart → `dart format`

Formatting rules must never depend on individual developers.

---

# 21. Linting

Linting is mandatory.

Pull Requests with lint errors must not be merged.

---

# 22. Documentation

Every public API must be documented.

Every exported class, function, or interface should include meaningful documentation when required by the language.

---

# 23. Code Review Checklist

Before requesting review:

* Code builds successfully.
* Tests pass.
* Linter passes.
* Formatter applied.
* No secrets committed.
* Documentation updated.
* No unnecessary dependencies introduced.

---

# 24. AI Coding Rules

AI-generated code must:

* Follow this document.
* Never invent business rules.
* Never bypass security checks.
* Never remove validation.
* Never remove audit logging.
* Never skip tests.

---

# 25. Final Principle

The best code is:

* Easy to read.
* Easy to test.
* Easy to change.
* Difficult to misuse.

Consistency across the codebase is more valuable than individual coding preferences.

---

# Revision History

| Version | Date      | Author  | Description              |
| ------- | --------- | ------- | ------------------------ |
| 1.0     | July 2026 | Founder | Initial Coding Standards |

---

# End of Document
