# AI BOS — MASTER AUDIT QUESTION & KNOWLEDGE BASE
## Stage 0 — Pre-Coding SaaS Foundation
Version: 0.1
Date: 2026-09-12
Status: WORKING MASTER — NOT FINAL BLUEPRINT

---

# 0. TUJUAN FILE

File ini adalah **kiblat utama untuk proses audit dan pengumpulan keputusan** AI Business Operating System (AI BOS).

Tujuannya bukan memberi perintah coding.

File ini menjadi tempat untuk:
1. Mengumpulkan seluruh ide dan konsep SaaS.
2. Menyatukan pengetahuan yang tersebar di banyak dokumen.
3. Menandai hal yang belum jelas.
4. Menandai konflik antar dokumen/konsep.
5. Menemukan requirement yang kurang.
6. Menguji apakah sebuah konsep tepat, terlalu luas, tumpang tindih, atau berisiko.
7. Menyimpan pertanyaan yang harus dijawab Human Owner.
8. Menyimpan jawaban final per tahap.
9. Menjadi dasar penyusunan Blueprint SaaS final.
10. Menjadi sumber konteks sebelum tahap implementasi dimulai.

**ATURAN UTAMA:**
- Tidak coding pada fase ini.
- Tidak membuat keputusan secara diam-diam.
- Tidak mengisi kekosongan dengan asumsi.
- Jika bukti tidak cukup: UNKNOWN.
- Jika dua sumber berbeda: CONFLICT.
- Jika maksud belum jelas: AMBIGUOUS.
- Jika kebutuhan belum ada: MISSING REQUIREMENT.
- Jika sesuatu terlihat keliru/kurang tepat: POTENTIAL ERROR.
- Jawaban Human Owner menjadi keputusan final setelah dikonfirmasi.

---

# 1. SUMBER YANG DIAUDIT

Sumber utama yang dipakai untuk Stage 0:

1. MASTER_BLUEPRINT_FINAL_v1.1.md
2. AI_BOS_MASTER_REFERENCE.md
3. AI_BOS_LOCKED_DECISIONS_ACT_001_090.md
4. AI_BOS_MVP_DISCOVERY_NOTES_v0.1.md
5. AI_BOS_FUTURE_DECISIONS_BACKLOG_v0.1.md
6. MASTER_OPERATIONAL_FLOW_v1.0.md

Dokumen execution/coding seperti MASTER EXECUTION PLAN dikeluarkan dari active design phase.

Catatan:
- Blueprint v1.1 mengandung materi konseptual sekaligus snapshot implementasi lama.
- Locked Decisions berisi keputusan sampai ACT-410 walaupun nama file berhenti di ACT-090.
- Operational Flow adalah spesifikasi perilaku operasional dan masih berstatus draft/review.
- Discovery Notes secara eksplisit bukan locked blueprint.
- Future Decisions adalah parking lot dan tidak boleh memblokir MVP.

---

# 2. VISI PRODUK YANG TERKUMPUL

AI BOS bukan sekadar bot WhatsApp.

Konsep utama:
> Platform SaaS multi-tenant yang membantu bisnis menjalankan operasi dengan AI secara terkontrol.

Kemampuan yang muncul dalam sumber:
- Customer Service
- Sales
- Support
- Follow-up
- Customer Management / CRM
- Knowledge Management
- Business Data
- Order Management
- Automation
- Analytics
- Business Intelligence
- Billing
- Integrations
- AI Management
- Owner AI
- Multi-channel communication
- Business recommendations
- Engineering/reliability assistance

Prinsip:
> Build once, configure many, activate gradually.

Satu Universal Core melayani banyak tenant. Perbedaan tenant berasal dari data, konfigurasi, knowledge, permissions, plan, add-ons, integrations, workflows, entitlements, usage limits, dan konfigurasi lain yang sah.

---

# 3. TARGET CUSTOMER

Primary:
- UMKM Indonesia
- online sellers
- retail
- fashion
- food & beverage
- service business
- small agencies
- appointment/booking businesses
- bisnis dengan volume inquiry WhatsApp signifikan

Future:
- growing SMB
- multi-branch
- agencies/resellers
- enterprise

## Pertanyaan yang masih perlu diputuskan
- Segmen UMKM mana yang menjadi beachhead market?
- Apakah semua tipe bisnis benar-benar target MVP?
- Bisnis apa yang sengaja tidak didukung pada MVP?
- Masalah customer mana yang paling bernilai untuk dibayar?
- Apakah produk pertama diposisikan sebagai AI Customer Service, AI Business Assistant, atau AI Business Operating System versi MVP?

---

# 4. STRUKTUR ENTITAS BISNIS

Konsep yang sudah ada:

PLATFORM
→ CLIENT / TENANT
→ TENANT CUSTOMER

Tenant adalah bisnis yang berlangganan AI BOS.
Customer adalah pelanggan milik tenant.

Hal ini harus konsisten di:
- Sales
- CRM
- onboarding
- memory
- analytics
- billing
- channel
- permission

## Pertanyaan
- Apakah satu Human Owner boleh memiliki banyak tenant? Sudah diarahkan YA.
- Apakah satu tenant boleh mempunyai banyak business unit/branch?
- Apakah branch adalah tenant, sub-tenant, atau entitas internal?
- Apa definisi resmi Owner, Admin, Staff, Customer, Prospect, Lead, Client, Tenant?
- Apakah Prospect/Lead/Customer/Client memiliki lifecycle dan data model berbeda?
- Bagaimana identity resolution bekerja antar channel?

---

# 5. SAAS PRODUCT STRUCTURE

Konsep paket:
- Starter — target Rp299.000/bulan
- Pro — target Rp799.000/bulan
- Business — target Rp1.999.000/bulan
- Enterprise — custom, indikatif Rp5m+/bulan

Revenue:
- Subscription
- Setup Fee
- Add-ons
- Custom Service
- Enterprise
- Reseller/White-label future

