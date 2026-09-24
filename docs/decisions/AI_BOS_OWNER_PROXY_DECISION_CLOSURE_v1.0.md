# AI BOS — OWNER PROXY DECISION CLOSURE
Version: 1.0
Status: OWNER-AUTHORIZED WORKING DECISION SET
Purpose: Menutup keputusan desain yang masih membutuhkan keputusan Human Owner, dengan saya bertindak sebagai proxy pengambil keputusan sesuai mandat yang sudah diberikan.

> Prinsip: Q1–Q51 tetap parent canonical. Keputusan di bawah tidak boleh melemahkan security, tenant isolation, deterministic truth, authority, approval, billing verification, atau scope MVP Starter + Pro.

---

# 0. RULE PENGAMBILAN KEPUTUSAN

Jika sebuah nilai dapat diputuskan secara aman dari intent AI BOS, saya tutup.
Jika nilai bergantung pada bukti implementasi, provider contract yang berubah, atau keputusan legal/jurisdiction-specific, saya tidak memalsukan kepastian; saya ubah menjadi target/configuration/evidence requirement.

Status:
- LOCKED = keputusan desain yang sekarang dipakai.
- TARGET = target engineering/operational, belum bukti tercapai.
- CONFIGURABLE = nilai boleh dikonfigurasi dalam batas platform.
- EVIDENCE REQUIRED = keputusan sudah ada, tetapi implementasi/test belum terbukti.
- EXTERNAL VERIFICATION REQUIRED = bergantung provider/hukum aktual.
- FUTURE = sengaja tidak masuk MVP/Pro saat ini.

---

# 1. GAP-001 — PRO TARGET SCOPE
STATUS: CLOSED / LOCKED

Keputusan:
- Commercial launch hanya Starter + Pro.
- Business/Enterprise bukan launch SKU.
- MVP adalah subset komersial minimum dari Starter/Pro, bukan produk terpisah.
- Pro menambah growth + automation.
- Owner AI adalah internal platform capability, bukan fitur tenant Pro.
- Universal Core adalah shared tenant platform, bukan "lapisan Owner AI".
- Foundation tidak otomatis menjadi SKU.

Batas Pro automation:
Event/State → Condition → Policy → Authority/Permission → Risk → Workflow → Action → Verification → Audit.

---

# 2. GAP-002 — ACTOR / AUTHORITY / PERMISSION
STATUS: CLOSED / LOCKED

Keputusan:
1. Account = identitas/login manusia.
2. Tenant = bisnis.
3. Membership = hubungan Account terhadap Tenant.
4. Owner/Admin/Staff adalah role/access relationship.
5. Satu Account boleh memiliki banyak Tenant.
6. Tenant AI hanya tenant-scoped.
7. Owner AI hanya internal platform-owner scope.
8. Delegation tidak menaikkan authority.
9. Tool tidak memiliki authority sendiri; tool hanya interface terkontrol.
10. AI tidak boleh self-authorize.
11. Customer statement bukan authorization dan bukan transaction truth.
12. HIGH action memerlukan approval sesuai policy.
13. CRITICAL action memerlukan Human Owner kecuali exact safe delegation telah diotorisasi.
14. Cross-tenant access selalu fail-closed jika scope tidak dapat dibuktikan.

Permission ≠ Authority ≠ Approval ≠ Entitlement ≠ Operating Mode.

---

# 3. GAP-003 — STATE MACHINE / SUBSCRIPTION
STATUS: CLOSED / LOCKED FOR DESIGN

## Subscription canonical states
PENDING
→ ACTIVE
→ PAYMENT_PENDING
→ GRACE
→ RESTRICTED
→ SUSPENDED
→ CANCELLED
→ EXPIRED
→ ARCHIVED

## Transition rules
- PENDING → ACTIVE hanya setelah payment/activation condition authoritative.
- ACTIVE → PAYMENT_PENDING saat renewal/payment obligation belum verified.
- PAYMENT_PENDING → ACTIVE setelah verified successful payment.
- PAYMENT_PENDING → GRACE saat payment deadline lewat tetapi grace masih berlaku.
- GRACE → ACTIVE setelah verified payment.
- GRACE → RESTRICTED saat grace berakhir.
- RESTRICTED → ACTIVE hanya setelah verified payment/valid restoration.
- RESTRICTED → SUSPENDED jika restriction threshold/policy terpenuhi.
- ACTIVE → CANCELLED hanya melalui valid cancellation request/process.
- CANCELLED → EXPIRED setelah service period berakhir.
- EXPIRED → ARCHIVED setelah retention lifecycle.
- SUSPENDED → ACTIVE tidak boleh terjadi hanya karena AI reasoning; harus ada authoritative restoration.
- No state transition may silently delete tenant data.

