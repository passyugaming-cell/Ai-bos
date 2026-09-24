# AI BOS — MASTER CONTROLLED CLOSURE PACK v1.0

## Purpose

Dokumen ini dibuat sebagai **satu paket kerja sekaligus**, bukan pengerjaan GAP satu per satu. Tujuannya adalah mengonsolidasikan seluruh area kontrak/readiness yang masih perlu dikendalikan sebelum implementasi, sambil mempertahankan Q1–Q51 sebagai baseline locked.

**Status dokumen:** CONTROLLED WORKING PACK — bukan klaim bahwa seluruh GAP sudah PASS atau repository sudah production-ready.

---

# 1. HIERARKI SUMBER

Urutan otoritas:

1. Q1–Q51 / Locked Decisions
2. Approved Master Blueprint
3. Master Audit Knowledge Base
4. Build Readiness / controlled GAP contracts
5. Test specifications
6. Repository implementation evidence

Dokumen tingkat bawah tidak boleh diam-diam mengubah keputusan tingkat atas.

Status yang harus dibedakan:

- LOCKED
- DEFINED
- PROPOSED
- OPEN
- UNKNOWN
- CONFLICT
- VERIFIED/PASS
- HISTORICAL

---

# 2. STATUS KONSOLIDASI

| Area | Status kerja | Catatan |
|---|---|---|
| Q1–Q51 | LOCKED | Baseline tidak diubah |
| GAP-002 Authority/Permission | REPAIRED / CONTROLLED | Jangan restart; final evidence/status harus direkonsiliasi |
| GAP-003 State Machine Registry | PASS (historical audit evidence) | Jangan klaim post-merge CI tanpa bukti |
| GAP-004 Source of Truth/Conflict | REPAIRED / CONTROLLED | Jangan restart; final evidence/status harus direkonsiliasi |
| GAP-006 Customer Identity | PASS WITH NON-BLOCKING FOLLOW-UPS | Tidak perlu restart |
| GAP-010 Plan/Entitlement | REPAIRED / CONTROLLED | Jangan restart |
| GAP-001 Pro Target Scope | CONTROLLED / needs final decision-record synchronization | Scope classes sudah ditetapkan dalam reconciliation work |
| GAP-005 Billing/Payment | CORE CONTROLLED; commercial inputs OPEN | Contract core tersedia; detail bisnis tertentu belum locked |
| GAP-007 WhatsApp E2E | DEFINED; provider verification OPEN | Provider-specific assumptions wajib diverifikasi sebelum release-ready |
| GAP-008 READY/ACTIVE Gate | DEFINED | Evidence-based gate |
| GAP-009 Failure/Fallback | DEFINED | Implementation-specific details/evidence masih diperlukan |
| GAP-011 AI Operating Modes | DEFINED | Exact autonomy envelopes remain implementation/policy detail |
| GAP-012 Notification/Follow-up | DEFINED; numeric campaign caps OPEN | D-COMM-02 remains to be finalized |
| GAP-013 Dashboard Acceptance | DEFINED | Screen-level acceptance still needs implementation evidence |
| GAP-014 Audit/Observability | DEFINED | Event implementation/evidence still required |
| GAP-015 Backup/Restore | DEFINED; RPO/RTO OPEN | Infrastructure targets need benchmark/approval |
| GAP-016 Consent/Communication | DEFINED | Legal/jurisdiction details remain inputs |
| GAP-017 Retention/Delete/Export | DEFINED; legal periods OPEN | Exact retention periods are jurisdiction/business inputs |
| GAP-018 Integration Capability | DEFINED | Actual provider list/entitlement requires verification |
| GAP-019 AI Cost/Budget | DEFINED; numeric thresholds OPEN | Benchmark/evidence required |
| D-COMM-01 AI quota mechanism | DECIDED C | Soft Limit + Throttling + Usage Alert/Follow-up; numeric quota not locked |
| D-COMM-02 Campaign limits/caps | PENDING / controlled | Mechanism and numeric values still require Owner decision |
| D-DOC-01 Readiness document status | PENDING / controlled | Historical OPEN labels need synchronization without destroying historical evidence |

---

