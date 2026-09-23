# AI BOS — MASTER BUILD READINESS TODO

**Version:** 1.0  
**Date:** 2026-09-14  
**Status:** ACTIVE WORKING CHECKLIST — NOT YET BUILD-READY  
**Project:** AI Business Operating System (AI BOS)

---

# 0. PURPOSE

Dokumen ini adalah **master to-do / control checklist sebelum AI BOS masuk build implementation**.

Tujuannya:

1. Menjaga arah proyek agar tidak ngasal.
2. Menjadikan **Q1–Q51 sebagai DATA INDUK / canonical decision baseline**.
3. Menutup gap desain yang ditemukan audit sebelum coding besar dimulai.
4. Memisahkan keputusan arsitektur, kontrak implementasi, recommendation, assumption, risk, dan evidence.
5. Mencegah scope creep ketika target produk diperluas dari MVP ke **PRO TARGET BUILD**.
6. Menentukan bukti apa yang harus tersedia sebelum suatu tahap dinyatakan selesai.
7. Menjadi checklist sebelum GitHub/Copilot mulai implementasi.
8. Menjadi checklist untuk audit silang setelah implementation berjalan.

**Aturan tertinggi:** checklist ini tidak boleh dipakai untuk mengubah Q1–Q51 secara diam-diam. Jika ada konflik dengan Q1–Q51, tandai `CONFLICT` dan hentikan keputusan sampai Human Owner menyelesaikannya.

---

# 1. DATA INDUK

## 1.1 Canonical baseline

**Q1 → Q51 = DATA INDUK AI BOS**

Status:
- Q1–Q51 = LOCKED
- LOCKED ≠ IMPLEMENTED
- Q1–Q51 menjadi baseline untuk seluruh GAP, design contract, build plan, dan audit berikutnya.

### Aturan perubahan

- Tidak boleh silent change.
- Tidak boleh override karena "lebih bagus".
- Tidak boleh mengganti keputusan lama hanya karena implementasi terasa sulit.
- Jika keputusan baru bertentangan dengan Q1–Q51:
  1. identifikasi konflik,
  2. dokumentasikan dampak,
  3. ajukan perubahan secara eksplisit,
  4. minta keputusan Human Owner,
  5. update sumber canonical hanya setelah disetujui.

## 1.2 Hierarki sumber kerja

Urutan kerja audit harus mempertimbangkan:

1. **Q1–Q51 Locked Decisions** — induk keputusan.
2. **Master Blueprint** — struktur produk/arsitektur yang sudah disahkan.
3. **Supporting architecture/reference docs** — konteks pendukung.
4. **Operational Flow** — perilaku operasional; statusnya harus diperhatikan bila masih draft.
5. **Discovery / backlog** — ide/temuan, bukan otomatis keputusan.
6. **Implementation repository** — source of truth untuk code setelah build dimulai.
7. **Recommendations / analysis** — bukan keputusan sampai disetujui.

---

# 2. PROJECT MODE SAAT INI

## Current mode

`PRE-CODING — DESIGN/CONTRACT CLOSURE`

## Current target

`PRO TARGET BUILD`

**Catatan penting:**

Kita tidak lagi memperlakukan MVP kecil sebagai target akhir build. MVP tetap dipertahankan sebagai baseline commercial slice / launch baseline, tetapi target design/build pertama diarahkan ke **PRO** setelah scope Pro direkonsiliasi dan dibekukan.

## Tidak boleh dilakukan sekarang

- [ ] Jangan coding feature baru hanya karena "kelihatannya perlu".
- [ ] Jangan mengubah Q1–Q51 diam-diam.
- [ ] Jangan membuat scope Pro = semua future features.
- [ ] Jangan menganggap feature list = implementation contract.
- [ ] Jangan menganggap architecture principle = finished implementation design.
- [ ] Jangan mulai production build sebelum P1 contracts selesai.
- [ ] Jangan menganggap repository/code snapshot lama sebagai current truth sebelum repository audit.

---

# 3. DEFINISI STATUS CHECKLIST

Gunakan status berikut secara konsisten:

- `NOT STARTED` — belum dikerjakan.
- `IN PROGRESS` — sedang dikerjakan.
- `DRAFT` — sudah ada draft tetapi belum disetujui.
- `REVIEW` — sedang diaudit.
- `LOCKED` — keputusan sudah dikunci.
- `PASS` — acceptance criteria terpenuhi dengan evidence.
- `BLOCKED` — tidak bisa lanjut karena dependency/konflik.
- `DEFERRED` — sengaja ditunda dan tidak boleh menghalangi target saat ini.
- `REJECTED` — tidak masuk scope.
- `UNKNOWN` — bukti belum cukup.
- `CONFLICT` — dua sumber/keputusan bertentangan.

---

# 4. MASTER CONTROL CENTER

Isi dan update bagian ini setiap kali ada perubahan besar.

**Current Stage:** `GAP-001 PRO TARGET SCOPE RECONCILIATION`  
**Current Mode:** `PRE-CODING`  
**Canonical Baseline:** `Q1–Q51 LOCKED`  
**Build Target:** `PRO`  
**Build Status:** `NO-GO`  
**P1 Blockers Open:** `9` minimum dari audit sebelumnya  
**P2 Gaps Open:** `10+`  
**Repository Audit:** `BELUM MENJADI BASIS BUILD-READY`  
**Next Controlled Action:** `GAP-001`

## Control questions

- [ ] Apa current scope?
- [ ] Apa source/version terbaru?
- [ ] Apa yang sudah LOCKED?
- [ ] Apa yang masih draft?
- [ ] Apa yang conflict?
- [ ] Apa yang unknown?
- [ ] Apa dependency tahap ini?
- [ ] Apa evidence PASS?
- [ ] Apa yang boleh berubah?
- [ ] Apa yang tidak boleh berubah?

---

# 5. MASTER ROADMAP — URUTAN YANG HARUS DIIKUTI