## Default commercial timing
- Billing cycle: monthly.
- Renewal anchor: subscription activation/renewal timestamp.
- Grace period: 3 calendar days after failed/unpaid renewal.
- During GRACE: essential access remains available; new high-cost/non-essential automation is restricted.
- RESTRICTED: customer-facing essential operations remain bounded; Pro growth automation and non-essential background jobs are disabled/deferred.
- SUSPENDED: transactional data retained; active customer automation stopped; dashboard/billing access retained where possible.
- Cancellation: access continues until paid-through period ends unless immediate suspension is explicitly requested/required.
- No automatic data destruction on cancellation.

These are AI BOS commercial defaults and can be changed through versioned policy/configuration.

---

# 4. GAP-004 — SOURCE OF TRUTH / CONFLICT
STATUS: CLOSED / LOCKED

Authoritative truth:
Account/Tenant → identity/config domain
Business/Product/Price/Stock → tenant business domains
Customer → customer domain
Conversation → conversation system
Cart → cart domain
Order → order domain
Payment → billing + provider verification/reconciliation
Subscription → billing/subscription domain
Entitlement → entitlement resolver
Knowledge → approved knowledge lifecycle
Memory → memory lifecycle
Workflow/Task → execution systems
Audit → immutable/auditable audit system

Conflict:
classify → identify authority → refresh current state/version → re-evaluate → reconcile/escalate → audit.

Never silently overwrite.

---

# 5. GAP-005 — BILLING / COMMERCIAL INPUTS
STATUS: CLOSED / LOCKED FOR CURRENT MVP TARGET

## Launch prices
- Starter: Rp299.000/month
- Pro: Rp799.000/month
- No Business/Enterprise launch pricing.

These are AI BOS subscription prices, not claims about provider fees.

## Billing
- Monthly recurring billing.
- No mandatory setup fee for self-service MVP.
- One active commercial subscription per tenant.
- Upgrade: new entitlement activates only after verified payment.
- Downgrade: effective at next renewal by default; existing data preserved.
- Immediate downgrade is allowed only through an explicit controlled policy.
- No automatic paid overage unless separately enabled and explicitly consented.
- MVP overage behavior: throttle/block according to entitlement contract, never silently bill.

## Proration
- Default: no mid-cycle proration in MVP.
- Upgrade mid-cycle: payment starts/charges the new plan under the selected provider flow; entitlement change only after verification.
- Downgrade: next renewal.
- If provider requires a different billing mechanism, adapter maps it without changing internal truth rules.

## Refund
- Refund is a separate transaction/state, never an automatic entitlement shortcut.
- Verified refund request → REFUND_PENDING → provider/result reconciliation → REFUNDED or exception.
- Subscription cancellation and refund are separate decisions.

## Tax/invoice/currency
- Internal commercial currency: IDR.
- Displayed prices are gross customer-facing prices unless a later approved tax policy says otherwise.
- Invoice must record subtotal, applicable tax, total, currency, billing period, tenant, payment status and provider reference.
- Exact tax treatment/rate remains jurisdiction/accounting configuration and must be verified before production billing claims.

---

# 6. D-COMM-01 — AI USAGE QUOTA
STATUS: CLOSED / LOCKED FOR MVP TARGET

## Monthly quota
Starter:
- 5,000,000 input tokens/month
- 1,000,000 output tokens/month

Pro:
- 20,000,000 input tokens/month
- 4,000,000 output tokens/month

Input and output are metered separately. Provider-specific token accounting must be normalized into the AI BOS usage schema where possible.

## Threshold behavior
- 80%: informational usage alert.
- 90%: warning + owner alert.
- 95%: throttle expensive/background AI work.
- 100%: block new non-essential AI work and continue only explicitly protected/essential operations within safety policy.
- No automatic paid overage.
- Existing critical deterministic business operations must not be corrupted by quota exhaustion.
- Usage counter resets according to the monthly subscription usage window.

## Priority under quota pressure
1. Security/identity
2. Payment/status verification
3. Active customer service needed for current conversation
4. Order/checkout deterministic operations
5. Human handoff
6. Essential workflow continuation
7. Analytics/background AI
8. Campaign generation/recommendation
9. Non-essential enrichment

AI quota never overrides provider rate limits, platform safety or tenant policy.

---

# 7. D-COMM-02 — CAMPAIGN / BROADCAST / FOLLOW-UP
STATUS: CLOSED / LOCKED

