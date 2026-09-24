# AI BOS — MASTER LOCK & SESSION HANDOFF REGISTER
Version: 2026-09-22

## GOVERNANCE — LOCKED
- Q1–Q51 is the canonical parent decision baseline.
- Locked Decisions must not be silently changed, superseded, or ignored.
- Changes require explicit audit/change process and Human Owner approval.
- Human/Project Owner has final approval and merge authority.
- Jules = implementation agent; ChatGPT = independent architecture/security reviewer.
- Never merge main automatically.
- Reuse existing subsystems; do not create duplicate/V2 systems without explicit decision.
- UNKNOWN stays UNKNOWN until verified.
- Surface CONFLICT, AMBIGUOUS, MISSING REQUIREMENT, and POTENTIAL ERROR explicitly.
- Stop for P0/P1 blockers, security/tenant-isolation issues, unclear authority/SoT/payment/identity, or missing critical approval/failure paths.

## AI ARCHITECTURE — LOCKED
- Multi-tenant SaaS with Universal Core.
- Universal Core is shared, configuration-driven, channel-independent, deterministic-first, auditable, secure, reusable.
- Human Owner's own business uses Internal AI ecosystem.
- Tenant businesses use Universal Core + Tenant AI + Tenant Specialist AI.
- Internal: Human Owner → Owner AI → Internal Specialist AIs.
- Tenant: Human Tenant/Admin → Tenant AI → Tenant Specialist AIs.
- Owner AI is distinct from Tenant AI and is not the same commercial tenant capability.
- Operating mode controls operational autonomy, not security authority. Autonomous ≠ unlimited authority.
- Authority, permission, entitlement, operating mode, risk, and approval remain separate.

## AI DOMAIN LAYERS
1. Platform Foundation
2. Universal Core / Domain Engine
3. Internal Owner AI
4. Tenant AI
5. Tenant Specialist AI
6. Commercial Feature
A technical foundation/internal AI component is not automatically a commercial SKU.

## D-PROD-01 — CAPABILITY CLASSIFICATION

### MVP / STARTER
001 Product Catalog & Price Management
002 Simple Service Catalog
004 Approved Knowledge / FAQ
005 Customer CRM & E.164 Identity
006 Conversation Session & State
007 Human Handoff State Machine & Requeue
008 Order Shopping Cart
009 ACT-111 Order Lifecycle
011 Manual Payment Confirmation
020 Next.js Dashboard MVP Metrics Shell

### PRO COMMERCIAL
003 Hybrid Product/Service Business Ordering — PRO + candidate Add-on; add-on mechanics not locked
015B Commercial Quota & Overage Policy — PRO CORE; numeric quota/overage not locked
018 Google Calendar Adapter — PRO OPTIONAL
019 Google Sheets Adapter — PRO OPTIONAL
021 Business Health & Financial Analytics API — PRO CORE
022 Basic Event-Triggered Workflow Actions — PRO CORE
023 Advanced Multi-Step Follow-Up Automation — PRO CORE
024 Automated Lead Qualification Workflows — PRO CORE
025 Abandoned Cart Recovery — PRO CORE
026 Customer Behavioral Segmentation — PRO CORE (implementation may be future)
027 Multiple Tenant Admin Roles & Permissions — PRO CORE
028 Human Operator Conversation Routing — PRO CORE
029 Advanced Customer CRM Timeline — PRO CORE

### PLATFORM FOUNDATION / CONTROL
012 Subscription Tier Management
013 Payment Verification Gates — mandatory
014 Temporal Entitlement & Safe Downgrades
015A Usage Metrics Tracking & Aggregation
016 Single Canonical Inbound WhatsApp Route
017 WhatsApp Outbound Sender & Status
030 Owner AI Role/Data Access/Secret Isolation — platform-level
033 Context Assembly 16KB Budget Trimming — AI infrastructure
034 Action Risk Classification & Approval Control Plane — mandatory
035 Workflow Execution & Retry State Machine
036 Task Status & Timestamp Side-Effects
037 Event Bus
038 Incident & Degraded Mode Reporting
039 System Notification Triggers
040 Audit Event Logging & Hash Verification — mandatory
041 Observability & Health Calculator APIs
042 Database Backup/PITR — mandatory
043 Multi-Tenant Data Isolation Enforcement — P0 mandatory security
044 Customer Privacy & Communication Opt-Out — privacy control