Jangan mengerjakan 19 gap secara acak.

## PHASE A — SCOPE FREEZE

1. GAP-001 — PRO Target Scope Reconciliation
2. GAP-010 — Plan & Entitlement Matrix minimum Pro

**Exit Gate A:** Target Pro jelas, batas MVP baseline jelas, future jelas, tidak ada ambiguous scope besar.

## PHASE B — AUTHORITY & DATA TRUTH

3. GAP-002 — Actor / Authority / Permission Matrix
4. GAP-004 — Source-of-Truth / Conflict Resolution Matrix
5. GAP-006 — Customer Identity Contract

**Exit Gate B:** Sistem tahu siapa boleh melakukan apa, sumber mana yang dipercaya, dan siapa customer yang dimaksud.

## PHASE C — STATE & TRANSACTION

6. GAP-003 — Domain State Machine Registry
7. GAP-005 — Billing / Payment Contract

**Exit Gate C:** Lifecycle penting dan transaction-critical behavior tidak lagi ambigu.

## PHASE D — CUSTOMER JOURNEY / ACTIVATION

8. GAP-007 — WhatsApp E2E Contract
9. GAP-008 — READY / ACTIVE Acceptance Gate

**Exit Gate D:** Tenant dapat bergerak dari onboarding → ready → active dengan evidence.

## PHASE E — RESILIENCE / DEGRADATION

10. GAP-009 — Failure / Fallback / Degraded Behavior Contract

**Exit Gate E:** failure path penting punya deterministic behavior.

## PHASE F — PRO OPERATIONS

11. GAP-011 — AI Operating Mode Matrix
12. GAP-012 — Notification / Follow-up Policy
13. GAP-013 — Dashboard Acceptance Contract
14. GAP-014 — Audit / Observability Event Taxonomy
15. GAP-015 — Backup / Restore Acceptance
16. GAP-016 — Consent / Communication Policy
17. GAP-017 — Retention / Delete / Export Contract
18. GAP-018 — Integration Capability Matrix
19. GAP-019 — AI Cost / Budget Guardrails

**Exit Gate F:** Pro operational contract cukup lengkap untuk masuk implementation planning.

## PHASE G — INTEGRITY AUDIT BEFORE BUILD

20. Cross-stage integrity check.
21. Contradiction scan terhadap Q1–Q51.
22. Scope leakage scan.
23. Terminology consistency scan.
24. State transition consistency scan.
25. Permission/authority consistency scan.
26. Source-of-truth consistency scan.
27. Tenant isolation trace scan.
28. Payment/billing consistency scan.
29. Failure/recovery consistency scan.
30. AI/security consistency scan.

**Exit Gate G:** `DESIGN BUILD-READY` atau `NO-GO`.

## PHASE H — REPOSITORY AUDIT

31. Audit repository aktual.
32. Bandingkan code vs blueprint vs locked decisions.
33. Identifikasi existing code yang reusable.
34. Identifikasi stale/obsolete code.
35. Identifikasi missing modules.
36. Identifikasi security/regression risk.
37. Buat implementation gap map.

**Exit Gate H:** repository siap dijadikan execution baseline.

## PHASE I — IMPLEMENTATION PLAN

38. Freeze implementation scope.
39. Split into epics/modules.
40. Define migrations.
41. Define tests.
42. Define acceptance criteria.
43. Define deployment sequence.
44. Define rollback/recovery.
45. Define observability.
46. Define release gate.

## PHASE J — BUILD

47. Implement in controlled slices.
48. Run targeted tests.
49. Run regression.
50. Security/tenant isolation testing.
51. Transaction/billing testing.
52. AI behavior/evaluation.
53. E2E WhatsApp testing.
54. Readiness testing.
55. Controlled deployment.
56. Post-deployment verification.

---

# 6. GAP-001 — PRO TARGET SCOPE RECONCILIATION

**Priority:** P1  
**Status:** `NOT STARTED / CURRENT`  
**Purpose:** Menentukan scope Pro yang benar-benar menjadi target build pertama.

## 6.1 Collect source capability list

- [ ] Extract semua capability dari Q1–Q51 yang relevan ke commercial product.
- [ ] Extract capability dari Master Blueprint.
- [ ] Extract capability dari Master Reference.
- [ ] Review roadmap V1 / V1.5 / V2 / V3.
- [ ] Review Discovery Notes.
- [ ] Review Future Decisions Backlog.
- [ ] Tandai implementation-history material agar tidak dianggap requirement baru.

## 6.2 Classify every capability

Setiap capability harus diberi satu status:

- `PRO CORE`
- `PRO OPTIONAL`
- `FOUNDATION`
- `MVP BASELINE`
- `FUTURE`
- `OUT OF SCOPE`
- `DRAFT`
- `AMBIGUOUS`
- `CONFLICT`

## 6.3 Minimum fields per capability

- Capability ID
- Name
- Description
- Source
- Q-reference if applicable
- User/business purpose
- Actor
- Tenant scope
- Dependencies
- Data needed
- Authority needed
- Permission needed
- Risk level
- MVP baseline?
- Pro target?
- Future?
- UI required?
- API required?
- AI involved?
- Deterministic component?
- Acceptance criteria
- Out-of-scope boundary
- Open question

## 6.4 Specific scope items to resolve

- [ ] Product
- [ ] Service
- [ ] Hybrid business
- [ ] FAQ / Knowledge
- [ ] Customer management
- [ ] Conversation
- [ ] Handoff/support case
- [ ] Cart
- [ ] Order
- [ ] Payment
- [ ] Subscription
- [ ] Billing
- [ ] Entitlement
- [ ] Usage
- [ ] WhatsApp
- [ ] Additional integrations
- [ ] Dashboard
- [ ] Analytics
- [ ] Basic automation
- [ ] Advanced automation
- [ ] Follow-up
- [ ] Lead qualification
- [ ] Abandoned cart
- [ ] Segmentation
- [ ] Multiple admins
- [ ] Assignment / round robin
- [ ] Advanced CRM
- [ ] Owner AI
- [ ] Internal specialist AI
- [ ] AI operating modes
- [ ] AI cost control
- [ ] Approval
- [ ] Workflow
- [ ] Task
- [ ] Event
- [ ] Incident
- [ ] Notification
- [ ] Audit
- [ ] Observability
- [ ] Backup/restore
- [ ] Security controls
- [ ] Privacy controls

