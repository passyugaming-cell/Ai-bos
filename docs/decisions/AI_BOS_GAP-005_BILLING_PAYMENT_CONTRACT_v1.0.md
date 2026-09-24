# AI BOS --- GAP-005 BILLING & PAYMENT CONTRACT v1.0

**Status:** CONTROLLED DRAFT FOR OWNER REVIEW\
**Stage:** PRE-BUILD --- CONTRACT CLOSURE

## 1. Purpose

This contract separates and governs:

`Invoice ≠ Payment ≠ Subscription ≠ Entitlement ≠ Usage ≠ Capacity`

It covers both tenant commerce/payment and SaaS subscription billing,
without silently inventing unresolved commercial policies.

## 2. Governing principles

1.  Payment truth is deterministic.
2.  Customer claims, screenshots, transfer proofs, or AI reasoning do
    not by themselves establish `PAID`.
3.  Provider callbacks/webhooks must be validated according to the
    provider contract.
4.  Duplicate financial side effects must be prevented with
    idempotency/deduplication.
5.  `UNKNOWN` is a real state and must not be silently converted to
    `FAILED`.
6.  External provider failure does not automatically mean internal
    transaction failure.
7.  Entitlement changes follow verified billing state, not AI decisions.
8.  Cancellation is not automatic data destruction.
9.  Downgrade preserves data unless a separately authorized
    retention/deletion rule applies.
10. Financial operations remain auditable and deterministic.

## 3. Canonical deterministic path

For a commercial transaction:

`Order / Commercial Intent` → `Invoice / Payment Intent` →
`Provider Payment` → `Provider Verification / Webhook` →
`Reconciliation` → `Internal Payment State` → `Subscription State` →
`Entitlement State`

This path must not be replaced by an AI-only decision.

## 4. Customer commerce payment

### Order/payment boundary

Current locked transaction behavior:

`CART → PENDING_CONFIRMATION → ORDER_CREATED → PAYMENT_PENDING → PAID → PROCESSING → FULFILLED → COMPLETED`

Controlled exceptions:

`CANCELLED` `PAYMENT_FAILED` `EXPIRED` `REFUND_PENDING` `REFUNDED`
`RETURN_REQUESTED` `RETURNED` `EXCHANGE_REQUESTED`

Checkout rules:

-   price is determined deterministically;
-   order price snapshot is immutable after order creation;
-   stock is authoritatively validated/reserved at checkout/commit;
-   payment remains `PAYMENT_PENDING` until authoritative verification;
-   duplicate payment webhooks are idempotent/deduplicated;
-   customer transfer proof is not automatically payment truth.

### Payment state

Canonical payment states from the controlled blueprint:

`INITIATED → PENDING → VERIFIED_PAID / FAILED / EXPIRED / CANCELLED / UNKNOWN`

`UNKNOWN` requires reconciliation before another payment side effect is
attempted.

## 5. Payment method boundary

Current controlled decision:

### Starter / MVP

Manual Payment Confirmation only.

Manual confirmation does **not** mean customer-provided evidence
automatically changes payment state to `PAID`.

### Pro+

Midtrans becomes the approved automated payment-provider path in the
current decision baseline.

Payment verification remains deterministic.

Provider-specific implementation details must follow the provider
adapter contract and must not leak into business-domain logic.

## 6. SaaS billing objects

The controlled model recognizes:

-   Plan
-   PlanFeature
-   PlanLimit
-   Addon
-   TenantAddon
-   Subscription
-   SubscriptionHistory
-   Invoice
-   InvoiceItem
-   Payment
-   Usage
-   Entitlement

These objects must remain semantically distinct.

### Invoice

Represents a billing obligation/record.

It must not be treated as proof that payment has succeeded.

### Payment

Represents the attempt/transaction and its verified outcome.

### Subscription

Represents the tenant's commercial subscription lifecycle.

### Entitlement

Represents the effective capabilities/limits available to the tenant.

### Usage

Represents measured consumption.

### Capacity

Represents available technical/resource capacity.

## 7. Subscription state

The current audit material contains a broader subscription state model:

`ACTIVE` `PAYMENT_PENDING` `GRACE` `RESTRICTED` `SUSPENDED` `EXPIRED`
`ARCHIVED`

A separate canonical transition table is still required before
implementation.

Do not invent durations or transition triggers where the source material
leaves them open.

## 8. Entitlement rule

Effective entitlement must derive from deterministic commercial state:

`Subscription State + Plan + Add-ons + Valid Lifecycle State + Policy + Usage`
→ `Entitlement Resolver` →
`Effective Capability + Effective Limit + Effective Restriction`

AI must never independently grant, remove, or extend entitlement.

## 9. Upgrade / downgrade / cancellation

### Upgrade

A plan upgrade changes entitlement only after verified billing state.

### Downgrade

Downgrade must preserve tenant data unless a separately authorized
retention/deletion rule applies.

