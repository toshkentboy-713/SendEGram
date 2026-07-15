# API Specification

**Document ID:** SEG-API-001

**Project:** SendEGram

**Version:** 1.0

**Status:** Foundation

---

# 1. Purpose

This document defines the public and internal API standards for SendEGram.

The API must be secure, versioned, consistent, and scalable.

---

# 2. API Principles

All APIs must follow these principles:

* RESTful
* Stateless
* Versioned
* Secure by Default
* Consistent Naming
* Predictable Responses
* Idempotent where applicable
* Fully Documented

---

# 3. Base URL

```
https://api.sendegram.com/v1
```

Future versions:

```
/v2
/v3
```

No breaking changes may be introduced inside the same major version.

---

# 4. Authentication

Protected endpoints require authentication.

Authorization:

```
Authorization: Bearer <AccessToken>
```

Access Tokens are short-lived.

Refresh Tokens are used to obtain new Access Tokens.

---

# 5. Standard Response Format

Successful response:

```json
{
  "success": true,
  "data": {},
  "meta": {},
  "requestId": "uuid"
}
```

Error response:

```json
{
  "success": false,
  "error": {
    "code": "TRANSFER_NOT_ALLOWED",
    "message": "Transfer cannot be completed."
  },
  "requestId": "uuid"
}
```

---

# 6. Authentication Endpoints

POST

```
/auth/register
```

POST

```
/auth/login
```

POST

```
/auth/logout
```

POST

```
/auth/refresh
```

POST

```
/auth/verify-otp
```

---

# 7. User Endpoints

GET

```
/users/me
```

PUT

```
/users/me
```

GET

```
/users/devices
```

DELETE

```
/users/devices/{id}
```

---

# 8. KYC Endpoints

POST

```
/kyc/start
```

POST

```
/kyc/upload
```

GET

```
/kyc/status
```

---

# 9. Transfer Endpoints

POST

```
/transfers
```

GET

```
/transfers
```

GET

```
/transfers/{id}
```

GET

```
/transfers/{id}/receipt
```

---

# 10. Payment Endpoints

GET

```
/payments/providers
```

POST

```
/payments
```

GET

```
/payments/history
```

GET

```
/payments/{id}
```

---

# 11. Transaction Endpoints

GET

```
/transactions
```

GET

```
/transactions/{id}
```

GET

```
/transactions/export
```

---

# 12. Notification Endpoints

GET

```
/notifications
```

PUT

```
/notifications/read
```

---

# 13. AI Endpoints

GET

```
/ai/insights
```

GET

```
/ai/recommendations
```

POST

```
/ai/feedback
```

AI endpoints are advisory only.

They must never execute financial operations.

---

# 14. Admin Endpoints

Restricted access.

Examples:

```
/admin/users
```

```
/admin/transfers
```

```
/admin/payments
```

```
/admin/reports
```

```
/admin/audit
```

---

# 15. HTTP Status Codes

200 OK

201 Created

202 Accepted

204 No Content

400 Bad Request

401 Unauthorized

403 Forbidden

404 Not Found

409 Conflict

422 Unprocessable Entity

429 Too Many Requests

500 Internal Server Error

503 Service Unavailable

---

# 16. Pagination

Collection endpoints shall support:

```
page
limit
sort
order
```

Example:

```
GET /transactions?page=1&limit=20
```

---

# 17. Filtering

Supported where applicable.

Examples:

* Status
* Date Range
* Currency
* Country
* Transaction Type

---

# 18. Versioning Policy

Major changes require a new API version.

Existing versions remain supported during the published deprecation period.

---

# 19. Security Requirements

* HTTPS only.
* JWT Access Tokens.
* Refresh Token rotation.
* Rate Limiting.
* Request Validation.
* Input Sanitization.
* Audit Logging.

Sensitive data must never appear in logs.

---

# 20. API Design Rules

* Use nouns instead of verbs.
* Use plural resource names.
* Return consistent response structures.
* Never expose internal database identifiers beyond public UUIDs.
* Never return sensitive information unnecessarily.

---

# 21. Idempotency

Financial operations that may be retried (such as transfer or payment creation) must support idempotency to prevent duplicate processing.

Clients shall provide an `Idempotency-Key` header for these operations.

---

# 22. Observability

Every request shall include:

* Request ID
* Timestamp
* Processing duration

These values support monitoring, debugging, and auditing.

---

# Revision History

| Version | Date      | Author  | Description               |
| ------- | --------- | ------- | ------------------------- |
| 1.0     | July 2026 | Founder | Initial API Specification |

---

# End of Document