## 6.5 Explicitly define non-goals

- [ ] Multi-channel
- [ ] Enterprise features
- [ ] White-label
- [ ] Reseller platform
- [ ] Advanced BI/forecasting
- [ ] Advanced ERP/POS
- [ ] Advanced logistics
- [ ] Automatic fulfillment
- [ ] Marketplace commerce
- [ ] Unbounded AI autonomy
- [ ] Unbounded AI-to-AI communication
- [ ] Cross-tenant learning
- [ ] Other future capability from backlog unless explicitly promoted

## 6.6 Exit criteria

GAP-001 PASS only if:

- [ ] Every Pro capability has a scope classification.
- [ ] No major Pro feature is "implied" only.
- [ ] Every future feature has explicit boundary.
- [ ] MVP baseline is still recognizable as subset of Pro.
- [ ] Pro does not accidentally include Business/Enterprise/Future.
- [ ] Dependencies are visible.
- [ ] Major conflicts resolved or formally accepted as DEFERRED with impact understood.

---

# 7. GAP-010 — PLAN & ENTITLEMENT MATRIX

**Priority:** P1/P2 depending activation scope  
**Status:** `NOT STARTED`

## TODO

- [ ] Define Starter baseline.
- [ ] Define Pro baseline.
- [ ] Define feature entitlement.
- [ ] Define limits.
- [ ] Define quotas.
- [ ] Define capacity implications.
- [ ] Define add-ons.
- [ ] Define upgrade.
- [ ] Define downgrade.
- [ ] Define suspension.
- [ ] Define cancellation.
- [ ] Define expiry.
- [ ] Define grace period behavior.
- [ ] Define over-limit behavior.
- [ ] Define running workflow behavior after plan change.
- [ ] Define whether feature is disabled immediately or at next boundary.
- [ ] Define no-data-loss rule on downgrade.
- [ ] Define entitlement resolver inputs.
- [ ] Define entitlement audit evidence.

## Exit

- [ ] Every commercial feature resolves deterministically to entitled/not entitled/limited state.
- [ ] No AI decides entitlement.
- [ ] Subscription state and entitlement state are distinct.

---

# 8. GAP-002 — ACTOR / AUTHORITY / PERMISSION MATRIX

**Priority:** P1  
**Status:** `NOT STARTED`

## Required actor classes

- [ ] Human Owner
- [ ] Owner AI
- [ ] Internal Specialist AI
- [ ] Tenant Admin
- [ ] Tenant Staff
- [ ] Tenant AI
- [ ] Customer
- [ ] Prospect/Lead where applicable
- [ ] Support human
- [ ] System/service actor
- [ ] Workflow engine
- [ ] Task system
- [ ] Integration/provider

## Required action domains

- [ ] Read business data
- [ ] Write business data
- [ ] Delete/archive
- [ ] Order
- [ ] Payment
- [ ] Refund/cancellation
- [ ] Subscription
- [ ] Entitlement
- [ ] AI configuration
- [ ] Knowledge
- [ ] Customer data
- [ ] Credentials/integrations
- [ ] Workflow
- [ ] Task
- [ ] Notification
- [ ] Automation
- [ ] Cross-tenant analytics
- [ ] Incident actions
- [ ] Security-sensitive actions
- [ ] Agent creation/change

## Matrix fields

- Actor
- Scope
- Domain
- Action
- Permission
- Authority
- Policy
- Risk
- Confirmation
- Approval
- Delegation
- Preconditions
- Verification
- Audit requirement
- Forbidden action

## Exit

- [ ] No critical action has an implicit actor.
- [ ] Permission and authority are not conflated.
- [ ] Approval requirements are explicit.
- [ ] AI cannot self-authorize.

---

# 9. GAP-004 — SOURCE OF TRUTH / CONFLICT RESOLUTION MATRIX

**Priority:** P1  
**Status:** `NOT STARTED`

## Domains to map

- [ ] Business profile
- [ ] Product
- [ ] Service
- [ ] Price
- [ ] Variant
- [ ] Stock
- [ ] FAQ
- [ ] Knowledge
- [ ] Promotion
- [ ] Customer
- [ ] Conversation
- [ ] Cart
- [ ] Order
- [ ] Payment
- [ ] Subscription
- [ ] Entitlement
- [ ] Usage
- [ ] Workflow state
- [ ] Task state
- [ ] Incident
- [ ] Integration state
- [ ] WhatsApp delivery
- [ ] Audit
- [ ] Memory

## Required fields

- Official source
- Read source
- Write authority
- Update path
- Freshness requirement
- Version requirement
- Conflict source A
- Conflict source B
- Resolution rule
- Escalation rule
- Audit requirement

## Special checks

- [ ] AI memory cannot override authoritative state.
- [ ] Customer claims do not become official transaction truth.
- [ ] Payment status cannot rely on AI interpretation.
- [ ] Volatile stock is revalidated at transaction boundary.
- [ ] Approved Knowledge cannot silently outrank live transaction truth.

## Exit

- [ ] No critical domain has an undefined Source of Truth.
- [ ] No critical conflict case is resolved by guessing.

---

# 10. GAP-006 — CUSTOMER IDENTITY CONTRACT

**Priority:** P1  
**Status:** `NOT STARTED`

## TODO

