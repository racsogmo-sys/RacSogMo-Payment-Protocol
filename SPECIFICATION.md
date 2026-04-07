# RacSogMo Technical Specification: Unified Payment Interface

## 1. Scope
This document defines the technical standards for the **RacSogMo Protocol** regarding multi-rail payment orchestration, including Credit Cards, Regional Digital Wallets (RDW), and Dynamic Virtual Accounts (DVA).

## 2. Multi-Rail Intent Routing
RacSogMo abstracts specific payment brands (e.g., local wallets) into functional **Intents**. AI Agents should use these intents to determine the optimal settlement path:

- **`RDW_PUSH` (Regional Digital Wallet Push):** For mobile-first transactions requiring app-to-app redirection or push notifications.
- **`DVA_SETTLE` (Dynamic Virtual Account):** For B2B or high-value transactions requiring unique bank transfer codes.
- **`CARD_SECURE_V3`:** For high-compliance credit card transactions with dual-layer whitelist verification.

## 3. Implementation Patterns
When an AI Agent receives a `payment_request`, it must query `get_available_payment_rails` to match the `device_type` with the supported `payment_intent`. 

### Example Mapping:
| User Device | Recommended Rail | Backend Protocol |
| :--- | :--- | :--- |
| Mobile | RDW_PUSH | Asynchronous Semantic Callback |
| Desktop | STATIC_QR / CARD | Synchronous Redirect / API |
| IoT / API | DVA_SETTLE | Webhook Notification |

---
© 2026 RacSogMo Standards Group.