Add-ons:
- extra WhatsApp
- AI credits
- storage
- analytics
- automation
- premium integrations
- custom AI agent
- priority support
- dedicated infrastructure
- AI Technician future

Model:
Plan + Addon + Entitlement + Usage

## Masih harus diaudit
- Apakah harga tersebut final atau hanya target?
- Fitur mana yang benar-benar membedakan setiap plan?
- Apakah semua fitur dapat dimodelkan dengan entitlement?
- Apa yang terjadi ketika downgrade membuat tenant melebihi limit?
- Bagaimana trial, grace period, suspension, expiry, renewal, upgrade, downgrade, cancellation?
- Apakah setup fee wajib atau opsional?
- Apa definisi "AI credits"?
- Bagaimana credit dihitung?
- Apakah AI usage berbeda per model?
- Bagaimana overage ditangani?
- Apakah tenant dapat membeli top-up?
- Apakah billing Indonesia membutuhkan pajak/invoice khusus?

---

# 6. MVP SCOPE

Sumber menyebut MVP mencakup:
- multi-tenant
- tenant isolation
- authentication
- business configuration
- products
- WhatsApp
- AI
- factual retrieval
- human handoff
- orders
- onboarding
- provisioning
- AI usage/cost
- subscription
- workflow
- events
- audit
- backup
- tests
- observability

Blueprint V1 commercial MVP juga menyebut:
- WhatsApp AI
- FAQ
- products
- prices
- stock
- customers
- conversations
- orders
- cart
- human handoff
- basic automation
- dashboard
- Starter/Pro
- billing
- onboarding
- essential integrations
- usage tracking

## Konflik / pertanyaan penting
**MVP scope belum sepenuhnya konsisten.**

Contoh:
- Blueprint menyebut Starter + Pro sebagai V1, sementara Business dan Enterprise sudah didefinisikan.
- Tenant AI/Owner AI memiliki beberapa versi scope berbeda.
- AI Support ada di blueprint/reference, tetapi lean MVP discovery menyarankan Tenant AI + Client Manager + Sales + lightweight Analyst.
- Data Manager AI disebut ada, tetapi discovery menyarankan tidak wajib untuk first tenant MVP.
- Beberapa capability seperti advanced CRM, forecast, anomaly detection, multi-channel muncul di plan/blueprint tetapi roadmap menempatkannya lebih lanjut.

Pertanyaan:
> Apa definisi MVP yang benar-benar ingin dijual pertama kali?

Jawaban: [BELUM DIPUTUSKAN]

---

# 7. UNIVERSAL CORE

Konsep:
Channel
→ Universal Message
→ Tenant Context
→ Conversation
→ Router
→ Deterministic Business Logic
→ AI bila diperlukan
→ Response
→ Channel Adapter

Universal Core:
- shared
- multi-tenant
- configuration-driven
- channel-independent
- deterministic-first
- auditable
- secure
- reusable

## Hal yang perlu diperjelas
- Apa batas Universal Core?
- Mana yang benar-benar Core dan mana Engine?
- Apakah Customer/Conversation/Product/Order adalah Core domain atau domain module?
- Apakah Universal Core hanya tenant-facing?
- Discovery secara eksplisit mengoreksi konsep bahwa Universal Core adalah operator bisnis Owner.
- Owner's own business menggunakan Internal AI ecosystem.
- Tenant business menggunakan Universal Core + Tenant AI + Tenant Specialist AI.

Ini merupakan **koreksi konseptual penting** yang harus dipertahankan.

---

# 8. INTERNAL AI DOMAIN vs TENANT AI DOMAIN

## Internal
Human Owner
→ Owner AI
→ Internal Specialist AIs

Initial:
- Owner AI
- Sales AI
- Client Manager AI
- Data Manager AI
- Analyst AI

## Tenant
Human Tenant/Admin
→ Tenant AI
→ Tenant Specialist AIs

Candidate:
- Tenant AI
- Sales AI
- Client Manager AI
- Analyst AI
- Data Manager AI

Discovery merekomendasikan lean tenant MVP:
1. Tenant AI
2. Client Manager AI
3. Sales AI
4. lightweight/on-demand Analyst

Data Manager AI tidak otomatis masuk MVP.

## Pertanyaan
- Apakah Tenant AI benar-benar perlu pada MVP?
- Apakah Tenant AI dan Owner AI menggunakan arsitektur agent yang sama dengan scope berbeda?
- Apa exact authority masing-masing?
- Apakah Tenant AI dapat membuat workflow?
- Apakah Tenant AI dapat mengubah business data?
- Apa yang dapat dilakukan specialist tanpa Tenant AI?
- Bagaimana agent dibuat/diaktifkan/dinonaktifkan?
- Bagaimana tenant memilih AI capability?
- Apakah AI capability merupakan feature, agent, app, atau entitlement?

---

# 9. AI AUTHORITY

Prinsip:
Authority is non-transitive and explicitly scoped.

Delegasi:
- tidak meningkatkan authority
- hanya mempertahankan atau mempersempit authority

Risk levels:
- LOW
- MEDIUM
- HIGH
- CRITICAL

LOW:
- FAQ
- summary
- recommendation
- internal task

MEDIUM:
- confirmation/policy

HIGH:
- Human Owner approval

CRITICAL:
- human-only

## Pertanyaan besar
- Apa daftar tindakan lengkap untuk setiap risk level?
- Apakah risk level configurable per tenant?
- Siapa yang menentukan risk?
- Apakah tenant dapat menurunkan/menaikkan autonomy?
- Apa perbedaan authority dan permission?
- Apa perbedaan authority, permission, entitlement, operating mode?
- Apakah subscription hanya menentukan capability, sementara permission menentukan access?
- Bagaimana budget membatasi authority?
- Apa yang terjadi saat authority/budget/time limit habis?

---

# 10. TENANT OPERATING MODE