- [ ] Define Account identity.
- [ ] Define Tenant identity.
- [ ] Define Customer identity.
- [ ] Define Contact/Channel identity.
- [ ] Define WhatsApp identity mapping.
- [ ] Define customer-to-tenant relation.
- [ ] Define duplicate identity detection.
- [ ] Define merge rules.
- [ ] Define identity conflict behavior.
- [ ] Define anonymous customer behavior.
- [ ] Define conversation ownership.
- [ ] Define cart ownership.
- [ ] Define order ownership.
- [ ] Define cross-channel future extension without breaking MVP/Pro.
- [ ] Define authorization impact of identity resolution.
- [ ] Define audit evidence.

## Security tests to require later

- [ ] Same phone number in different tenants.
- [ ] Tenant ambiguity.
- [ ] Reused WhatsApp number scenario.
- [ ] Session/context confusion.
- [ ] Customer tries to access another customer's order.

## Exit

- [ ] Customer identity resolves deterministically within tenant scope.
- [ ] Ambiguity never silently maps to another customer/tenant.

---

# 11. GAP-003 — DOMAIN STATE MACHINE REGISTRY

**Priority:** P1  
**Status:** `NOT STARTED`

## Domains

- [ ] Account
- [ ] Tenant
- [ ] Tenant onboarding
- [ ] Subscription
- [ ] Entitlement
- [ ] Integration
- [ ] WhatsApp connection
- [ ] Customer
- [ ] Conversation
- [ ] Support case
- [ ] Cart
- [ ] Order
- [ ] Payment
- [ ] Invoice if applicable
- [ ] Workflow
- [ ] Task
- [ ] Approval
- [ ] Notification/delivery
- [ ] Incident
- [ ] Knowledge item
- [ ] Memory item where operationally relevant

## Every state machine must specify

- Current state
- Valid next states
- Invalid transitions
- Preconditions
- Actor
- Permission
- Authority
- Policy
- Risk
- Approval requirement
- Side effects
- Verification
- Failure state
- UNKNOWN state if applicable
- Retry behavior
- Recovery behavior
- Audit evidence

## Exit

- [ ] No critical lifecycle relies on an undocumented boolean flag.
- [ ] Invalid transitions are explicitly blocked.
- [ ] State owner is identified.
- [ ] Derived status cannot become authoritative domain state accidentally.

---

# 12. GAP-005 — BILLING / PAYMENT CONTRACT

**Priority:** P1  
**Status:** `NOT STARTED`

## TODO

- [ ] Define Plan.
- [ ] Define Add-on.
- [ ] Define Subscription.
- [ ] Define Invoice.
- [ ] Define Payment.
- [ ] Define Entitlement.
- [ ] Define Usage.
- [ ] Define Quota.
- [ ] Define Capacity.
- [ ] Define provider state.
- [ ] Define internal payment state.
- [ ] Define reconciliation state.
- [ ] Define webhook lifecycle.
- [ ] Define idempotency key strategy.
- [ ] Define UNKNOWN result.
- [ ] Define duplicate webhook handling.
- [ ] Define failed payment.
- [ ] Define expiry.
- [ ] Define refund if Pro includes it.
- [ ] Define cancellation.
- [ ] Define upgrade.
- [ ] Define downgrade.
- [ ] Define suspension.
- [ ] Define reactivation.
- [ ] Define grace period policy.
- [ ] Define overage policy.
- [ ] Define payment verification evidence.

## Exit

- [ ] No plan becomes ACTIVE from customer statement alone.
- [ ] No entitlement becomes active without authoritative verification.
- [ ] Duplicate callbacks cannot duplicate financial effects.
- [ ] UNKNOWN is never reported as SUCCESS.

---

# 13. GAP-007 — WHATSAPP CUSTOMER-FACING E2E CONTRACT

**Priority:** P1  
**Status:** `NOT STARTED`

## E2E path

- [ ] Webhook receive
- [ ] Authenticity/verification
- [ ] Tenant resolution
- [ ] Customer identity
- [ ] Conversation resolution
- [ ] Message normalization
- [ ] Intent/context processing
- [ ] Authoritative retrieval
- [ ] AI decision boundary
- [ ] Tool/action control
- [ ] Response policy
- [ ] Human handoff
- [ ] Outbound adapter
- [ ] Provider response
- [ ] Delivery status
- [ ] Audit

## Failure scenarios

- [ ] Duplicate webhook
- [ ] Out-of-order event
- [ ] Webhook retry
- [ ] Invalid signature
- [ ] Unknown tenant
- [ ] Tenant mismatch
- [ ] Unknown customer
- [ ] Provider timeout
- [ ] AI timeout
- [ ] AI unavailable
- [ ] Tool unavailable
- [ ] Order/payment UNKNOWN
- [ ] Handoff active
- [ ] Human already responding
- [ ] Message collision prevention

## Exit

- [ ] One controlled customer-facing response path.
- [ ] Tenant scope survives entire message lifecycle.
- [ ] Duplicate delivery does not duplicate logical side effects.
- [ ] No unverified transaction status is communicated as success.

---

# 14. GAP-008 — READY / ACTIVE ACCEPTANCE GATE

**Priority:** P1  
**Status:** `NOT STARTED`

## Tenant readiness checklist

- [ ] Account valid
- [ ] Tenant valid
- [ ] Subscription valid
- [ ] Entitlement resolved
- [ ] Business profile valid
- [ ] Required business data valid
- [ ] Product/service data valid
- [ ] Knowledge minimum satisfied
- [ ] Policies configured
- [ ] Communication configuration valid
- [ ] WhatsApp connection valid
- [ ] Credential/integration state valid
- [ ] Webhook tested
- [ ] AI scenario tests passed
- [ ] Factual retrieval passed
- [ ] Handoff passed
- [ ] Customer identity passed
- [ ] Cart/order flow passed
- [ ] Payment flow passed if enabled
- [ ] Tenant isolation tests passed
- [ ] Permission tests passed
- [ ] Critical security tests passed
- [ ] Required audit evidence exists
- [ ] Client acceptance completed where required
- [ ] Owner/system readiness approval completed where required