Starter:
- Marketing campaign: disabled.
- Marketing broadcast: disabled.
- Marketing automated follow-up: disabled.
- Transactional/service communication remains available within policy.

Pro:
- 1,000 delivered marketing messages / rolling 30 days / tenant.
- 250 unique marketing recipients / rolling 24h / tenant.
- 250 recipients / broadcast execution.
- 2 broadcast executions / rolling 7 days / tenant.
- 2 active marketing campaigns / tenant.
- 1 execution / campaign / rolling 24h.
- 250 recipients / campaign execution.
- 3 delivered marketing messages / recipient / rolling 30 days.
- Minimum 72h between delivered marketing messages to same recipient.
- 2 marketing follow-ups / recipient / rolling 30 days.
- 2 abandoned-cart follow-ups / cart/customer sequence.
- Quiet hours: 21:00–08:00 recipient-local time.
- After 2 consecutive marketing messages without qualifying engagement: suppress marketing for 30 days.
- Explicit opt-out = immediate suppression.
- Re-subscribe requires new explicit opt-in.
- Marketing cannot be disguised as utility/service.
- Cap reached = block/suppress, not silent queueing.
- UNKNOWN delivery requires reconciliation before retry.
- Provider/law limit overrides AI BOS internal ceiling.

Effective limit:
MIN(law, provider, AI BOS, tenant policy, campaign config).

---

# 8. GAP-006 — CUSTOMER IDENTITY
STATUS: CLOSED / LOCKED

Canonical:
Account → Tenant → Channel Identity → Contact → Customer → Conversation → Cart → Order.

Rules:
- WhatsApp number is channel identity, not universal authorization.
- Identity match must occur inside tenant scope.
- Ambiguous match never silently selects another customer.
- Merge requires controlled process and audit preservation.
- Shared/untrusted identifiers cannot expose another customer's order.
- Future channels attach to the same tenant-scoped identity model.

---

# 9. GAP-007 — WHATSAPP E2E
STATUS: DESIGN CLOSED / EXTERNAL VERIFICATION REQUIRED

Canonical route:
Provider Webhook
→ Authenticity/Integrity Validation
→ Tenant Resolution
→ Channel Identity
→ Customer Identity
→ Conversation
→ Context/Deterministic Data
→ AI/Policy/Authority
→ Response
→ Channel Adapter
→ Provider
→ Delivery Result
→ Audit.

Rules:
- inbound duplicate idempotent;
- tenant ambiguity blocks;
- outbound logical message idempotent;
- delivery UNKNOWN is not SUCCESS;
- human takeover suppresses conflicting automation;
- provider outage enters degraded mode;
- current provider requirements must be verified before release.

---

# 10. GAP-008 — READY / ACTIVE
STATUS: CLOSED / LOCKED

Tenant READY requires applicable evidence for:
identity, tenant scope, subscription, entitlement, business data, knowledge/policy, WhatsApp, payment integration when commerce enabled, webhook test, AI evaluation, deterministic retrieval, ambiguity handling, handoff, commerce test, tenant isolation, critical security, audit/observability.

ACTIVE = READY + operating only inside the activated capability envelope.

No "READY" based on documentation alone.

---

# 11. GAP-009 — FAILURE / FALLBACK
STATUS: CLOSED / LOCKED

Failure classes:
TEMPORARY / PERMANENT / UNKNOWN / SECURITY / HUMAN_REQUIRED / PARTIAL.

Rules:
- Retry only when safe/idempotent.
- UNKNOWN requires reconciliation.
- Payment UNKNOWN never becomes SUCCESS by timeout assumption.
- WhatsApp UNKNOWN never creates duplicate logical send.
- Workflow resumes from durable state/checkpoint.
- Security boundary failure = fail closed.
- Provider fallback requires pre-approved provider/model and preserves policy/authority.
- Never fabricate unavailable data.

---

# 12. GAP-011 — AI OPERATING MODE
STATUS: CLOSED / LOCKED

Manual:
AI recommends/drafts; human initiates material action.

Semi-Autonomous:
AI may execute explicitly permitted low-risk actions; material actions require confirmation/approval.

Autonomous:
AI may execute only actions explicitly included in its autonomy envelope and still remains bounded by authority, permission, risk, budget, tools, time, stop conditions and verification.

Automatic pause:
scope breach, permission revocation, budget exhaustion, security anomaly, tenant ambiguity, critical conflict, repeated failure, verification failure, approval expiry.

Autonomous ≠ unlimited.

---

# 13. GAP-012 — NOTIFICATION / FOLLOW-UP
STATUS: CLOSED / LOCKED

Every automated message requires:
recipient + tenant + purpose + type + eligibility + timing + frequency + stop conditions + channel + authorization/consent where required.