### INTERNAL / AI CONTROL
031 Internal Specialist Agents — Internal Owner AI domain; not sold to tenants.
032 Deterministic-First AI Operating Modes — AI Control Architecture; reusable by Tenant AI, Owner AI, future AIs.

## D-PROD-02 — PAYMENT
DECIDED: B — Starter/MVP supports Manual Payment Confirmation only; Midtrans becomes Pro+.
- Manual payment = Starter/MVP.
- Midtrans = Pro+.
- Payment verification remains deterministic/foundation.
- Transfer proof does not automatically establish PAID.
- Exact entitlement exposure remains subject to entitlement matrix.

## D-PROD-03 — HUMAN HANDOFF CAPACITY
DECIDED: C — configurable per operator/tenant.
- Tenant may configure concurrent conversation capacity.
- Platform keeps a technical safety limit.
- At capacity: queue/requeue/routing/fallback; do not force another conversation onto the operator.
- Previous illustrative value “5” is NOT canonical.

## D-COMM-01 — USAGE QUOTA
DECIDED: C — Soft Limit + Throttling + Usage Alert/Follow-up.
- Usage is tracked through foundation usage metrics.
- Near-limit alerts can notify the tenant owner.
- Example 80%/90%/100% thresholds are illustrative only, NOT locked.
- At/after quota, applicable capabilities may be throttled rather than simply hard-stopped.
- Alerts do not themselves authorize billing, payment, upgrade, or financial actions.
- Numeric Starter/Pro quotas are NOT YET LOCKED.
- Exact throttling matrix is NOT YET LOCKED.

## D-COMM-02 — CAMPAIGN LIMITS/CAPS
STATUS: PENDING.
Need decide mechanism and later numeric values for campaign/broadcast/follow-up limits, frequency/caps, and safe communication boundaries.
Any illustrative numbers are NOT canonical.

## D-DOC-01 — READINESS DOCUMENT STATUS
STATUS: PENDING.
Issue: readiness documentation may still show historical GAPs as OPEN after repairs/merges.
This is a document-control/governance issue, not automatically a reason to reopen merged GAPs.
Need decide how to synchronize current status while preserving historical evidence.

## IMPORTANT LOCKED TRANSACTION BEHAVIOR
- Order: CART → PENDING_CONFIRMATION → ORDER_CREATED → PAYMENT_PENDING → PAID → PROCESSING → FULFILLED → COMPLETED.
- Controlled exception states: CANCELLED, PAYMENT_FAILED, EXPIRED, REFUND_PENDING, REFUNDED, RETURN_REQUESTED, RETURNED, EXCHANGE_REQUESTED.
- Checkout pricing deterministic; order price snapshot immutable.
- Payment stays PAYMENT_PENDING until authoritative verification.
- Duplicate payment webhooks must be idempotent/deduplicated.
- Stock must be authoritatively validated/reserved at checkout/commit.
- Customer transfer proof is not automatically payment truth.

## CURRENT DEVELOPMENT / AUDIT CONTEXT
Recent merged repairs include GAP-010, GAP-002, GAP-004, P1 repair, GAP-006, and GAP-003.
GAP-003 was independently audited PASS before merge.
GAP-006 was independently audited PASS WITH NON-BLOCKING FOLLOW-UPS before merge.
Do not claim post-merge CI for a merge commit unless actually verified.
Historical OPEN labels in readiness docs require document-control reconciliation.

## NEXT CONTROLLED WORK
1. Finish D-COMM-02.
2. Finish D-DOC-01.
3. Update controlled GAP-001 decision record / Final PRO Target Scope Contract.
4. Do not start unrelated feature development merely because classifications exist.
5. Before numeric quota/campaign policies, define values, units, enforcement, alerts, and entitlement mapping.
6. Research current WhatsApp API/provider limits and AI API limits plus relevant competitors before locking commercial numbers. External research is evidence, not a canonical project decision.

## NEW-CHAT CONTINUITY
Upload this file first in a new chat, together with the Master Audit Knowledge Base and Master Build Readiness TODO when available.
Tell the new chat:
“This is the latest controlled AI BOS lock/decision handoff. Do not restart the project. Preserve all LOCKED decisions, follow Q1–Q51, and continue from the first PENDING decision. Any conflict must be surfaced, not silently changed.”