## Exit

`ACTIVE` requires evidence, not simply a database flag.

---

# 15. GAP-009 — FAILURE / FALLBACK / DEGRADED BEHAVIOR CONTRACT

**Priority:** P1  
**Status:** `NOT STARTED`

## Components

- [ ] AI provider
- [ ] Secondary/fallback AI provider if adopted
- [ ] WhatsApp provider
- [ ] Payment provider
- [ ] Database
- [ ] Queue
- [ ] Worker
- [ ] Workflow engine
- [ ] Task system
- [ ] Integration provider
- [ ] Search/index
- [ ] Knowledge retrieval
- [ ] Notification provider
- [ ] Dashboard API

## Every failure must classify

- [ ] Temporary
- [ ] Permanent
- [ ] UNKNOWN
- [ ] Security-related
- [ ] Human-required
- [ ] Partial success

## Every critical failure must define

- Retry?
- Maximum retry
- Backoff
- Idempotency requirement
- Reconciliation
- Fallback
- Degraded mode
- Stop condition
- Human escalation
- Audit
- User-visible status
- Recovery

## Exit

- [ ] No blind retry on uncertain side effects.
- [ ] No false SUCCESS.
- [ ] Partial success cannot be silently treated as full success.
- [ ] Service degradation does not silently corrupt business truth.

---

# 16. GAP-011 — AI OPERATING MODE MATRIX

**Priority:** P2 → P1 if Pro autonomy is activated broadly  
**Status:** `NOT STARTED`

## Modes

- [ ] Manual
- [ ] Semi-Autonomous
- [ ] Autonomous

## For each mode define

- [ ] Allowed actions
- [ ] Forbidden actions
- [ ] Risk ceiling
- [ ] Permission requirement
- [ ] Approval requirement
- [ ] Confirmation requirement
- [ ] Budget/resource limit
- [ ] Time limit
- [ ] Tool scope
- [ ] Stop conditions
- [ ] Escalation rules
- [ ] Verification requirements
- [ ] Audit evidence

## Exit

Mode changes operational autonomy only; it never bypasses security, tenant isolation, authority, permission, policy, or risk constraints.

---

# 17. GAP-012 — NOTIFICATION / FOLLOW-UP POLICY

**Priority:** P2  
**Status:** `NOT STARTED`

## TODO

- [ ] Define notification types.
- [ ] Define reminders.
- [ ] Define transactional messages.
- [ ] Define follow-up.
- [ ] Define abandoned cart if included in Pro.
- [ ] Define lead follow-up if included.
- [ ] Define eligibility.
- [ ] Define timing.
- [ ] Define frequency.
- [ ] Define quiet hours if required.
- [ ] Define stop conditions.
- [ ] Define human handoff suppression.
- [ ] Define customer opt-out.
- [ ] Define duplicate suppression.
- [ ] Define state re-check before delivery.
- [ ] Define delivery UNKNOWN handling.
- [ ] Define audit.

## Exit

- [ ] Follow-up cannot run indefinitely.
- [ ] Automation cannot conflict with human handling.
- [ ] Outdated state is revalidated before important communication.

---

# 18. GAP-013 — DASHBOARD ACCEPTANCE CONTRACT

**Priority:** P2  
**Status:** `NOT STARTED`

## MVP/Pro dashboard domains

- [ ] Overview
- [ ] WhatsApp status
- [ ] Chats/conversations
- [ ] Handoff/cases
- [ ] Customers
- [ ] Orders
- [ ] Cart
- [ ] Payment/order status
- [ ] Business profile
- [ ] Products/services
- [ ] FAQ/Knowledge
- [ ] AI usage
- [ ] Basic/Pro analytics as scoped
- [ ] Subscription/billing if tenant-facing

## Each screen must define

- [ ] Source of data
- [ ] Tenant scope
- [ ] Permission
- [ ] Allowed actions
- [ ] Empty state
- [ ] Loading state
- [ ] Error state
- [ ] UNKNOWN state where applicable
- [ ] Refresh semantics
- [ ] Audit requirement for material changes

## Exit

No dashboard number/status may silently be treated as authoritative transaction truth unless its source is authoritative.

---

# 19. GAP-014 — AUDIT / OBSERVABILITY EVENT TAXONOMY

**Priority:** P2  
**Status:** `NOT STARTED`

## Event families to define

- [ ] Authentication
- [ ] Authorization
- [ ] Tenant lifecycle
- [ ] Configuration
- [ ] Product/data change
- [ ] Knowledge change
- [ ] Customer change
- [ ] Conversation
- [ ] Handoff
- [ ] Order
- [ ] Payment
- [ ] Subscription
- [ ] Entitlement
- [ ] AI execution
- [ ] AI block
- [ ] Tool execution
- [ ] Workflow
- [ ] Task
- [ ] Approval
- [ ] Notification
- [ ] Incident
- [ ] Integration
- [ ] Security anomaly
- [ ] Backup/restore
- [ ] Deployment/release

## Required evidence fields

- Event ID
- Timestamp
- Actor
- Tenant
- Target
- Action
- Purpose where applicable
- Version context where applicable
- Result
- Correlation/trace ID
- Security-sensitive redaction
- Related workflow/task/case/order ID as applicable

## Exit

- [ ] Important actions reconstructable without private chain-of-thought.
- [ ] Audit data cannot be freely manipulated by audited actor.
- [ ] No secrets in logs/audit.

---

# 20. GAP-015 — BACKUP / RESTORE ACCEPTANCE

**Priority:** P2  
**Status:** `NOT STARTED`

## TODO

- [ ] Define protected state.
- [ ] Define backup scope.
- [ ] Define tenant isolation in backup.
- [ ] Define restore scope.
- [ ] Define restore authorization.
- [ ] Define state/version handling.
- [ ] Define audit preservation.
- [ ] Define external side-effect reconciliation.
- [ ] Define Ghost Data protection after restore.
- [ ] Define verification checks.
- [ ] Define degraded service during recovery.
- [ ] Define recovery evidence.