Stop immediately when:
opt-out, conversion/resolution, human takeover, closed case, state invalid, frequency cap, tenant block, privacy/risk prohibition.

---

# 14. GAP-013 — DASHBOARD MVP
STATUS: CLOSED / LOCKED

Starter MVP dashboard:
1. Overview
2. WhatsApp/integration status
3. Conversations
4. Customers
5. Products/services
6. Orders/cart/payment
7. Business settings
8. Knowledge/FAQ
9. Subscription/usage
10. Basic metrics
11. Human handoff

Pro adds:
automation/workflows, team/admin, assignment, conversion analytics, AI usage/cost, richer analytics, integrations.

Advanced BI/forecasting remains outside current Pro target.

---

# 15. GAP-014 — AUDIT / OBSERVABILITY
STATUS: CLOSED / LOCKED

Audit minimum:
WHO, WHAT, WHEN, TENANT, PREVIOUS STATE, NEW STATE, WHY, SOURCE, APPROVAL, RESULT, CORRELATION ID, VERSION.

Never log raw secrets or private chain-of-thought.

---

# 16. GAP-015 — BACKUP / RESTORE
STATUS: CLOSED AS TARGET / IMPLEMENTATION EVIDENCE REQUIRED

MVP target:
- PITR-capable database where infrastructure supports it.
- Backup cadence: at least daily full/snapshot baseline.
- PITR target window: 7 days.
- RPO target: ≤ 24h for baseline MVP; ≤ 1h for PITR-protected critical datastore.
- RTO target: ≤ 4h for baseline MVP.
- Restore drill: quarterly at minimum.
- Restore must verify data integrity, tenant isolation, authorization, state consistency, audit preservation, external side-effect reconciliation and no ghost data.

These are engineering targets, not claims that the current repository/infrastructure already achieves them.

---

# 17. GAP-016 — CONSENT / COMMUNICATION
STATUS: CLOSED / LOCKED

Communication classes:
TRANSACTIONAL / SERVICE / OPERATIONAL / MARKETING / AUTHENTICATION.

Marketing requires explicit category-specific opt-in.
Opt-out is authoritative immediately.
Silence, purchase or previous engagement does not create permanent marketing consent.
Tenant policy cannot weaken platform/provider/legal requirements.

---

# 18. GAP-017 — RETENTION / DELETE / EXPORT
STATUS: CONTRACT CLOSED / LEGAL VALUES EXTERNAL

Rules:
- Operational, transaction, conversation, knowledge, memory, audit, security, billing/usage and backup data have distinct lifecycle policies.
- Deletion is controlled lifecycle, not raw database deletion.
- Delete propagates to cache/index/memory/knowledge/integrations/exports where applicable.
- Historical/audit evidence is preserved where required.
- Export requires identity + tenant scope + permission + audit.
- Closed tenant data is not immediately destroyed.
- Backup retention follows infrastructure policy and legal obligations.
- Exact statutory retention periods are jurisdiction/accounting/legal configuration, not invented by AI BOS.

Default product retention target:
- active tenant operational data: while subscription/lifecycle permits;
- cancelled tenant: 30-day recovery window;
- after recovery window: controlled deletion/anonymization process, except records required for billing, legal, fraud/security and audit;
- backups age out according to backup retention policy.

---

# 19. GAP-018 — INTEGRATION CAPABILITY
STATUS: CLOSED / LOCKED FOR MVP/PRO BOUNDARY

MVP mandatory:
- WhatsApp
- one approved payment provider contract.

Pro candidate:
- Google Sheets
- Google Calendar
- API/webhooks.

Make/n8n/Zapier remain future/optional integration candidates, not guaranteed launch features.

Credential states:
DRAFT → CONNECTING → VERIFYING → ACTIVE → DEGRADED → DISCONNECTED/REVOKED.

Credential existence ≠ integration ACTIVE.

---

# 20. GAP-019 — AI COST / BUDGET
STATUS: CLOSED / LOCKED AS CONTROL CONTRACT

Cost dimensions:
tenant, agent, task, workflow, request, model/provider, time window, usage unit.

Controls:
- soft threshold
- hard threshold
- queue/defer/degrade
- approved model routing
- retry budget
- workflow budget
- tenant budget
- platform budget.

Default policy:
- No autonomous AI action may create an unbounded financial obligation.
- AI spend must be attributable.
- Provider cost is recorded separately from customer subscription revenue.
- Failed/unknown provider calls are not silently counted as successful business actions.
- Budget exhaustion causes bounded degradation, not security bypass.

Exact provider cost tables remain external/configurable because model/provider prices change.