# 3. GAP-001 — FINAL PRO TARGET SCOPE CONTROL

## Scope classes

Every capability must be assigned to exactly one controlled class:

- PRO CORE
- PRO OPTIONAL
- FOUNDATION
- MVP BASELINE
- FUTURE
- OUT OF SCOPE
- UNKNOWN / OPEN

### Commercial boundary

MVP commercial offering remains:

- Starter
- Pro

Business/Enterprise/white-label are future scope and must not be silently pulled into MVP.

### Critical rule

A foundation capability may be implemented because Pro depends on it without making that foundation itself a separately sold Pro feature.

A future capability does not become Pro merely because another Pro feature references the same infrastructure.

---

# 4. D-COMM-01 — AI USAGE QUOTA

## Decided mechanism

**C = Soft Limit + Throttling + Usage Alert/Follow-up**

This mechanism is controlled.

## Not yet locked

The following must not be treated as canonical numeric values:

- Starter monthly token quota
- Pro monthly token quota
- warning thresholds
- throttling thresholds
- model-routing/degradation matrix
- overage/top-up policy
- exact usage reset rules

### Required implementation principle

Quota/usage exhaustion must never:

- corrupt business truth
- bypass security
- create an undisclosed financial obligation
- silently change subscription/entitlement
- cause uncontrolled autonomous spending

---

# 5. D-COMM-02 — CAMPAIGN / BROADCAST / FOLLOW-UP LIMITS

## Controlled communication gate

`Candidate Communication
→ Recipient/Tenant Resolution
→ Purpose & Message Type
→ Eligibility
→ Consent/Communication Policy
→ Frequency/Rate Limit
→ Suppression/Stop Conditions
→ Authorization & Entitlement
→ Risk
→ Send
→ Delivery Result
→ Audit`

## Required limit dimensions

At minimum the design must be able to represent:

- per-recipient frequency
- tenant campaign volume
- batch size
- follow-up count
- minimum spacing
- quiet hours
- concurrent execution
- retry limit
- duplicate suppression
- opt-out suppression
- human takeover suppression
- state-based suppression
- plan/entitlement restrictions

## Numeric values

**NOT LOCKED.**

Do not invent numeric caps before Owner approval and evidence review.

---

# 6. D-DOC-01 — READINESS DOCUMENT CONTROL

Historical GAP status must be preserved as historical evidence.

Current status must be represented separately.

Recommended convention:

- `HISTORICAL_STATUS` = what the document said at that time
- `CURRENT_CONTROLLED_STATUS` = current audited/reconciled state
- `EVIDENCE_REFERENCE` = source supporting current status
- `OWNER_DECISION` = explicit decision where required

A historical `OPEN` label does not automatically mean a repaired GAP must be reopened.

---

# 7. GAP-005 — BILLING / PAYMENT

## Source-of-truth separation

`Invoice ≠ Payment ≠ Subscription ≠ Entitlement ≠ Usage ≠ Capacity`

## Deterministic path

`Order/Commercial Intent
→ Invoice/Payment Intent
→ Provider Payment
→ Provider Verification/Webhook
→ Reconciliation
→ Internal Payment State
→ Subscription State
→ Entitlement State`

## Payment states

`INITIATED → PENDING → VERIFIED_PAID / FAILED / EXPIRED / CANCELLED / UNKNOWN`

## Locked principles

- Customer claim is not payment proof.
- Provider callback/webhook must be validated.
- Financial side effects must be idempotent.
- `UNKNOWN` requires reconciliation before duplicate payment action.
- Provider failure does not automatically mean internal transaction failure.
- Refund/cancellation is transactional and auditable.
- Upgrade affects entitlement only after verified billing.
- Downgrade preserves data unless separate retention/deletion rules apply.
- Cancellation is not automatic data destruction.

## Commercial inputs still OPEN

- exact subscription transition table
- trial policy
- grace duration
- restriction behavior
- billing/renewal dates
- proration
- refund policy details
- tax/invoice behavior
- currency
- partial payment
- COD if applicable
- manual payment confirmation workflow details
- downgrade effective timing
- over-limit behavior
- add-on lifecycle
- usage reset/rollover/overage
- exact Starter/Pro quotas
- throttling rules