Proposed:
1. Manual
2. Semi-Autonomous
3. Autonomous

Manual:
AI menganalisis/rekomendasi/draft; execution menunggu approval bila berlaku.

Semi-Autonomous:
routine approved work dapat otomatis; selected actions perlu approval.

Autonomous:
approved routine workflows dapat berjalan tanpa instruksi per aksi.

Important:
Mode mengatur operational autonomy, bukan security authority.

## Pertanyaan
- Apa exact capability setiap mode?
- Apakah mode berlaku global atau per agent/workflow?
- Apakah mode dapat berbeda per channel?
- Apakah mode dapat berbeda per action?
- Apakah customer dapat mengubah mode atau hanya Owner/Admin?
- Bagaimana mode berinteraksi dengan risk level?
- Apa default mode?
- Apa safe fallback mode?

---

# 11. SOURCE OF TRUTH

Hierarchy:
1. Database/System
2. Business Configuration
3. Approved Knowledge
4. Conversation Context
5. AI Reasoning

AI bukan source of truth untuk:
- price
- stock
- invoice
- payment
- subscription
- entitlement
- customer ID
- order status
- payment status
- configuration
- permission

## Audit questions
- Apa authoritative source untuk setiap domain?
- Apakah Business Configuration termasuk DB atau layer berbeda?
- Apa jika DB dan external provider berbeda?
- Apa jika dua official sources berbeda?
- Apa source priority per field?
- Siapa yang boleh mengubah source of truth?
- Bagaimana conflict resolution?
- Bagaimana versioning?
- Bagaimana rollback?

---

# 12. BUSINESS DATA

Konsep:
- business profile
- products
- variants
- price
- stock
- customers
- orders
- policies
- configuration

Import:
Upload/Connect
→ Parse
→ Validate
→ Preview
→ Confirm
→ Persist
→ Audit

AI extraction:
Photo
→ AI extraction
→ draft
→ client review
→ official data

Import statuses:
- VALID
- NEEDS_REVIEW
- CONFLICT
- ERROR

## Pertanyaan
- Field wajib apa saja untuk setiap business type?
- Field mana sensitive?
- Apa exact validation rules?
- Apa yang boleh auto-fix?
- Apa yang selalu membutuhkan confirmation?
- Bagaimana duplicate detection?
- Bagaimana bulk import?
- Bagaimana partial failure?
- Bagaimana rollback?
- Bagaimana schema evolution?
- Bagaimana data archival/deletion?
- Bagaimana conflict resolution?

---

# 13. KNOWLEDGE SYSTEM

Knowledge types:
- FAQ
- SOP
- Policy
- Product Information
- Promotion
- Business Information
- Customer-facing Information
- Internal Information
- Legal/Compliance
- Operational Instructions

Lifecycle:
DRAFT
→ VALIDATING
→ APPROVED
→ ACTIVE
→ OUTDATED
→ ARCHIVED

Knowledge harus memiliki:
- source
- owner
- status
- version
- timestamp
- expiry
- approval
- confidence
- change history
- tenant ownership
- audience/visibility

## Pertanyaan
- Siapa yang dapat membuat knowledge?
- Siapa yang approve?
- Apakah AI boleh membuat draft?
- Apakah knowledge tertentu wajib approval?
- Bagaimana conflict antar knowledge?
- Bagaimana expiry otomatis?
- Bagaimana retrieval threshold?
- Bagaimana citation/provenance?
- Bagaimana knowledge injection dicegah?
- Apa perbedaan Business Data dan Knowledge secara formal?

---

# 14. MEMORY SYSTEM

Memory:
- conversation context
- Business Memory
- Client/Customer Memory
- system memory where applicable

Business Memory:
- owner decisions
- policies
- strategies
- preferences
- constraints
- long-term context

Rules:
- selective
- current explicit info wins
- historical context preserved when appropriate
- tenant isolated
- memory is not transactional truth

## Pertanyaan
- Apa exact schema memory?
- Apa yang boleh menjadi memory?
- Siapa yang boleh membuat memory?
- Bagaimana confidence?
- Kapan memory expired?
- Bagaimana conflict?
- Bagaimana delete/anonymize?
- Bagaimana memory antar conversation?
- Bagaimana customer memory dipisahkan dari tenant/business memory?
- Apakah memory MVP atau future?
- Bagaimana memory memengaruhi AI context tanpa menjadi source of truth?

---

# 15. CONTEXT ASSEMBLY

Candidate context:
- tenant
- trusted actor
- permissions
- business profile
- customer
- conversation
- product/order/cart
- approved knowledge
- Business Memory
- Client Memory
- authoritative facts
- task/workflow state

Context must distinguish:
FACTS
RULES
MEMORY
CONVERSATION
USER INPUT
AI INSTRUCTIONS

Minimum necessary context.

## Pertanyaan
- Apa exact context assembly order?
- Apa priority jika context conflict?
- Apa token budget?
- Apa relevance threshold?
- Bagaimana sensitive data filtering?
- Siapa yang melakukan authorization sebelum context dikirim ke model?
- Bagaimana prompt injection dari data/knowledge/tool result ditangani?
- Bagaimana context versioning?
- Bagaimana audit context tanpa menyimpan data sensitif berlebihan?

---

# 16. CUSTOMER CONVERSATION

Target:
Customer
→ Channel Adapter
→ Universal Message
→ Tenant Resolution
→ Customer Identity
→ Conversation
→ Router
→ Deterministic Business Logic
→ AI if required
→ Response
→ Channel Adapter
→ Customer

Router candidate intents:
- greeting
- product list
- price
- stock
- variant
- product info
- order
- cart
- FAQ
- handoff
- unknown

## Pertanyaan
- Apakah router deterministic, AI-assisted, atau hybrid?
- Apa confidence threshold?
- Apa fallback unknown?
- Bagaimana intent berubah di tengah conversation?
- Bagaimana multiple simultaneous intents?
- Bagaimana conversation locking?
- Bagaimana human takeover?
- Bagaimana duplicate inbound message?
- Bagaimana out-of-order message?
- Bagaimana customer identity antar channel?