---

# 21. ACCOUNT / IDENTITY / RECOVERY
STATUS: CLOSED / LOCKED

- Account creation: Dashboard or WhatsApp.
- Existing Account + WhatsApp requires verified linking.
- WhatsApp number may differ from Account phone.
- One WhatsApp Business identity may be used by multiple authorized users.
- Password/account recovery must use verified recovery factors.
- WhatsApp possession alone cannot recover another user's account unless explicitly linked through a verified account-linking flow.
- Recovery of tenant ownership requires stronger verification than normal staff access.
- Last-owner removal is blocked until another authorized owner exists or controlled platform recovery is completed.
- Recovery events are audited.

---

# 22. ACTIVE TENANT UX
STATUS: CLOSED / LOCKED

Default:
- After login, if one active tenant: enter it.
- If multiple tenants: show explicit tenant selector.
- Preserve last-used tenant only as convenience; always revalidate authorization.
- No tenant context is inferred solely from conversation text.
- Tenant switch invalidates/rebuilds tenant-scoped context and pending action authority.
- Cross-tenant pending actions are never carried over automatically.

---

# 23. BUSINESS TYPE / ONBOARDING
STATUS: CLOSED FOR MVP

MVP supported archetypes:
1. Retail/product seller
2. Food & beverage
3. Fashion/apparel
4. Simple service business
5. Small agency/consultancy

Common required onboarding:
business identity, contact, operating hours, products/services, prices, stock where applicable, FAQ/policy, payment method, WhatsApp, communication policy, staff/handoff.

Adaptive onboarding:
ask only requirements needed for the selected business archetype/capability.

Unsupported/complex domains are allowed to stop at limited readiness rather than pretending full support.

---

# 24. ONBOARDING INTERRUPTION / RESUME
STATUS: CLOSED / LOCKED

Onboarding is durable and resumable.

Every requirement has:
NOT_STARTED / IN_PROGRESS / NEEDS_REVIEW / COMPLETE / BLOCKED.

Resume:
- return to first unresolved requirement;
- preserve verified data;
- never silently overwrite completed data;
- revalidate stale external integrations before READY.

---

# 25. READY PER CAPABILITY
STATUS: CLOSED / LOCKED

READY is not one global boolean.

Use capability readiness:
- CORE_READY
- WHATSAPP_READY
- COMMERCE_READY
- PAYMENT_READY
- AI_READY
- AUTOMATION_READY
- MARKETING_READY

Tenant ACTIVE capability set = intersection of:
subscription + entitlement + readiness + policy + integration health.

---

# 26. CONVERSATION CONCURRENCY
STATUS: CLOSED / LOCKED

- One conversation has one authoritative current state.
- Inbound messages are sequenced/idempotent.
- Concurrent AI/workflow actions require version/checkpoint validation.
- Stale mutation fails/reloads rather than overwriting newer state.
- Human takeover has precedence over conflicting queued customer-facing automation.

---

# 27. HUMAN HANDOFF RACE CONDITION
STATUS: CLOSED / LOCKED

When human takeover becomes ACTIVE:
- queued AI customer-facing actions are cancelled/suppressed where possible;
- workflow checks handoff state before every material send;
- already-sent messages remain audit truth;
- after resolution, automation may resume only if the triggering state still qualifies.

---

# 28. CUSTOMER REQUEST IDEMPOTENCY
STATUS: CLOSED / LOCKED

Customer requests that can create side effects require an idempotency key derived from stable request/event identity.

Examples:
checkout, payment initiation, order creation, broadcast execution, follow-up execution.

Duplicate request:
return existing logical result or safe UNKNOWN state; never duplicate financial/customer side effects.

---

# 29. SUPPORT SLA / ESCALATION
STATUS: CLOSED AS MVP INTERNAL TARGET

Starter:
- business-hours support target: response within 1 business day.
- critical security/payment incident: prioritize immediately.

Pro:
- business-hours support target: response within 4 business hours.
- critical security/payment incident: immediate prioritization.

These are support operating targets, not uptime guarantees.

---

# 30. INCIDENT SEVERITY
STATUS: CLOSED / LOCKED

SEV-1:
cross-tenant exposure, active critical security compromise, duplicate/incorrect financial side effect, destructive data corruption.

SEV-2:
major tenant-wide outage/degraded core commerce/WhatsApp/payment affecting many tenants.

SEV-3:
material feature degradation with workaround.

SEV-4:
minor defect, cosmetic issue, low-impact operational problem.

Incident lifecycle:
DETECTED → TRIAGED → CONFIRMED → CONTAINED → DIAGNOSING → RECOVERING → VERIFYING → RESOLVED → CLOSED.

