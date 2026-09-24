# AI BOS — GAP-001 CONTROLLED DECISION RECORD
## FINAL PRO TARGET SCOPE CONTRACT v1.0
Date: 2026-09-24
Status: CLOSED — DECISION CONTRACT LOCKED
Parent: Q1–Q51 LOCKED

---

## 1. DECISION

GAP-001 is **CLOSED as a scope/design contract**.

Every capability must belong to exactly one controlled class:

- PRO CORE
- PRO OPTIONAL
- FOUNDATION
- MVP BASELINE
- FUTURE
- OUT OF SCOPE
- UNKNOWN / OPEN

No implementation item may enter from vague wording such as “basic automation” or “essential integrations” without decomposition into an explicit capability and scope class.

This closes scope control. It does not claim implementation, testing, provider verification, or production readiness.

## 2. MVP / STARTER

MVP is the minimum commercial subset:

Customer → WhatsApp → AI → factual business answers → human handoff → product/service → cart → checkout → order → payment → verification → PAID → manual fulfillment

plus tenant setup, onboarding, billing/subscription, basic dashboard, usage, audit, observability, and recovery foundations.

Controlled Starter/MVP capabilities include:

- Product Catalog & Price Management
- Simple Service Catalog
- Approved Knowledge / FAQ
- Customer CRM & E.164 Identity
- Conversation Session & State
- Human Handoff State Machine & Requeue
- Order Shopping Cart
- Order Lifecycle
- Manual Payment Confirmation
- Dashboard MVP metrics shell

## 3. PRO TARGET

Pro adds the defined growth/automation layer:

- lead qualification
- follow-up
- abandoned-cart recovery
- customer segmentation
- multiple staff
- operator assignment/routing
- richer workflows
- campaign capabilities subject to communication policy
- advanced analytics
- API/webhook expansion
- additional integrations

The controlled Pro registry includes the corresponding Pro Core/Optional capabilities already defined in the blueprint.

Classification as Pro does **not** mean implementation already exists or has passed testing.

## 4. FOUNDATION

Foundation/control capabilities are not automatically commercial SKUs:

- Subscription Tier Management
- Payment Verification Gates
- Temporal Entitlement & Safe Downgrades
- Usage Metrics Tracking & Aggregation
- Canonical WhatsApp routes
- Owner AI role/data/secret isolation
- Context assembly controls
- Risk classification and approval control
- Workflow/task/event infrastructure
- Incident/degraded-mode reporting
- Notifications
- Audit/hash verification
- Observability
- Backup/PITR
- Multi-tenant isolation
- Privacy/communication opt-out
- Deterministic-first operating modes
- Internal Specialist Agents

## 5. OUT OF PRO TARGET

Current Pro excludes:

- commercial multi-channel rollout beyond WhatsApp
- enterprise-only infrastructure/SLA/security packaging
- white-label/reseller platform
- advanced ERP/POS/accounting/warehouse
- advanced logistics/automatic waybill/automatic fulfillment
- marketplace commerce
- advanced BI/forecasting/business-health intelligence
- global/cross-tenant learning
- unbounded autonomous AI
- unbounded AI-to-AI command chains
- arbitrary AI access to secrets/files/shell/database
- enterprise custom integration as standard Pro

Future preparation does not make a capability current scope.

## 6. SIMPLE SERVICE BOUNDARY

MVP/Pro supports simple services with:

- name
- description
- price
- duration
- active state

Complex booking/appointment, membership, and subscription-service systems require separate change control.

## 7. AUTOMATION BOUNDARY

Every Pro automation follows:

Event/State → Condition → Policy → Authority/Permission → Risk → Workflow → Action → Verification → Audit

Campaign/follow-up automation requires:

- recipient eligibility
- purpose
- tenant scope
- consent/communication policy
- frequency limit
- stop condition
- suppression when human handling/current state makes automation inappropriate

Unlimited autonomous campaign behavior is out of scope.

## 8. ENTITLEMENT BOUNDARY

Deterministic entitlement:

`Subscription State + Plan + Add-ons + Valid Lifecycle State + Policy → Entitlement Resolver → Effective Capability / Limit`

AI never decides entitlement.

Plan changes must not activate capability before verified financial truth, silently delete data on downgrade, mutate running workflow definitions ambiguously, bypass disabled features through another agent/tool, or create silent unlimited overage.

## 9. NON-EQUIVALENCES

Scope classification ≠ implementation status.

Implementation status ≠ test status.

Test status ≠ production readiness.

Foundation ≠ commercial feature.

Pro Core ≠ already implemented.

Future-ready ≠ current scope.

## 10. EXIT CRITERIA

- [x] MVP and Pro distinguished.
- [x] Foundation distinguished from commercial exposure.
- [x] Future scope separated.
- [x] Out-of-scope areas explicit.
- [x] Automation boundary explicit.
- [x] Service complexity boundary explicit.
- [x] Entitlement remains deterministic.
- [x] Vague scope cannot directly enter implementation.
- [x] Unknowns remain visible.

## 11. REMAINING DEPENDENCIES

GAP-001 does not itself close:

1. numeric AI usage quotas and exact throttling matrix;
2. subscription transition table and exact billing lifecycle values;
3. exact pricing/tax/invoice/business billing inputs;
4. detailed capability acceptance evidence;
5. repository implementation evidence;
6. remaining authority/permission details where not explicitly closed;
7. remaining identity, onboarding, retention, operational, integration, recovery, and cost contracts.

These do not reopen GAP-001.

## 12. FINAL STATUS

**GAP-001: CLOSED — DECISION CONTRACT LOCKED**

This is a controlled scope decision, not an implementation or production-readiness claim.

---
## END