---

# 17. HUMAN HANDOFF

Handoff state:
AI_HANDOFF_REQUESTED
→ HUMAN_ASSIGNED
→ HUMAN_IN_PROGRESS
→ RESOLVED
→ VERIFY
→ RESUME_AI / CLOSE

Triggers:
- customer asks human
- complaint
- sensitive case
- repeated uncertainty
- high-risk action
- low confidence
- policy requires human

Human takeover:
AI replies paused according to policy.

## Pertanyaan
- Siapa yang menerima handoff?
- Assignment rules?
- Queue?
- Business hours?
- SLA?
- Priority?
- What if no human available?
- Apakah AI boleh membantu human internally?
- Bagaimana handback?
- Apakah human takeover berlaku per conversation atau per customer?
- Berapa lama AI pause?
- Apa yang terjadi setelah human tidak aktif?

---

# 18. ORDER / CART / PAYMENT

Order:
Intent
→ Product/Variant Validation
→ Stock
→ Cart
→ Customer Confirmation
→ Order

Checkout:
- deterministic price
- stock validation
- customer/address where required
- payment amount
- order/payment state

Payment:
PAYMENT_PENDING
→ verified gateway/webhook
→ PAID

Customer screenshot/proof is not payment authority.

Payment must handle:
- duplicate webhook
- replay
- timeout
- external success/internal failure
- reconciliation
- idempotency

## Pertanyaan
- Apa exact order state machine?
- Apa exact cart state?
- Kapan stock di-reserve?
- Bagaimana race condition?
- Bagaimana expired cart?
- Bagaimana payment timeout?
- Apa order vs invoice vs payment?
- Apa partial payment?
- Apa COD?
- Apa manual transfer?
- Bagaimana refund?
- Bagaimana return/exchange?
- Bagaimana cancellation?
- Bagaimana payment reconciliation?

---

# 19. BILLING / SUBSCRIPTION / ENTITLEMENT

Concepts:
- Plan
- PlanFeature
- PlanLimit
- Addon
- TenantAddon
- Subscription
- SubscriptionHistory
- Invoice
- InvoiceItem
- Payment
- Usage
- Entitlement

Subscription states:
- ACTIVE
- PAYMENT_PENDING
- GRACE
- RESTRICTED
- SUSPENDED
- EXPIRED
- ARCHIVED

Important:
Subscription state != operational/bot state.

## Pertanyaan
- Exact state transitions?
- Trial behavior?
- Default 7-day trial sudah dikunci atau masih perlu konfirmasi?
- Grace period duration?
- Restriction matrix?
- Data retention after expiry?
- Reactivation?
- Upgrade proration?
- Downgrade effective time?
- Add-on expiry?
- Payment failure?
- Invoice lifecycle?
- Tax?
- Currency?
- Refund?
- Overage?
- Credit rollover?
- Usage reset period?

---

# 20. WORKFLOW ENGINE

Model:
TRIGGER
→ CONDITION
→ ACTION
→ RESULT
→ NEXT STEP

Protections:
- retry
- timeout
- idempotency
- duplicate protection
- loop protection
- permission
- cost/rate limits
- kill switch
- versioning
- execution history

Retry:
- bounded
- classified
- exponential backoff/jitter where appropriate
- safe checkpoint

## Pertanyaan
- Apa workflow object lengkap?
- Apa action catalog?
- Apa condition language?
- Apakah user dapat membuat workflow natural-language?
- Bagaimana AI menghasilkan draft workflow?
- Apa yang wajib approval?
- Bagaimana workflow versioning?
- Bagaimana scheduled workflow timezone?
- Bagaimana missed execution?
- Bagaimana concurrency?
- Bagaimana rollback?
- Bagaimana workflow dependency?
- Bagaimana kill switch scope?

---

# 21. EVENT BUS

Event = sesuatu yang telah terjadi.

Metadata:
- event_id
- event_type
- tenant_id
- source
- timestamp
- payload
- correlation_id
- causation_id
- schema_version
- idempotency key where relevant

Consumers:
- Workflow
- Task
- Notification
- Analytics
- AI

## Pertanyaan
- Event catalog?
- Which events are public/internal?
- Ordering guarantees?
- Delivery guarantee?
- Dead-letter?
- Retention?
- Replay?
- Versioning?
- Event ownership?
- Sensitive data in event payload?
- Cross-tenant event protection?

---

# 22. TASK SYSTEM

Task:
- objective
- assignee/agent/role
- priority
- context
- deadline
- status
- result
- validation

Lifecycle:
CREATED
→ ASSIGNED
→ IN_PROGRESS
→ WAITING_DATA / WAITING_APPROVAL
→ COMPLETED

Error:
FAILED / BLOCKED / CANCELLED

## Pertanyaan
- Task vs workflow boundary?
- Who can create?
- Who can assign?
- Delegation depth?
- Task dependencies?
- SLA?
- Priority rules?
- Reassignment?
- Expiry?
- Human vs AI task?
- Validation of completion?
- Duplicate task prevention?

---

# 23. APPROVAL SYSTEM

Approval:
- action
- target
- reason
- expected result
- risk
- evidence
- confidence
- requester
- status
- timestamp

Statuses:
PENDING
APPROVED
REJECTED
MODIFIED
EXPIRED
CANCELLED

Approval is action/target/time/parameter bound.

## Pertanyaan
- Approval authority matrix?
- Single approver or multi-approver?
- Delegation?
- Expiry?
- Modification semantics?
- Emergency approval?
- What counts as valid owner approval?
- Can approval be revoked?
- What happens if action parameters change?
- How is approval displayed to user?
- How is approval audited?

---

# 24. NOTIFICATION / FOLLOW-UP