---

# 31. DEGRADED MODE
STATUS: CLOSED / LOCKED

If AI unavailable:
- deterministic factual retrieval continues where safe;
- order/payment truth continues through deterministic systems;
- AI-dependent automation pauses/degrades;
- human handoff remains available where infrastructure permits.

If WhatsApp unavailable:
- no false delivery success;
- outbound messages enter controlled pending/failed/unknown state;
- no blind duplicate retry.

If payment provider unavailable:
- payment remains pending/unknown;
- no PAID transition from customer claim.

If database unavailable:
- fail safely; do not invent state.

---

# 32. PUBLIC API PRODUCT BOUNDARY
STATUS: CLOSED / LOCKED

MVP:
- internal APIs only except provider webhooks required for operation.

Pro:
- controlled tenant-scoped API/webhook surface for explicitly supported capabilities.

Never expose:
raw DB, arbitrary query execution, shell, filesystem, secrets, internal AI control plane, unrestricted cross-tenant administration.

Every public API request requires authentication, tenant scope, authorization, rate limit, schema validation, idempotency where applicable, audit and versioning.

---

# 33. UNIVERSAL WEBHOOK CONTRACT
STATUS: CLOSED / LOCKED

Inbound webhook:
signature/authenticity → provider identity → tenant mapping → schema validation → replay/idempotency → event persistence → processing → result/audit.

Webhook must carry:
provider, event ID, event type, timestamp, tenant/channel mapping, schema version, payload reference, correlation ID.

Unknown event type:
persist safely, do not execute unknown side effects.

---

# 34. LONG-RUNNING TASK LEASE
STATUS: CLOSED / LOCKED

- Durable task lease with expiry.
- Worker heartbeat.
- Expired lease can be reclaimed only with version/checkpoint protection.
- Side-effecting step must be idempotent.
- Never run two workers against the same mutable task without coordination.
- UNKNOWN external result requires reconciliation before replay.

---

# 35. WORKFLOW VERSIONING
STATUS: CLOSED / LOCKED

- Published workflow version is immutable.
- New edits create a new version.
- Running execution remains bound to its starting version unless an explicit migration policy exists.
- Disabled workflow cannot start new execution.
- Existing execution may finish only within valid entitlement/policy.
- Security/entitlement revocation can force cancellation/pause.

---

# 36. SCHEDULED WORKFLOW
STATUS: CLOSED / LOCKED

- Store timezone explicitly.
- Store schedule version.
- Missed execution policy: do not blindly replay all missed runs.
- Default missed-run behavior: skip stale execution and create an audit record.
- For business-critical scheduled tasks, explicit catch-up policy may be configured.
- Entitlement and tenant state are rechecked at execution time.

---

# 37. DATA CLASSIFICATION
STATUS: CLOSED / LOCKED

Classes:
PUBLIC
INTERNAL
CONFIDENTIAL
SENSITIVE
SECRET/CREDENTIAL.

Default:
customer identity, transaction and operational business data = CONFIDENTIAL.
authentication secrets, provider credentials, tokens = SECRET/CREDENTIAL.
Sensitive personal/financial information receives stricter access/logging rules.

AI context assembly must filter by classification and authority.

---

# 38. KNOWLEDGE vs BUSINESS DATA vs MEMORY
STATUS: CLOSED / LOCKED

Business Data:
authoritative operational truth.

Knowledge:
approved explanatory/instructional content with lifecycle/version.

Memory:
contextual historical information used to improve interaction.

Memory never outranks current business data.

Knowledge cannot silently overwrite transactional truth.

---

# 39. KNOWLEDGE EFFECTIVE DATE
STATUS: CLOSED / LOCKED

Knowledge record has:
version, status, effective_from, optional effective_until, source, owner, approval, audience, tenant.

At runtime:
only current applicable approved version may become active context.

Expired/outdated knowledge cannot silently remain authoritative.

---

# 40. MEMORY WRITE GOVERNANCE
STATUS: CLOSED / LOCKED

AI may propose memory writes.
Memory write is accepted only if:
- scope is valid,
- data classification permits,
- source is traceable,
- confidence/quality threshold is met,
- no contradiction with current authoritative data,
- retention policy permits it.

Customer explicit correction supersedes stale conversational memory.

---

# 41. AI EVALUATION / ACTIVATION
STATUS: CLOSED / LOCKED

AI capability cannot become READY merely because model responds.

Minimum evaluation:
- factual accuracy
- tenant isolation
- prompt-injection resistance
- tool authorization
- refusal/fail-closed behavior
- ambiguity handling
- transaction truth protection
- handoff behavior
- cost/latency envelope
- regression set.