## Exit

- [ ] Restore cannot silently reactivate deleted/revoked data.
- [ ] Restore cannot erase historical truth.
- [ ] External side effects are not assumed reversed by internal restore.

---

# 21. GAP-016 — CONSENT / COMMUNICATION POLICY

**Priority:** P2  
**Status:** `NOT STARTED`

## TODO

- [ ] Transactional communication.
- [ ] Service communication.
- [ ] Marketing communication.
- [ ] Consent/opt-in where required.
- [ ] Opt-out.
- [ ] Frequency rules.
- [ ] Purpose limitation.
- [ ] Suppression.
- [ ] Tenant policy.
- [ ] Platform mandatory constraints.
- [ ] Audit.
- [ ] Privacy boundaries.

## Exit

- [ ] Marketing/follow-up cannot be triggered merely because a customer exists.
- [ ] Opt-out/suppression can stop applicable future communication.

---

# 22. GAP-017 — RETENTION / DELETE / EXPORT CONTRACT

**Priority:** P2  
**Status:** `NOT STARTED`

## Data classes

- [ ] Operational data
- [ ] Transaction history
- [ ] Customer data
- [ ] Conversation data
- [ ] Knowledge
- [ ] Memory
- [ ] Analytics
- [ ] Usage
- [ ] Billing records
- [ ] Audit evidence
- [ ] Backup copies
- [ ] Derived artifacts

## TODO

- [ ] Retention state
- [ ] Archive
- [ ] Soft delete
- [ ] Permanent deletion
- [ ] Export
- [ ] Tenant closure
- [ ] Propagation to cache/index/memory/knowledge where applicable
- [ ] Backup implications
- [ ] Historical truth preservation
- [ ] Privacy/legal rule placeholder
- [ ] Audit

## Exit

- [ ] Deleted/ineligible information cannot remain active as AI fact merely due cache/index/memory.
- [ ] Historical records that must remain are protected from arbitrary deletion.

---

# 23. GAP-018 — INTEGRATION CAPABILITY MATRIX

**Priority:** P2  
**Status:** `NOT STARTED`

## Candidate integrations to audit

- [ ] WhatsApp
- [ ] Payment provider(s)
- [ ] Google Sheets
- [ ] Google Calendar
- [ ] Other payment/CRM/storage integrations appearing in current documentation

## For every integration define

- Purpose
- Scope
- Tenant mapping
- Authentication
- Credential storage boundary
- Available capabilities
- Read operations
- Write operations
- Authoritative domains
- Non-authoritative domains
- Webhook
- Retry
- UNKNOWN handling
- Idempotency
- Conflict resolution
- Rate limit
- Failure handling
- Audit
- Plan entitlement
- MVP/Pro/Future status

## Exit

- [ ] Provider-specific logic stays behind adapter boundary.
- [ ] Credential presence alone does not mean integration ACTIVE.
- [ ] External provider state does not automatically dominate internal state.

---

# 24. GAP-019 — AI COST / BUDGET GUARDRAILS

**Priority:** P2  
**Status:** `NOT STARTED`

## TODO

- [ ] Define usage dimensions.
- [ ] Tenant budget.
- [ ] Agent budget if required.
- [ ] Workflow budget.
- [ ] Request budget.
- [ ] Retry budget.
- [ ] Model/provider cost attribution.
- [ ] Soft threshold.
- [ ] Hard threshold.
- [ ] Degraded/economy mode.
- [ ] Over-budget behavior.
- [ ] Alert.
- [ ] Approval for exceptional cost.
- [ ] Anti-runaway control.
- [ ] Cost reconciliation.
- [ ] Tenant transparency.
- [ ] Platform cost monitoring.

## Exit

- [ ] Autonomous operation cannot spend unlimited resources.
- [ ] Cost control cannot weaken mandatory safety/security/business correctness.
- [ ] Usage is distinct from billing truth.

---

# 25. CROSS-STAGE INTEGRITY CHECK

WAJIB dilakukan setelah seluruh P1 contract selesai dan sebelum repository/build planning dianggap ready.

## 25.1 Decision integrity

- [ ] Semua Q1–Q51 tetap intact.
- [ ] Tidak ada silent override.
- [ ] Semua new decisions punya ID.
- [ ] Semua conflicts dicatat.
- [ ] All LOCKED decisions have clear dependency.

## 25.2 Scope integrity

- [ ] Pro target tidak mengandung Future secara tidak sengaja.
- [ ] Business/Enterprise tidak bocor ke Pro.
- [ ] MVP baseline tetap subset yang valid.
- [ ] No duplicated capability with different names.
- [ ] No feature exists only because of vague wording.

## 25.3 Terminology integrity

Standardize at minimum:

- [ ] Platform
- [ ] Account
- [ ] Owner
- [ ] Tenant
- [ ] Tenant Admin
- [ ] Customer
- [ ] Prospect
- [ ] Lead
- [ ] Client
- [ ] Conversation
- [ ] Case
- [ ] Task
- [ ] Workflow
- [ ] Event
- [ ] State
- [ ] Trigger
- [ ] Policy
- [ ] Configuration
- [ ] Permission
- [ ] Authority
- [Approval]
- [Entitlement]
- [Quota]
- [Capacity]
- [Usage]
- [Memory]
- [Knowledge]
- [Source of Truth]
- [Integration]
- [Credential]

## 25.4 Security integrity

- [ ] Tenant isolation through request → context → AI → tool → workflow → storage → result.
- [ ] Secrets never become ordinary AI context.
- [ ] Untrusted content cannot authorize actions.
- [ ] No indirect privilege escalation through agent chaining.
- [ ] No cross-tenant leakage via cache/search/queue/file/event/analytics/billing.

## 25.5 AI integrity