Event != notification.

Notification requires:
- recipient
- channel
- priority
- purpose
- content/template
- timing
- permissions
- delivery state

Follow-up:
- bounded
- cooldown
- quiet hours
- stop conditions
- opt-out enforcement
- inbound response takes priority

## Pertanyaan
- Notification preference model?
- Global vs tenant vs customer preference?
- Quiet hours timezone?
- Message frequency?
- Marketing vs transactional communication?
- WhatsApp provider policy?
- Retry?
- Delivery state?
- Template management?
- Opt-out semantics?
- What counts as consent?

---

# 25. INTEGRATIONS

Universal Integration Foundation:
- Integration
- IntegrationConnection
- IntegrationCredential
- IntegrationExecution
- WebhookConfig
- REST adapter
- Webhook adapter
- provider adapters
- encrypted credential reference
- execution tracking
- EventBus
- audit
- tenant isolation

Providers mentioned:
- WhatsApp Cloud API
- Google Calendar
- Google Sheets
- payment provider / Midtrans
- future CRM/other providers
- future channels

## Pertanyaan
- Integration capability registry?
- Connection lifecycle?
- OAuth?
- Credential rotation?
- Credential revocation?
- Provider rate limits?
- Health checks?
- Retry policy?
- Reconciliation?
- Provider-specific limitations?
- What integrations are truly MVP?

---

# 26. WHATSAPP

WhatsApp is first commercial channel, not architecture boundary.

Responsibilities:
- receive
- normalize
- send
- authentication/verification
- tenant mapping
- connection lifecycle
- rate handling
- retries
- audit
- usage
- entitlement

Connection:
NOT_CONNECTED
→ CONNECTING
→ CONNECTED
→ VERIFYING
→ ACTIVE

Failures:
FAILED
DISCONNECTED
EXPIRED
SUSPENDED

## Pertanyaan
- One tenant multiple numbers? Already directed YES.
- Number role?
- Inbound identity mapping?
- Outbound routing?
- Business hours?
- Template requirements?
- Media handling?
- Message limits?
- Provider billing?
- Delivery status?
- Duplicate webhook?
- Reconciliation?
- What happens when number disconnects?

---

# 27. CALENDAR / BOOKING

Google Calendar is first calendar integration.

Capabilities mentioned:
- OAuth
- token refresh
- free/busy
- event CRUD
- timezone
- workflow actions
- Owner AI tools
- API
- events
- permissions

Booking must recheck availability at commit time.

## Pertanyaan
- Is booking MVP?
- Which business types use booking?
- Booking object?
- Appointment lifecycle?
- Cancellation policy?
- Reschedule?
- Buffer time?
- Working hours?
- Multiple calendars?
- Timezone?
- Race condition?
- Payment/deposit?
- Reminders?

---

# 28. ANALYTICS / BI

Layers:
DATA
→ ANALYSIS
→ INTELLIGENCE

Data = what happened.
Analysis = why/how.
Intelligence = what should we do.

Potential metrics:
- revenue
- conversion
- churn
- usage
- AI cost
- trends
- anomalies
- forecast
- health score

Health Score example:
Usage 20%
Reliability 20%
Engagement 15%
Business Result 20%
Support 10%
Payment 10%
Adoption 5%

## Pertanyaan
- Apakah formula health score final?
- Metric definitions?
- Timezone?
- Attribution?
- Data freshness?
- Historical snapshots?
- KPI versioning?
- Forecast minimum data?
- Confidence?
- Anomaly baseline?
- Who can see which analytics?
- Cross-tenant analytics rules?

---

# 29. OWNER AI / BUSINESS INTELLIGENCE

Owner AI:
Observe
→ Understand
→ Prioritize
→ Delegate
→ Analyze
→ Recommend
→ Approval
→ Act if permitted
→ Verify
→ Learn

Capabilities:
- business overview
- daily brief
- weekly review
- client health
- usage
- revenue
- churn risk
- payment issues
- support trends
- automation health
- AI cost
- recommendations
- task coordination
- approval requests
- business memory

Owner AI is not unrestricted admin.

## Pertanyaan
- Exact Owner AI authority?
- Which actions automatic?
- Which require approval?
- Which are impossible for AI?
- How does Owner AI access cross-tenant information?
- How does it avoid data dump?
- How does it prioritize alerts?
- What budget can it operate within?
- What is its operating schedule?
- What happens if it fails?
- How does Human Owner override it?
- What is the emergency stop?

---

# 30. AI SALES

Responsibilities:
- prospect handling
- qualification
- product recommendation
- package recommendation
- proposal
- follow-up
- objection handling
- conversion assistance

Rules:
- no fabricated pricing/promos
- no unauthorized discount
- no entitlement mutation
- non-pressuring sales

## Questions
- Exact sales funnel?
- Lead scoring?
- Proposal lifecycle?
- Negotiation authority?
- Discount thresholds?
- Follow-up rules?
- Lost reason?
- Win-back?
- Handoff to Client Manager?
- Which functions are MVP?

---

# 31. AI CLIENT MANAGER

Responsibilities:
- onboarding
- requirement collection
- validation
- reminders
- configuration assistance
- lifecycle management
- renewal
- churn prevention

## Questions
- Is Client Manager mandatory for MVP?
- What can it execute autonomously?
- What is human handoff?
- What is its authority?
- What happens after subscription expiry?
- How does it distinguish onboarding state from subscription state?
- How does it resume after pause?

---

# 32. AI SUPPORT

Responsibilities:
- support
- troubleshooting
- complaint classification
- escalation
- handoff
- summaries
- incident analysis

Rules:
- evidence-based diagnosis
- symptom != root cause
- hypothesis != confirmed cause
- production-critical mutation requires permission/approval

## Questions
- What logs/data can it access?
- What actions can it execute?
- Can it restart/reconnect?
- Can it disable workflow?
- What is automatic containment?
- What requires human approval?
- How are incidents escalated?