Activation requires passing the applicable evaluation gate.

---

# 42. PROMPT INJECTION / UNTRUSTED CONTENT
STATUS: CLOSED / LOCKED

External/customer/retrieved content is data by default.

It cannot:
- grant permissions,
- redefine policy,
- authorize tools,
- reveal secrets,
- change tenant scope,
- override system/platform constraints.

Tool results are data unless explicitly converted into a controlled internal instruction by an authorized workflow component.

---

# 43. CONFUSED DEPUTY / DELEGATION
STATUS: CLOSED / LOCKED

Every delegated task carries:
principal, actor, tenant, authority scope, allowed tools, risk, expiry, purpose, correlation ID.

Delegated agent cannot:
- widen tenant scope,
- widen permission,
- create new authority,
- delegate beyond its own boundary,
- approve its own restricted action.

---

# 44. APPROVAL SECURITY
STATUS: CLOSED / LOCKED

Approval must bind:
request, actor, tenant, action, exact scope, version, risk, expiry, timestamp.

Requester and approver separation is required for actions where policy requires it.

AI cannot approve its own blocked action.

Expired/revoked approval cannot be reused.

---

# 45. MODEL / PROVIDER FALLBACK
STATUS: CLOSED / LOCKED

Fallback is allowed only among pre-approved models/providers.

Fallback must preserve:
policy, tenant scope, tool permissions, cost budget, output validation and risk level.

If no safe fallback:
bounded failure/handoff.

Provider failure does not justify lower security.

---

# 46. CORRELATION / TRACE
STATUS: CLOSED / LOCKED

Every material request gets:
request_id, correlation_id, tenant_id, actor_id where applicable, workflow/task ID, tool invocation ID where applicable, version IDs.

Trace IDs propagate across:
API → event → workflow → task → tool → provider → audit.

---

# 47. AUDIT IMMUTABILITY / TAMPER EVIDENCE
STATUS: CLOSED / LOCKED

Audit is append-oriented.

Minimum:
event ID, timestamp, tenant, actor, action, previous state, new state, source, correlation, version, result.

Integrity mechanism:
hash/chained integrity or equivalent tamper-evidence mechanism.

Audit cannot be edited by ordinary tenant users.

---

# 48. METRIC DEFINITIONS
STATUS: CLOSED / LOCKED

Core:
- active tenants = tenants in ACTIVE state.
- active subscriptions = subscriptions in ACTIVE/valid paid lifecycle.
- AI usage = normalized provider usage attributed to tenant/request.
- AI cost = provider/infrastructure cost attributed to usage where measurable.
- successful order = order reaches PAID/valid post-payment state according to commerce contract.
- marketing delivered = provider-confirmed delivery, not merely attempted.
- conversion = defined event pair/version, never inferred loosely by AI.

Every metric has:
definition, source, timezone/window, tenant scope, calculation version.

---

# 49. COST / UNIT ECONOMICS
STATUS: CLOSED AS CONTROL MODEL

Track:
MRR by plan
provider fees
AI cost
WhatsApp communication cost
payment provider fees
infrastructure cost
support cost
storage/egress where material.

Minimum internal guardrail:
- Pro must not silently subsidize unbounded provider usage.
- Communication and AI quotas are safety ceilings.
- Unit economics review occurs before raising quotas or enabling new expensive automation.
- Any new paid provider capability gets a cost attribution field before commercial activation.

Exact margin is not locked because actual provider/infrastructure costs must be measured from production-like usage.

---

# 50. BRANCH / MULTI-BUSINESS
STATUS: CLOSED FOR MVP

MVP:
one Tenant represents one business operating context.

Multiple branches/business units are not separate tenants by default and are not fully exposed as MVP functionality.

Future branch support must use explicit branch entity + scoped permissions + inventory/order/routing semantics.

Do not fake branch support through free-text configuration.

---

# 51. RETENTION / CUSTOMER DELETE VS TRANSACTION
STATUS: CLOSED / LOCKED

Customer deletion request:
- identity verified;
- tenant scope verified;
- deletion eligibility checked;
- transactional/legal/audit records preserved or anonymized where required;
- active AI context invalidated;
- caches/indexes/memory updated;
- exports and integrations considered;
- audit records retained as required.

Deletion cannot rewrite historical financial truth.

---

# 52. TENANT CLOSURE VS EXTERNAL INTEGRATION
STATUS: CLOSED / LOCKED

Before CLOSED:
- disable automation;
- stop outbound marketing;
- revoke/disable integrations;
- rotate/revoke credentials where applicable;
- reconcile pending external operations;
- preserve required billing/audit evidence;
- mark external UNKNOWN operations for reconciliation.