---

# 8. GAP-007 — WHATSAPP E2E

## Canonical path

`Provider Webhook
→ Authenticity/Integrity Validation
→ Tenant Resolution
→ Channel Identity
→ Customer Identity
→ Conversation
→ Intent/Context
→ Deterministic Data Retrieval/AI
→ Policy/Authority
→ Response Generation
→ Channel Adapter
→ Provider
→ Delivery Result
→ Audit`

## Mandatory behavior

- duplicate inbound events are idempotent
- tenant ambiguity blocks processing
- provider retries cannot create duplicate logical response/order/payment
- outbound response remains linked to tenant/customer/conversation
- human handoff suppresses conflicting automation
- `DELIVERY UNKNOWN` is visible and never presented as false success
- AI cannot expose another tenant's context
- provider outage activates defined degraded behavior

## Provider-specific items

Must be verified against current provider documentation before release-ready status.

Open/verify items include:

- exact provider/API contract
- webhook authentication/verification method
- retry semantics
- delivery status semantics
- provider rate limits
- template/message policy
- conversation-window rules
- media handling
- phone-number/business-account mapping
- opt-in requirements
- provider error taxonomy
- number migration/reconnection behavior

Do not hardcode provider assumptions before verification.

---

# 9. GAP-008 — READY / ACTIVE ACCEPTANCE GATE

A tenant becomes READY only when applicable evidence exists for:

- identity/authentication
- tenant scope
- subscription
- entitlement
- business profile
- product/service data
- knowledge/policy
- WhatsApp
- payment integration when commerce is enabled
- webhook/response
- AI scenario evaluation
- deterministic retrieval
- unknown/ambiguous behavior
- handoff
- order/payment when commerce is enabled
- tenant isolation
- critical security
- audit/observability

`ACTIVE` means the tenant can operate safely inside the exact activated capability envelope.

No activation merely because the AI believes onboarding is complete.

---

# 10. GAP-009 — FAILURE / FALLBACK / DEGRADED

## Failure taxonomy

`TEMPORARY | PERMANENT | UNKNOWN | SECURITY | HUMAN_REQUIRED | PARTIAL`

## AI provider failure

1. Retry only when safe/idempotent.
2. Use an approved fallback provider/model only when controlled.
3. Use deterministic response when sufficient.
4. Otherwise bounded unavailable response or handoff.
5. Never fabricate.

## Payment uncertainty

`UNKNOWN → reconcile → retry/stop/manual`

## WhatsApp uncertainty

No duplicate logical message without reconciliation/idempotency.

## Workflow failure

Resume/retry/compensate/stop according to state and side effects. No blind rerun.

## Security failure

Fail closed when the security boundary cannot be established.

## Database/service failure

Preserve persistent workflow state where possible; recovery must verify integrity, tenant scope and security.

---

# 11. GAP-011 — AI OPERATING MODES

## Manual

AI recommends/drafts; human initiates material action.

## Semi-Autonomous

AI executes allowed low-risk actions inside policy/limits; material actions require confirmation/approval according to risk.

## Autonomous

AI executes actions explicitly included in its autonomy envelope, still bounded by:

- authority
- permission
- risk
- budget
- resource
- time
- tools
- stop conditions
- verification

Autonomy never overrides security, tenant isolation, transaction controls or mandatory approval.

## Automatic pause triggers

- scope breach
- permission revocation
- budget exhaustion
- security anomaly
- tenant ambiguity
- critical conflict
- repeated failure
- verification failure
- approval expiry

---

# 12. GAP-012 — NOTIFICATION / FOLLOW-UP

Every automated communication requires:

`Recipient + Tenant + Purpose + Message Type + Eligibility + Timing + Frequency Limit + Stop Conditions + Channel + Authorization/Consent where required`

Stop when:

- opt-out
- resolved/converted
- human takeover
- case closed
- state no longer qualifies
- frequency limit reached
- tenant policy blocks it
- risk/privacy rules prohibit it

Customer-facing automation must not compete with human handling.

This contract must be combined with D-COMM-02 before numeric campaign/follow-up limits are locked.

---

# 13. GAP-013 — DASHBOARD ACCEPTANCE