---

# 33. AI DATA MANAGER

Responsibilities:
- organization
- import
- validation
- normalization
- quality detection
- change request preparation

Discovery says this may be excluded from lean tenant MVP.

## Questions
- Is it actually needed?
- Which deterministic functions make it unnecessary?
- Is AI adding enough value to justify cost?
- Should it remain internal only?
- Could it be a capability/app rather than always-running agent?

---

# 34. AI ANALYST

Responsibilities:
- analytics interpretation
- trend explanation
- anomaly investigation
- recommendations
- KPI summaries
- business insights

Must distinguish:
- fact
- inference
- recommendation
- uncertainty

## Questions
- On-demand or proactive?
- Tenant vs Owner scope?
- Which metrics are supported MVP?
- Does Analyst create tasks?
- Can Analyst trigger workflows?
- What evidence must accompany recommendations?

---

# 35. SECURITY

Foundations:
- authentication
- authorization
- tenant isolation
- RBAC
- least privilege
- secure credentials
- webhook verification
- rate limiting
- audit
- approval
- kill switch
- secure errors
- session security
- 2FA where appropriate
- IP restrictions for higher tiers

AI must not receive unrestricted:
- SQL
- shell
- Python
- filesystem
- external APIs
- credentials

## Questions
- Full threat model?
- Trust boundaries?
- Prompt injection?
- Tool-result injection?
- Confused deputy?
- Agent-to-agent injection?
- Secret proxying?
- Approval self-authorization?
- Session hijacking?
- CSRF?
- webhook replay?
- data export?
- tenant deletion?
- backup access?
- admin abuse?
- audit tampering?

---

# 36. OBSERVABILITY / AUDIT

Observability:
- uptime
- latency
- errors
- AI latency
- AI cost
- workflow failure
- queue health
- DB health
- WhatsApp health
- integration health
- important audit events

Audit should reconstruct:
WHO
WHAT
WHEN
TENANT
PREVIOUS STATE
NEW STATE
WHY
SOURCE
APPROVAL
RESULT

## Questions
- What must be audited?
- What must be logged?
- Retention?
- Privacy?
- Tenant visibility?
- Owner visibility?
- Correlation IDs?
- Incident trace?
- AI decision provenance?
- Cost attribution?
- Tool call evidence?
- How to prevent logs becoming sensitive-data leakage?

---

# 37. RELIABILITY / INCIDENT / RECOVERY

Incident:
DETECT
→ CONTAIN
→ DIAGNOSE
→ RECOVER
→ VERIFY
→ REPORT
→ LEARN

Reliability:
- health checks
- dependency checks
- timeout
- retry
- idempotency
- backups
- restore testing
- recovery procedure

## Questions
- Exact RPO/RTO?
- Backup frequency?
- Retention?
- Restore procedure?
- Disaster scenario?
- Region failure?
- Database corruption?
- provider outage?
- AI provider outage?
- WhatsApp outage?
- queue failure?
- duplicate events?
- partial system failure?
- safe degraded mode?

---

# 38. DATA LIFECYCLE

Need formal policy for:
- creation
- validation
- active use
- update
- versioning
- archival
- deletion
- anonymization
- retention
- backup
- restoration

## Questions
- Who owns tenant data?
- What data does platform own?
- What is retained after cancellation?
- What is deleted?
- What is anonymized?
- What is legally retained?
- How is export handled?
- How is tenant deletion verified?
- What data may be used for aggregate learning?
- Is explicit consent required?

---

# 39. UX / DASHBOARD

Owner dashboard candidate:
- Overview
- Owner AI
- Clients
- Sales
- Revenue
- Subscriptions
- Support
- Tasks
- Approvals
- Automation
- AI Usage
- Analytics
- Platform Health
- Integrations
- Audit

Tenant dashboard:
- Inbox
- Customers
- Products
- Orders
- AI
- Knowledge
- Automation
- Analytics
- Team
- Integrations
- WhatsApp
- Subscription
- Usage
- Settings

## Questions
- What is MVP dashboard?
- What must be mobile-first?
- What is self-service?
- Which settings are dangerous?
- How are approvals shown?
- How are AI actions explained?
- How are usage/cost displayed?
- How is readiness shown?

---

# 40. SELF-SERVICE

Target:
Discover
→ Choose plan
→ Register
→ Pay
→ Provision
→ Enter data
→ Import knowledge
→ Connect WhatsApp
→ Test AI
→ Activate
→ Monitor
→ Upgrade
→ Add-on
→ Billing

Goal:
Normal flows should not require manual developer intervention.

## Questions
- What still requires Human Owner?
- What requires support?
- What can be fully self-service in MVP?
- What information must be collected?
- How does onboarding adapt by business type?
- How is incomplete onboarding handled?

---

# 41. STATE MACHINE REGISTER

States found across documents must be consolidated.

Potential state domains:
1. Client lifecycle
2. Subscription lifecycle
3. Payment lifecycle
4. Order lifecycle
5. Cart lifecycle
6. Onboarding lifecycle
7. Integration lifecycle
8. WhatsApp connection lifecycle
9. Workflow lifecycle
10. Task lifecycle
11. Approval lifecycle
12. Knowledge lifecycle
13. Memory lifecycle
14. Incident lifecycle
15. Conversation/handoff lifecycle
16. Notification delivery lifecycle

## CRITICAL AUDIT TASK
Do NOT mix state domains.

Examples:
- Subscription ACTIVE does not mean service ACTIVE.
- WhatsApp CONNECTED does not mean tenant READY.
- Onboarding PAUSED does not mean subscription paused.
- Payment PAID does not automatically mean client fully operational.

For each state machine later define:
- states
- entry conditions
- exit conditions
- allowed transitions
- forbidden transitions
- actor
- authorization
- event
- side effects
- retry
- timeout
- recovery
- audit
- terminal states

---