The exact effective-time and over-limit behavior remains a commercial
decision requiring closure.

### Cancellation

Cancellation is not equivalent to data deletion.

The exact cancellation timing, access behavior, refund behavior, and
retention period remain open business inputs.

## 10. Failure and reconciliation

### Provider success / internal failure

Do not assume that a provider-side success means the internal operation
is complete.

The system must reconcile provider state with internal state.

### Provider timeout

Represent uncertain outcome as:

`REQUEST → UNKNOWN`

Then:

`UNKNOWN → RECONCILE → VERIFIED OUTCOME → CONTROLLED CONTINUATION`

Do not blindly create a second financial operation.

### Duplicate webhook

Repeated provider events must not create:

-   duplicate payment;
-   duplicate subscription activation;
-   duplicate entitlement extension;
-   duplicate invoice settlement;
-   duplicate refund;
-   duplicate customer-facing financial side effect.

## 11. Refund / cancellation

Refund and cancellation must be:

-   deterministic;
-   authorized;
-   idempotent;
-   auditable;
-   represented by explicit state;
-   reconciled with the provider when external payment infrastructure is
    involved.

Exact refund eligibility, timing and fee treatment remain
business-policy inputs unless separately locked.

## 12. Usage and quota

D-COMM-01 remains:

`Soft Limit + Throttling + Usage Alert/Follow-up`

Current controlled status:

-   numeric Starter quota: OPEN;
-   numeric Pro quota: OPEN;
-   exact threshold percentages: OPEN;
-   exact throttling matrix: OPEN;
-   exact overage/top-up mechanics: OPEN.

No illustrative number becomes canonical through this contract.

## 13. Security / authority boundary

Billing/payment actions must enforce:

`Identity → Tenant Scope → Authorization → Entitlement/Commercial State → Risk/Policy → Deterministic Execution → Verification → Audit`

The AI may:

-   explain billing state;
-   assist with customer communication;
-   recommend an action where permitted;
-   initiate a typed workflow/tool request within authority.

The AI may not:

-   declare payment successful without authoritative evidence;
-   fabricate invoice/payment state;
-   grant entitlement;
-   bypass provider verification;
-   bypass tenant isolation;
-   bypass approval or financial controls;
-   use arbitrary database/API access to alter financial state.

## 14. Audit requirements

Financially meaningful events should preserve, as applicable:

-   tenant;
-   actor/system actor;
-   event type;
-   correlation ID;
-   idempotency key/reference;
-   provider/reference ID where appropriate;
-   prior state;
-   new state;
-   timestamp;
-   contract/version information;
-   verification/reconciliation result.

Secrets and private chain-of-thought must not be stored as audit
evidence.

## 15. Still OPEN --- must not be silently decided

The source material does not yet fully lock:

1.  exact subscription transition table;
2.  trial policy;
3.  exact grace-period duration;
4.  restriction matrix;
5.  exact billing dates/renewal semantics;
6.  proration;
7.  exact refund policy;
8.  tax/invoice policy;
9.  currency policy;
10. partial-payment policy;
11. COD policy;
12. exact manual-payment confirmation workflow;
13. downgrade effective time;
14. behavior when a tenant exceeds the downgraded plan limit;
15. add-on lifecycle;
16. usage reset period;
17. credit rollover;
18. overage/top-up behavior;
19. exact Starter/Pro usage quotas;
20. exact throttling matrix.

These are **OPEN**, not bugs to be guessed away.

## 16. GAP-005 closure assessment

### Resolved / controlled

-   Separation of Invoice / Payment / Subscription / Entitlement / Usage
    / Capacity.
-   Deterministic billing/payment path.
-   Payment verification boundary.
-   Manual-payment boundary for Starter/MVP.
-   Midtrans Pro+ boundary from current decision baseline.
-   `UNKNOWN` and reconciliation behavior.
-   Idempotency/deduplication principle.
-   Upgrade/downgrade/cancellation safety principles.
-   AI authority boundary.

### Remaining closure work

GAP-005 should not be marked fully closed for implementation until the
remaining commercial inputs above are explicitly decided or formally
classified as configurable/business-policy inputs with an implementation
contract.

## 17. Next controlled work

After Owner review of GAP-005:

`GAP-007 — WhatsApp E2E Contract` →
`GAP-008 — READY / ACTIVE Acceptance Gate` →
`GAP-009 — Failure / Degraded Contract` → `Cross-Stage Integrity Audit`
→ `Repository / Jules Pre-Build Readiness`

## 18. Owner approval register

-   [ ] GAP-005 separation of billing objects accepted
-   [ ] deterministic billing/payment path accepted
-   [ ] Starter/MVP manual-payment boundary accepted
-   [ ] Pro+ Midtrans boundary accepted
-   [ ] UNKNOWN/reconciliation rule accepted
-   [ ] unresolved commercial inputs intentionally remain OPEN
-   [ ] GAP-005 allowed to proceed to final status after remaining open
    inputs are classified/decided