## Pro dashboard sections

1. Overview
2. WhatsApp/integration health
3. Chats/conversations
4. Handoff/support cases
5. Customers
6. Products/services
7. Orders/cart/payment
8. Business configuration
9. Knowledge/FAQ
10. Automation/workflows
11. Team/admin/assignment
12. Analytics/conversion
13. AI usage/cost
14. Subscription/plan/entitlement
15. Audit/operational status where appropriate

Every screen must specify:

- source
- tenant scope
- permission
- state/refresh behavior
- empty state
- error state
- sensitive-data handling

Advanced BI/forecasting remains outside the Pro target.

---

# 14. GAP-014 — AUDIT / OBSERVABILITY

## Minimum event categories

### Identity/security
`AUTH_LOGIN, AUTH_FAILURE, TENANT_SCOPE_RESOLVED, ACCESS_DENIED, SECURITY_ANOMALY`

### Data
`BUSINESS_UPDATED, PRODUCT_UPDATED, KNOWLEDGE_APPROVED, MEMORY_STATUS_CHANGED`

### Commerce
`CART_CREATED, ORDER_CREATED, ORDER_STATE_CHANGED, PAYMENT_INITIATED, PAYMENT_VERIFIED, PAYMENT_UNKNOWN`

### AI
`AI_REQUEST, AI_DECISION_METADATA, AI_ACTION_REQUESTED, AI_ACTION_BLOCKED, AI_HANDOFF, AI_FALLBACK`

### Workflow
`WORKFLOW_STARTED, WORKFLOW_WAITING, WORKFLOW_FAILED, WORKFLOW_RETRIED, WORKFLOW_COMPLETED`

### Approval
`APPROVAL_REQUESTED, APPROVAL_GRANTED, APPROVAL_REJECTED, APPROVAL_EXPIRED`

### Integration
`INTEGRATION_CONNECTED, INTEGRATION_VERIFIED, WEBHOOK_RECEIVED, WEBHOOK_REJECTED, DELIVERY_RESULT`

### Billing
`SUBSCRIPTION_CHANGED, ENTITLEMENT_CHANGED, USAGE_RECORDED`

Audit metadata must avoid secrets/private chain-of-thought while preserving tenant/actor/correlation/version context.

---

# 15. GAP-015 — BACKUP / RESTORE

Restore is successful only when:

- data integrity verified
- tenant isolation verified
- authorization restored correctly
- state consistency checked
- historical truth preserved
- audit evidence preserved
- external side effects reconciled
- ghost data does not become active again

Service availability is not equivalent to business correctness.

RPO/RTO and backup topology remain infrastructure targets requiring benchmark/approval.

---

# 16. GAP-016 — CONSENT / COMMUNICATION

Communication must distinguish:

- transactional
- service/support
- operational reminder
- marketing/promotional

Where consent/opt-in is required:

- eligibility must be checked
- opt-out must be respected

AI cannot treat a customer message as implicit permanent marketing permission.

Tenant policy cannot override platform/security requirements.

---

# 17. GAP-017 — RETENTION / DELETE / EXPORT

## Data classes

- operational
- transaction/historical
- conversation
- knowledge
- memory
- audit
- security evidence
- billing/usage
- backups

## Rules

- retention differs by domain
- deletion is a controlled lifecycle, not simple DB deletion
- propagation to indexes/cache/memory/knowledge/integrations/exports/backups must be considered
- historical/audit truth is not arbitrarily destroyed
- tenant closure follows controlled retention/deletion lifecycle
- export requires identity, tenant scope, permission and audit
- deleted/expired data cannot remain active AI truth through cache/memory/index

Exact legal retention periods remain jurisdiction/business inputs.

---

# 18. GAP-018 — INTEGRATION CAPABILITY

## Core rule

All integrations use provider-independent adapter/capability boundaries.

## Mandatory first wave

- WhatsApp channel
- one approved payment provider contract

## Candidate Pro integrations

- Google Sheets
- Google Calendar
- Make
- n8n
- Zapier
- API/webhooks

Actual provider list and entitlement must be verified before implementation claims.

## Integration lifecycle