- [ ] AI does not own transaction truth.
- [ ] AI does not self-authorize.
- [ ] AI recommendation is not approval.
- [ ] AI output is not automatically fact.
- [ ] AI mode does not bypass security.
- [ ] AI fallback does not corrupt state.
- [ ] AI evaluation has evidence.

## 25.6 Transaction integrity

- [ ] Order flow deterministic.
- [ ] Payment verification deterministic.
- [ ] Idempotency exists where needed.
- [ ] UNKNOWN state exists.
- [ ] Concurrent updates are controlled.
- [ ] External side-effect UNKNOWN is reconciled.

---

# 26. STOP RULES

Proyek **WAJIB STOP / NO-GO** apabila salah satu terjadi:

- [ ] Q1–Q51 conflict belum diselesaikan.
- [ ] Tenant boundary tidak jelas.
- [ ] Actor authority tidak jelas untuk high-impact action.
- [ ] Source of Truth tidak jelas untuk transaction-critical domain.
- [ ] Payment truth ambigu.
- [ ] Customer identity ambigu sehingga berpotensi salah tenant/customer.
- [ ] Critical state transition belum didefinisikan.
- [ ] High-risk action belum punya approval/authority path.
- [ ] Critical failure mode belum punya safe behavior.
- [ ] Required evidence belum tersedia tetapi status dinyatakan PASS.
- [ ] Scope Pro masih berubah-ubah tanpa change control.
- [ ] Implementation dimulai dengan assumption penting yang belum disetujui.

---

# 27. EVIDENCE REQUIREMENT

Tidak boleh menulis `PASS` hanya karena konsep sudah ditulis.

Untuk setiap gate, simpan evidence berupa satu atau lebih:

- Decision record
- Final matrix
- State diagram
- Contract specification
- Scenario test
- Acceptance test
- Repository evidence
- Migration plan
- Security test
- E2E test
- Observability trace
- Audit record
- Owner approval

## Format evidence

`EVIDENCE-ID | Artifact | Version | Date | Scope | Result | Reviewer`

---

# 28. CHANGE CONTROL

Setiap perubahan setelah Q1–Q51 harus masuk log.

## Required fields

- Change ID
- Date
- Source request
- Related Q decision
- Related GAP
- Current state
- Proposed change
- Reason
- Impact
- Security impact
- Tenant impact
- Data impact
- Workflow impact
- Billing impact
- Compatibility impact
- Migration needed?
- Rollback/recovery
- Recommendation
- Human Owner decision
- Final status

## Rule

Tidak boleh mengedit keputusan canonical hanya karena diskusi berubah di chat.

---

# 29. REPOSITORY AUDIT — SETELAH DESIGN CONTRACT PASS

## 29.1 Repository baseline

- [ ] Confirm repository identity.
- [ ] Confirm branch/commit/tag used for audit.
- [ ] Confirm current build state.
- [ ] Confirm database/migration state.
- [ ] Confirm test suite.
- [ ] Confirm environment/configuration model.

## 29.2 Compare code vs source

- [ ] Architecture matches blueprint.
- [ ] Q1–Q51 constraints respected.
- [ ] Existing implementation not mistaken as final architecture.
- [ ] Deprecated code identified.
- [ ] Duplicate systems identified.
- [ ] Security boundaries inspected.
- [ ] Tenant isolation inspected.
- [ ] Auth inspected.
- [ ] Billing/payment inspected.
- [ ] AI Gateway inspected.
- [ ] Agent boundary inspected.
- [ ] Workflow/task inspected.
- [ ] Integration adapters inspected.
- [ ] Observability inspected.

## 29.3 Security/code checks

- [ ] No secrets committed.
- [ ] No arbitrary AI SQL.
- [ ] No unrestricted shell/tool access.
- [ ] No unrestricted filesystem access.
- [ ] No cross-tenant query path.
- [ ] No unguarded admin bypass.
- [ ] No prompt-only security boundary.
- [ ] No direct provider-specific business logic where adapter required.

---

# 30. IMPLEMENTATION READINESS GATE

Do not start broad production implementation until all are PASS:

### Architecture
- [ ] Q1–Q51 integrity PASS.
- [ ] Target Pro scope PASS.
- [ ] No critical ambiguity.

### Data
- [ ] Source-of-Truth matrix PASS.
- [ ] Customer identity PASS.
- [ ] State registry PASS.

### Authority/security
- [ ] Authority matrix PASS.
- [ ] Tenant isolation design PASS.
- [ ] Secret boundary PASS.
- [ ] Prompt/injection boundary PASS.

### Commerce
- [ ] Billing/payment contract PASS.
- [ ] Entitlement matrix PASS.
- [ ] Order/cart/payment states PASS.

### Communication
- [ ] WhatsApp E2E contract PASS.
- [ ] Notification/follow-up policy PASS where relevant.

### Reliability
- [ ] Failure/fallback PASS.
- [ ] Recovery/backup acceptance PASS as required.

### Operations
- [ ] Dashboard contract PASS.
- [ ] Audit taxonomy PASS.
- [ ] Cost guardrail PASS.

### Repository
- [ ] Actual repository audited.
- [ ] Implementation gap map completed.
- [ ] Existing code reuse/rewriting decisions explicit.

If any critical gate is not PASS:

`BUILD STATUS = NO-GO`

---

# 31. IMPLEMENTATION PLANNING CHECKLIST

After Build Readiness Gate passes:

- [ ] Domain boundaries fixed.
- [ ] Module boundaries fixed.
- [ ] Database entities fixed.
- [ ] API contracts fixed.
- [ ] Event contracts fixed.
- [ ] Workflow contracts fixed.
- [ ] Tool contracts fixed.
- [ ] AI agent contracts fixed.
- [ ] Permission checks fixed.
- [ ] Migration sequence fixed.
- [ ] Test strategy fixed.
- [ ] Deployment sequence fixed.
- [ ] Observability fixed.
- [ ] Rollback/recovery plan fixed.
- [ ] Definition of Done fixed.