# 42. CROSS-SYSTEM DEPENDENCY MAP

Need to formally map:

Plan
→ Subscription
→ Entitlement
→ Requirement
→ Onboarding
→ Configuration
→ Integration
→ Readiness
→ Activation
→ Operations
→ Usage
→ Billing
→ Renewal

And:

Channel
→ Universal Message
→ Tenant Resolution
→ Customer
→ Conversation
→ Router
→ Business Data
→ Workflow/AI
→ Response
→ Event
→ Analytics

And:

Data
→ Analysis
→ Insight
→ Recommendation
→ Decision
→ Action
→ Result
→ Evaluation
→ Memory

## Questions
- Where are boundaries?
- Which subsystem owns each fact?
- Which subsystem may mutate it?
- Which subsystem only reads it?
- Which events connect them?
- Which dependencies are mandatory?
- Which can operate independently?

---

# 43. MAJOR FINDINGS FROM STAGE 0

## CONFLICTS

### CON-001 — Old implementation context vs new pre-coding objective
Blueprint contains implementation status and coding direction, while current project objective is to redesign the SaaS blueprint before coding.

Action:
Separate conceptual truth from historical implementation status.

### CON-002 — MVP boundary is not fully consistent
Different documents imply different MVP capability sets.

Action:
Require explicit MVP definition.

### CON-003 — AI scope differs between Blueprint and Discovery
Discovery proposes leaner tenant AI scope.

Action:
Resolve before final Blueprint.

### CON-004 — Universal Core ownership/boundary was corrected
Discovery explicitly rejects the older interpretation that Universal Core operates the Owner's own business.

Action:
Preserve corrected separation:
Owner business = Internal AI ecosystem.
Tenant business = Universal Core + Tenant AI + Tenant Specialists.

### CON-005 — Lifecycle representations differ
Client lifecycle appears with different state names and granularity across documents.

Action:
Create one canonical lifecycle model.

---

# 44. AMBIGUITIES

### AMB-001
What exactly is the MVP product sold to the first paying customer?

### AMB-002
Is Owner AI part of MVP or V2?

### AMB-003
Is Tenant AI mandatory for MVP?

### AMB-004
Are Starter/Pro/Business/Enterprise all launch plans or staged plans?

### AMB-005
Are listed prices final, target, or placeholders?

### AMB-006
Is memory MVP, V1.5, or V2?

### AMB-007
Is booking/calendar MVP?

### AMB-008
Is Google Sheets MVP?

### AMB-009
Is AI Data Manager MVP?

### AMB-010
Is AI Support customer-facing MVP or internal support only?

### AMB-011
What exactly constitutes "AI credit"?

### AMB-012
What is the exact distinction between AI capability, Agent, Feature, Module, App, Plan Feature, Entitlement and Add-on?

### AMB-013
What exactly is a Client vs Tenant in every subsystem?

### AMB-014
What is the canonical customer identity model?

### AMB-015
What is the canonical business policy model?

### AMB-016
What is the canonical workflow/action model?

---

# 45. MISSING REQUIREMENTS

These are not necessarily errors; they are areas where the current source material does not yet give enough detail.

1. Complete MVP acceptance criteria.
2. Complete persona/actor matrix.
3. Complete authority matrix.
4. Complete permission matrix.
5. Complete entitlement matrix.
6. Complete plan-feature matrix.
7. Complete billing state machine.
8. Complete payment method policy.
9. Complete tax/invoice policy.
10. Complete customer identity model.
11. Complete branch/multi-business model.
12. Complete data retention policy.
13. Complete privacy/data ownership policy.
14. Complete deletion/export policy.
15. Complete AI budget model.
16. Complete AI operating mode matrix.
17. Complete workflow action catalog.
18. Complete notification policy.
19. Complete consent/opt-out model.
20. Complete booking model if booking is supported.
21. Complete support SLA model.
22. Complete incident severity model.
23. Complete backup/RPO/RTO policy.
24. Complete degradation/fallback behavior.
25. Complete integration capability matrix.
26. Complete API product boundary.
27. Complete dashboard MVP scope.
28. Complete onboarding requirement catalog per business type.
29. Complete readiness criteria per capability.
30. Complete cross-system dependency graph.
31. Complete state machine registry.
32. Complete error taxonomy.
33. Complete audit event taxonomy.
34. Complete data classification/sensitivity model.
35. Complete AI evaluation/readiness model.
36. Complete model/provider fallback policy.
37. Complete cost model.
38. Complete commercial unit economics.

---

# 46. POTENTIAL DESIGN RISKS

1. Overbuilding the final vision before validating MVP.
2. Treating every AI agent as mandatory.
3. Confusing capability with authority.
4. Confusing entitlement with permission.
5. Mixing Owner business and tenant business.
6. Mixing subscription state with operational state.
7. Letting AI become source of truth.
8. Duplicate subsystem creation.
9. Too many future features entering MVP.
10. Undefined state transitions.
11. Undefined conflict resolution.
12. Undefined data retention.
13. Undefined AI cost boundaries.
14. Undefined fallback when AI provider fails.
15. Undefined provider outage behavior.
16. Undefined WhatsApp policy/limits.
17. Undefined consent/communication rules.
18. Undefined identity resolution.
19. Undefined branch/multi-business semantics.
20. Too much autonomy without exact authority boundaries.
21. Overcomplicated architecture before revenue validates it.
22. Security assumptions depending on LLM behavior.
23. Incomplete observability.
24. Lack of deterministic acceptance criteria.
25. Using historical implementation status as if it were current product truth.

---

# 47. DOCUMENTATION / SOURCE ISSUES

### DOC-001
`AI_BOS_LOCKED_DECISIONS_ACT_001_090.md` contains ACT-001 through ACT-410 despite filename indicating 001_090.

### DOC-002
Blueprint v1.1 calls itself a living canonical document but also contains implementation snapshot/history.