`DRAFT → CONNECTING → VERIFYING → ACTIVE → DEGRADED → DISCONNECTED/REVOKED`

Credential presence alone does not mean ACTIVE.

External input is not automatically instruction, authorization or internal truth.

External timeout/UNKNOWN must be reconciled before duplicate side effect.

---

# 19. GAP-019 — AI COST / BUDGET

## Governance dimensions

- tenant
- agent
- task
- workflow
- request
- model/provider
- time window
- token/usage measurement as supported

## Controls

- soft threshold
- hard threshold
- queue/defer/degrade
- controlled model routing
- retry budget
- workflow budget
- tenant budget
- platform budget

Budget exhaustion must never corrupt business truth or bypass security.

Autonomous operation is never unlimited spending.

Exact money/token thresholds remain commercial/infrastructure configuration and require benchmark/evidence.

---

# 20. CROSS-STAGE INTEGRITY AUDIT

Before coding, verify consistency across:

- Q1–Q51
- Pro scope
- entitlement
- authority
- permission
- source of truth
- identity
- state machines
- billing
- WhatsApp
- readiness
- failure/recovery
- AI modes
- notification
- privacy
- integrations
- cost

## Mandatory checks

### Terminology
No object has conflicting meanings.

### State
Allowed transitions do not silently conflict across contracts.

### Authority
No feature grants an actor more authority than its actor contract.

### Tenant isolation
Every data/request/workflow/tool/event path retains tenant scope.

### AI
AI recommendation never silently becomes authorization or official truth.

### Billing
Entitlement derives from deterministic billing state.

### Recovery
Retry cannot accidentally duplicate financial/customer side effects.

### Scope
Future capability is not silently pulled into Pro.

---

# 21. REPOSITORY / JULES GATE

The design documents being complete does **not** prove repository readiness.

Before coding:

1. Verify repository state.
2. Verify canonical documents are present.
3. Verify AGENTS.md and Jules pre-build instructions.
4. Verify branch/PR safety.
5. Verify test suite exists.
6. Perform repository audit.
7. Jules produces implementation plan.
8. Human Owner reviews/approves the plan.
9. Only then implementation begins.

No claim of production readiness, passing tests, CI, or merged implementation without direct evidence.

---

# 22. WHAT IS STILL AN OWNER DECISION

The controlled pack deliberately leaves these open where the sources do not lock them:

### Commercial
- exact Starter/Pro numeric AI quotas
- throttling thresholds
- campaign/broadcast/follow-up numeric caps
- subscription/trial/grace details
- proration
- refunds
- taxes/invoices/currency
- overage/top-up/rollover
- add-on lifecycle

### Infrastructure
- RPO/RTO
- backup topology
- exact AI provider/model budget thresholds

### Legal/business policy
- exact retention periods
- jurisdiction-specific consent requirements

### Provider verification
- current WhatsApp provider/API constraints
- current payment-provider details
- exact provider retry/rate-limit/message rules

These must be decided, configured, or externally verified before the corresponding release-ready claims are made.

---

# 23. FINAL CONTROLLED WORK ORDER

The project should NOT be treated as restarting.

The consolidated work is:

**A. Reconcile document status**
→ D-DOC-01

**B. Synchronize GAP-001 final scope record**

**C. Close/decide D-COMM-02**
→ mechanism + values + enforcement + alerts + entitlement mapping

**D. Keep repaired GAPs as repaired**
→ GAP-002 / 003 / 004 / 006 / 010
→ do not restart unless new evidence creates a real conflict

**E. Consolidate GAP-005 through GAP-019 contracts**
→ this document is the consolidated working baseline
→ remaining OPEN inputs remain explicitly open

**F. Run cross-stage integrity audit**

**G. Audit repository and Jules governance**

**H. Jules produces pre-build implementation plan**

**I. Human Owner approval**

**J. Only after approval: implementation**

---

# 24. IMPORTANT STATUS DISCLAIMER

This pack is a **controlled consolidation of requirements and known closure work**.

It is NOT evidence that:

- the repository implementation is complete;
- all tests pass;
- all GAPs are PASS;
- production is ready;
- provider limits have been verified;
- numeric commercial limits have been approved.

Those claims require corresponding evidence.