---

# 32. BUILD EXECUTION CHECKLIST

Implement one bounded slice at a time.

For every implementation slice:

1. Read relevant locked decisions.
2. Read relevant contract.
3. Confirm scope.
4. Identify dependencies.
5. Implement minimum bounded change.
6. Run targeted tests.
7. Run related regression.
8. Check tenant isolation.
9. Check permissions.
10. Check idempotency/failure path.
11. Check audit evidence.
12. Compare result against contract.
13. Update status.
14. Record deviations.
15. Stop if unexpected architecture change appears.

---

# 33. PRE-RELEASE MASTER CHECKLIST

## Functional

- [ ] Critical user journeys work.
- [ ] Customer journey works.
- [ ] Tenant onboarding works.
- [ ] WhatsApp E2E works.
- [ ] Order/payment works.
- [ ] Human handoff works.
- [ ] Pro entitlements work.

## Security

- [ ] Tenant isolation tested.
- [ ] Permission tested.
- [ ] Secret handling tested.
- [ ] Prompt injection tested.
- [ ] Cross-tenant access tested.
- [ ] Tool boundaries tested.

## Data

- [ ] Source of Truth validated.
- [ ] Identity resolution validated.
- [ ] State transitions validated.
- [ ] Migration tested.
- [ ] Backup/restore tested.

## AI

- [ ] Grounding tested.
- [ ] Hallucination resistance tested.
- [ ] Tool action correctness tested.
- [ ] Unauthorized action blocked.
- [ ] Handoff tested.
- [ ] UNKNOWN status preserved.
- [ ] Cost guardrails tested.

## Reliability

- [ ] Retry safe.
- [ ] Duplicate events safe.
- [ ] Crash recovery safe.
- [ ] Partial success explicit.
- [ ] Provider failure handled.
- [ ] Recovery verified.

## Observability

- [ ] Trace available.
- [ ] Audit available.
- [ ] Important state transitions visible.
- [ ] AI execution trace available without private CoT.
- [ ] Cost/usage visible.
- [ ] Security events visible.

---

# 34. CURRENT OPEN WORK REGISTER

## P1

- [ ] GAP-001 — PRO Target Scope Reconciliation
- [ ] GAP-002 — Actor / Authority / Permission Matrix
- [ ] GAP-003 — Domain State Machine Registry
- [ ] GAP-004 — Source-of-Truth / Conflict Resolution Matrix
- [ ] GAP-005 — Billing / Payment Contract
- [ ] GAP-006 — Customer Identity Contract
- [ ] GAP-007 — WhatsApp E2E Contract
- [ ] GAP-008 — READY / ACTIVE Acceptance Gate
- [ ] GAP-009 — Failure / Fallback / Degraded Contract

## P2

- [ ] GAP-010 — Plan / Entitlement Matrix
- [ ] GAP-011 — AI Operating Mode Matrix
- [ ] GAP-012 — Notification / Follow-up Policy
- [ ] GAP-013 — Dashboard Acceptance Contract
- [ ] GAP-014 — Audit / Observability Event Taxonomy
- [ ] GAP-015 — Backup / Restore Acceptance
- [ ] GAP-016 — Consent / Communication Policy
- [ ] GAP-017 — Retention / Delete / Export Contract
- [ ] GAP-018 — Integration Capability Matrix
- [ ] GAP-019 — AI Cost / Budget Guardrails

---

# 35. FINAL PRINCIPLE

AI BOS tidak boleh bergerak dengan pola:

`IDE → CODING → baru menemukan masalah.`

Pola yang harus dipakai:

`Q1–Q51 INDUK`

→ `AUDIT`

→ `SCOPE`

→ `CONTRACT`

→ `AUTHORITY`

→ `STATE`

→ `SOURCE OF TRUTH`

→ `IDENTITY`

→ `TRANSACTION`

→ `E2E`

→ `FAILURE`

→ `PRO OPERATION`

→ `INTEGRITY CHECK`

→ `REPOSITORY AUDIT`

→ `IMPLEMENTATION PLAN`

→ `BUILD`

→ `TEST`

→ `VERIFY`

→ `RELEASE`

Setiap tahap harus mempunyai **EXIT GATE**.

Tidak ada tahap yang boleh dianggap selesai hanya karena "sudah dibahas".

---

# 36. CURRENT NEXT ACTION

**NEXT:** GAP-001 — PRO TARGET SCOPE RECONCILIATION

Output yang wajib dihasilkan dari GAP-001:

1. PRO capability inventory.
2. MVP baseline inventory.
3. Future/non-goal inventory.
4. Scope classification setiap capability.
5. Dependency map.
6. Ambiguity register.
7. Conflict register.
8. Recommendation register.
9. Human Owner decision list.
10. Final PRO Target Scope Contract.
11. GAP-001 Integrity Check.
12. GAP-001 PASS / REMAIN OPEN decision.

**JANGAN lanjut GAP-002 sebelum GAP-001 memiliki scope yang cukup jelas untuk menjadi basis authority matrix.**

---

# 37. OWNER DECISION LOG — TO BE FILLED

| ID | Decision | Source/Reason | Impact | Status |
|---|---|---|---|---|
| DEC-001 | Q1–Q51 menjadi data induk | Human Owner | Semua audit/build | LOCKED |
| DEC-002 | Target build diarahkan ke Pro | Human Owner direction | GAP-001 scope | APPROVED DIRECTION — LOCK AFTER RECONCILIATION |
| DEC-003 |  |  |  | OPEN |
| DEC-004 |  |  |  | OPEN |

---

# 38. AUDIT CHANGE LOG

| Version | Date | Change | Reason |
|---|---|---|---|
| 1.0 | 2026-09-14 | Initial Master Build Readiness TODO; Q1–Q51 treated as canonical parent; target shifted from small MVP to Pro-target reconciliation | Prevent direction drift before build |

---

# END
