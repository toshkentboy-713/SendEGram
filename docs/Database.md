# Database Design

**Document ID:** SEG-DB-001

**Project:** SendEGram

**Version:** 1.0

**Status:** Foundation

---

# 1. Purpose

This document defines the logical database model for SendEGram.

The database must support current MVP features while remaining flexible enough for future expansion without major structural changes.

---

# 2. Database Principles

The database must follow these principles:

* Normalize business data where appropriate.
* Preserve complete auditability.
* Never physically delete financial records.
* Support horizontal application scaling.
* Protect sensitive information.
* Maintain referential integrity.

---

# 3. Core Entities

## Users

Stores user identity and profile information.

Fields include:

* User ID
* Phone Number
* First Name
* Last Name
* Date of Birth
* Language
* Status
* Created At
* Updated At

---

## User Devices

Stores trusted devices.

Fields include:

* Device ID
* User ID
* Device Name
* Platform
* Last Login
* Status

---

## User Sessions

Stores active sessions.

Fields include:

* Session ID
* User ID
* Device ID
* Access Token ID
* Refresh Token ID
* Expires At

---

## KYC Records

Stores identity verification information.

Fields include:

* Verification ID
* User ID
* Verification Status
* Provider
* Submitted At
* Approved At

---

## Countries

Stores supported countries.

Fields include:

* Country ID
* ISO Code
* Name
* Status

---

## Currencies

Stores supported currencies.

Fields include:

* Currency ID
* ISO Code
* Symbol
* Decimal Precision

---

## Exchange Rates

Stores exchange rates.

Fields include:

* Rate ID
* Base Currency
* Target Currency
* Buy Rate
* Sell Rate
* Source
* Timestamp

---

## Recipients

Stores frequently used recipients.

Fields include:

* Recipient ID
* User ID
* Full Name
* Country
* Destination Information

---

## Transfers

Stores international transfers.

Fields include:

* Transfer ID
* User ID
* Recipient ID
* Amount
* Currency
* Exchange Rate
* Fee
* Status
* Partner
* Created At

---

## Payments

Stores utility and service payments.

Fields include:

* Payment ID
* User ID
* Service Provider
* Account Number
* Amount
* Status
* Receipt Number

---

## Transactions

Represents the financial ledger for user-visible activity.

Fields include:

* Transaction ID
* Reference Type
* Reference ID
* User ID
* Transaction Type
* Amount
* Currency
* Status
* Created At

Every completed transfer or payment must generate a transaction record.

---

## Receipts

Stores payment and transfer receipts.

Fields include:

* Receipt ID
* Transaction ID
* Receipt Number
* Generated At

---

## Notifications

Stores user notifications.

Fields include:

* Notification ID
* User ID
* Type
* Title
* Body
* Status
* Sent At

---

## AI Insights

Stores generated financial insights.

Fields include:

* Insight ID
* User ID
* Category
* Summary
* Generated At

AI recommendations must remain advisory and must never represent executed actions.

---

## Audit Logs

Stores immutable security and compliance events.

Examples:

* Login
* Logout
* KYC Approved
* Transfer Created
* Payment Completed
* Profile Updated
* Security Changes

Audit records must never be modified or deleted.

---

# 4. Relationships

User

↓

Devices

↓

Sessions

↓

Transfers

↓

Transactions

↓

Receipts

User

↓

Payments

↓

Transactions

User

↓

Notifications

User

↓

AI Insights

User

↓

KYC Records

---

# 5. Soft Delete Policy

Financial data must not be permanently deleted.

Business entities requiring deletion shall use:

* Is Active
* Deleted At
* Deleted By

where applicable.

Audit records are never deleted.

---

# 6. Data Retention

User data retention shall comply with applicable legal and regulatory requirements.

Financial records must be retained according to jurisdiction-specific obligations.

---

# 7. Performance Strategy

Indexes shall exist for:

* User ID
* Phone Number
* Transaction ID
* Transfer Status
* Payment Status
* Created At

Composite indexes shall be introduced based on production query patterns.

---

# 8. Security Requirements

Personally identifiable information must be protected.

Sensitive fields shall be encrypted where appropriate.

Access to financial data must follow least-privilege principles.

---

# 9. Future Entities

Reserved for future releases:

* Wallet Accounts
* Wallet Transactions
* Cards
* Card Tokens
* QR Payments
* Merchants
* Merchant Settlements
* Business Accounts
* Savings Goals
* Investments
* Insurance Policies
* Loyalty & Rewards

The schema must allow these entities to be added without breaking existing relationships.

---

# 10. Database Design Rules

* Every table must use UUID as the primary key.
* Every table must include Created At and Updated At timestamps.
* Financial events are immutable.
* All monetary values must use fixed precision decimal types.
* Foreign key relationships must be explicitly defined.
* Business rules must not rely solely on database constraints.

---

# Revision History

| Version | Date      | Author  | Description             |
| ------- | --------- | ------- | ----------------------- |
| 1.0     | July 2026 | Founder | Initial Database Design |

---

# End of Document