Tenant CLOSED must not leave active external credentials or autonomous workflows.

---

# 53. DATA EXPORT
STATUS: CLOSED / LOCKED

Export requires:
verified identity + tenant authorization + export scope + sensitive-data policy + audit.

Export must be versioned and reproducible enough to explain:
what data, when, tenant, requester, scope.

Cross-tenant export is impossible through tenant APIs.

---

# 54. OWNER / ADMIN LAST-OWNER RULE
STATUS: CLOSED / LOCKED

A tenant must always have at least one valid owner/admin authority path while ACTIVE.

Removing the last owner:
- blocked, or
- requires verified ownership transfer/recovery workflow.

No AI-only owner transfer.

---

# 55. MVP ACCEPTANCE CONTRACT
STATUS: CLOSED AS DESIGN / EVIDENCE REQUIRED

MVP is accepted only when:
- account/tenant works;
- tenant isolation passes;
- business data works;
- WhatsApp inbound/outbound works;
- AI factual retrieval works;
- handoff works;
- cart/order works;
- payment verification works;
- manual payment confirmation works;
- subscription/entitlement works;
- dashboard basics work;
- audit/observability work;
- failure/UNKNOWN/idempotency tests pass;
- security negative tests pass;
- E2E test passes.

---

# 56. STARTER ACCEPTANCE
STATUS: CLOSED AS DESIGN / EVIDENCE REQUIRED

Starter must provide:
- one tenant;
- basic business configuration;
- product/service;
- FAQ/knowledge;
- WhatsApp;
- customer/conversation;
- basic AI sales/support;
- handoff;
- cart/order;
- manual payment confirmation;
- basic dashboard;
- usage/billing.

Marketing automation is disabled.

---

# 57. PRO ACCEPTANCE
STATUS: CLOSED AS DESIGN / EVIDENCE REQUIRED

Pro adds:
- growth/automation;
- follow-up;
- abandoned cart;
- lead qualification;
- segmentation;
- multiple staff/admin;
- assignment/routing;
- bounded workflows;
- campaign/broadcast under D-COMM-02;
- richer analytics;
- supported integrations.

All remain bounded by entitlement, policy, consent, risk, budget and readiness.

---

# 58. OUT OF SCOPE
STATUS: CLOSED / LOCKED

Current launch does NOT include:
- Business/Enterprise commercial SKUs;
- commercial multi-channel rollout beyond WhatsApp;
- white-label/reseller;
- advanced ERP/POS/accounting/warehouse;
- advanced logistics/automatic waybill;
- marketplace;
- advanced BI/forecasting;
- global cross-tenant learning;
- unbounded autonomous AI;
- unrestricted AI-to-AI chains;
- arbitrary DB/shell/filesystem/secrets;
- enterprise custom integrations as standard Pro.

---

# 59. DOCUMENT CONTROL
STATUS: CLOSED / LOCKED

Historical OPEN labels are historical evidence unless a new controlled finding reopens them.

MERGED/REPAIRED ≠ PASS automatically.
PASS requires evidence.
Post-merge CI is not claimed without actual verification.
Decision state, implementation state, testing state and production state remain separate.

---

# 60. WHAT REMAINS OPEN AFTER THIS PROXY CLOSURE

These are NOT unanswered owner questions. They are evidence/configuration/external-verification items:

1. Repository implementation evidence.
2. Actual CI/test execution results.
3. GAP-003/GAP-006 post-merge evidence where not yet verified.
4. GAP-002/GAP-004/GAP-010/GAP-P1 post-merge evidence where not yet verified.
5. WhatsApp provider-specific current production contract verification.
6. Payment provider production contract verification.
7. Exact statutory tax/retention obligations with accountant/legal input.
8. Actual infrastructure benchmark proving RPO/RTO.
9. Actual provider/model price tables and AI cost measurements.
10. Security penetration/tenant-isolation execution evidence.
11. Real E2E WhatsApp/payment tests.
12. Production observability and restore-drill evidence.
13. Any new contradiction discovered by repository audit.

These are deliberately not "solved" on paper.

---

# 61. FINAL DECISION POSITION

Design decision closure:
GREEN.

Implementation evidence:
PENDING.

Repository readiness:
MUST BE VERIFIED.

Production readiness:
NOT READY until evidence gates pass.

Next engineering-controlled step:
AUDIT ACTUAL REPOSITORY → MAP IMPLEMENTATION GAPS → BUILD/TEST → EVIDENCE → RELEASE GATE.

This document does not authorize skipping evidence.