### DOC-003
Operational Flow is explicitly Draft for Review.

### DOC-004
Discovery Notes are not locked.

### DOC-005
Master Reference calls itself a quick-reference "kiblat" but says it is not implementation source of truth.

### DOC-006
There are duplicate older Blueprint versions.

### DOC-007
The existing documents mix:
- product definition
- architecture
- operational behavior
- implementation history
- development instructions

These should be separated in the new documentation structure.

---

# 48. NEW MASTER DOCUMENT STRUCTURE

The eventual final documentation should be separated into:

01_PRODUCT_VISION
02_BUSINESS_MODEL
03_CUSTOMER_AND_PERSONA
04_PRODUCT_REQUIREMENTS
05_SAAS_STRUCTURE
06_MVP_SCOPE
07_SYSTEM_ARCHITECTURE
08_AI_ARCHITECTURE
09_DATA_ARCHITECTURE
10_KNOWLEDGE_AND_MEMORY
11_BUSINESS_OPERATIONS
12_WORKFLOW_AND_EVENT_SYSTEM
13_BILLING_AND_ENTITLEMENT
14_INTEGRATIONS_AND_CHANNELS
15_SECURITY_AND_TRUST
16_OPERATIONAL_STATE_MACHINES
17_FAILURE_RECOVERY
18_UX_AND_DASHBOARD
19_ANALYTICS_AND_BI
20_OBSERVABILITY_AND_AUDIT
21_COST_AND_UNIT_ECONOMICS
22_TEST_AND_ACCEPTANCE_SPECIFICATION
23_FUTURE_ROADMAP
24_DECISION_REGISTER
25_REQUIREMENT_TRACEABILITY
26_FINAL_SAAS_BLUEPRINT

Coding instructions should NOT be placed in these documents.

---

# 49. AUDIT REGISTERS

## Requirement Register
REQ-xxx
Description:
Source:
Status:
Decision:
Affected systems:

## Ambiguity Register
AMB-xxx
Question:
Why ambiguous:
Possible interpretations:
Required owner decision:
Status:

## Conflict Register
CON-xxx
Source A:
Source B:
Conflict:
Impact:
Required decision:
Status:

## Gap Register
GAP-xxx
Missing:
Why important:
Affected area:
Priority:
Resolution:

## Risk Register
RISK-xxx
Risk:
Cause:
Impact:
Probability:
Mitigation:
Status:

## Decision Register
DEC-xxx
Question:
Options:
Recommendation:
Owner decision:
Date:
Status:

## Assumption Register
ASM-xxx
Assumption:
Why needed:
Evidence:
Risk:
Owner confirmation:
Status:

---

# 50. PROCESS FOR FUTURE STAGES

Every stage follows:

READ
→ UNDERSTAND
→ MAP
→ CROSS-CHECK
→ IDENTIFY
→ QUESTION
→ RESOLVE
→ STRUCTURE
→ VALIDATE
→ SAVE

No important answer should exist only in chat.

After each stage:
1. Update this master knowledge/audit file.
2. Save new decisions.
3. Update registers.
4. Mark resolved vs unresolved.
5. Preserve historical decisions.
6. Re-check cross-stage consistency.

---

# 51. FINAL END STATE

The project is NOT ready for coding until the following exists:

[ ] Product definition complete
[ ] Business model complete
[ ] Customer definition complete
[ ] MVP scope explicit
[ ] Functional requirements complete
[ ] Non-functional requirements complete
[ ] Actor model complete
[ ] Permission model complete
[ ] Authority model complete
[ ] Entitlement model complete
[ ] Plan/add-on model complete
[ ] AI architecture complete
[ ] Data model concept complete
[ ] Knowledge model complete
[ ] Memory model complete
[ ] Conversation model complete
[ ] Order/payment model complete
[ ] Billing model complete
[ ] Workflow model complete
[ ] Event model complete
[ ] Task model complete
[ ] Approval model complete
[ ] Integration model complete
[ ] WhatsApp model complete
[ ] Security model complete
[ ] State machines complete
[ ] Failure/recovery model complete
[ ] Observability model complete
[ ] Audit model complete
[ ] Cost model complete
[ ] UX/dashboard scope complete
[ ] MVP acceptance criteria complete
[ ] Future scope separated
[ ] All major conflicts resolved
[ ] All critical ambiguities resolved
[ ] Critical gaps resolved
[ ] Cross-system dependencies validated
[ ] Final Blueprint assembled
[ ] Final Blueprint consistency audit passed
[ ] Human Owner approval obtained

ONLY AFTER THIS:
→ implementation planning
→ repository architecture
→ GitHub
→ coding agent
→ implementation

---

# 52. STAGE ANSWER LOG

## Stage 0
Status: IN PROGRESS
Date: 2026-09-12

### Current objective
Build a clean, single audit/knowledge foundation before asking detailed product/system questions.

### Owner answers
[Belum ada]

### Decisions created
[Belum ada]

### Resolved findings
[Belum ada]

### Remaining critical questions
1. Define the actual commercial MVP.
2. Define the boundary between Platform, Tenant, Customer.
3. Define Internal AI vs Tenant AI scope.
4. Define exact meaning of Feature/Module/Agent/App/Entitlement/Add-on.
5. Define canonical lifecycle/state domains.
6. Define exact authority/permission relationship.
7. Define billing/subscription rules.
8. Define data/knowledge/memory boundaries.
9. Define MVP integrations.
10. Define the final product surface.

---

# 53. GOLDEN RULE

> **Kita tidak sedang mengumpulkan sebanyak mungkin fitur. Kita sedang memastikan seluruh bagian dari satu SaaS AI BOS saling cocok, memiliki tujuan, memiliki batas, memiliki sumber kebenaran, memiliki alur, memiliki kondisi gagal, dan dapat dibangun tanpa harus menebak.**

This file is the working compass.
The final Blueprint will be produced only after the audit questions and decisions are resolved.
