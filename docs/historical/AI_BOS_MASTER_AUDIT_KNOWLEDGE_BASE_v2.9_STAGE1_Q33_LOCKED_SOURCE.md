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


---

# Q27 — POLICY & RULE SCOPE ARCHITECTURE — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q27 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Policy and rule memiliki scope yang eksplisit.
2. Internal/platform policy dipisahkan dari tenant policy.
3. System security/non-negotiable constraints tidak dapat di-override tenant.
4. Tenant policy hanya berlaku dalam tenant scope dan platform authority ceiling.
5. Workflow/task policy dapat memberikan constraint tambahan.
6. Agent Contract membatasi kemampuan agent.
7. Transaction/domain truth tetap authoritative dan deterministic.
8. Policy ≠ permission.
9. Permission ≠ authority.
10. Authority ≠ approval.
11. Recommendation ≠ policy.
12. AI tidak boleh self-authorize atau memperluas policy/permission.
13. Policy memiliki lifecycle dan versioning.
14. Policy memiliki applicability/scope/condition yang jelas.
15. Conflict tidak boleh diselesaikan dengan tebakan.
16. Mandatory conflict → stop affected action dan escalate.
17. Configurable/default policy harus dibedakan dari mandatory policy.
18. Policy evaluation harus mempertimbangkan scope, authority, applicability, risk, permission, approval, dan domain truth.
19. Policy tidak boleh digunakan untuk mengalahkan tenant isolation/security boundary.
20. Perubahan policy penting harus authorized, validated, versioned, auditable, dan diverifikasi.
21. Detail Authority Matrix + Policy Precedence Matrix + Conflict Resolution Matrix tetap menjadi desain lanjutan, bukan dianggap telah selesai oleh Q27.

## Policy Scope Model

AI BOS menggunakan beberapa scope konseptual:

- **System Policy** — aturan fundamental platform, termasuk security, tenant isolation, authorization, secret protection, audit, dan mandatory safety constraints.
- **Platform Business Policy** — aturan bisnis AI BOS sebagai penyedia platform.
- **Tenant Policy** — aturan bisnis milik masing-masing tenant.
- **Workflow/Task Policy** — constraint yang berlaku pada proses atau pekerjaan tertentu.
- **Agent Policy / Agent Contract** — batas capability, responsibility, data access, tools, authority, risk, escalation, verification, dan failure behavior agent.
- **Transaction/Domain Rule** — aturan authoritative/deterministic pada domain seperti stock, order, payment, subscription, entitlement, dan transaksi lainnya.

## Conflict & Precedence Principles

Tidak digunakan satu hierarchy sederhana yang menganggap semua policy dengan scope lebih tinggi otomatis dapat membatalkan semua policy di bawahnya.

Evaluasi policy mempertimbangkan:

```text
SCOPE
→ AUTHORITY
→ APPLICABILITY
→ MANDATORY CONSTRAINTS
→ PERMISSION
→ RISK
→ APPROVAL
→ DOMAIN TRUTH
→ ACTION DECISION
```

Contoh prinsip:

- System security mengalahkan tenant preference.
- Tenant policy tidak dapat mengubah deterministic transaction truth.
- Tenant policy tidak otomatis memberikan permission kepada agent.
- Agent Contract tidak dapat diperluas hanya karena tenant meminta capability tambahan.
- AI recommendation tidak otomatis menjadi policy.
- Conflict/ambiguity pada policy penting tidak boleh ditebak atau diselesaikan diam-diam.

## Policy Lifecycle

Policy penting harus dapat memiliki lifecycle:

```text
DRAFT
→ VALIDATING
→ APPROVED
→ ACTIVE
→ UPDATED / SUPERSEDED
→ ARCHIVED
```

Policy penting perlu dapat ditelusuri minimal berdasarkan:

- policy identity
- scope
- tenant scope jika relevan
- domain
- version
- status
- source
- effective period
- creator/updater
- approver jika diperlukan
- audit linkage

Policy yang sudah tidak berlaku tidak boleh tetap digunakan oleh AI hanya karena masih berada di memory, cache, index, knowledge, atau context.

## Non-Negotiable Boundary

Tenant dapat mengatur perilaku bisnisnya dalam ruang yang diperbolehkan platform, tetapi tidak dapat menggunakan tenant policy untuk:

- melewati tenant isolation;
- membuka secret/credential yang tidak berwenang;
- memberikan self-authorization kepada AI;
- melewati mandatory approval;
- mengubah security boundary;
- mengubah authoritative transaction truth;
- menghapus audit/evidence yang wajib dipertahankan;
- memberikan akses lintas tenant;
- mengubah locked architecture tanpa governance yang sesuai.

## Scope Separation

Internal/platform dan tenant menggunakan kerangka konseptual yang serupa, tetapi bukan fakta, policy, data, atau authority yang sama.

```text
PLATFORM / INTERNAL SCOPE
System Policy
Platform Business Policy
Internal Agent/Workflow Rules
Platform Authoritative Data

TENANT SCOPE
Tenant Policy
Tenant Agent/Workflow Rules
Tenant Authoritative Business Data
Tenant Approved Knowledge
```

Cross-scope access harus melalui authority, permission, purpose, scope, security, dan audit yang sesuai.

## Future Design Artifacts

Q27 secara sengaja belum mengunci detail teknis dari:

- Authority Matrix
- Policy Precedence Matrix
- Conflict Resolution Matrix
- Policy schema/database model
- policy evaluation engine implementation
- exact override mechanism
- technical policy storage
- policy versioning implementation
- policy approval UI

Detail tersebut menjadi pekerjaan desain/audit berikutnya dan tidak boleh diasumsikan selesai hanya karena Q27 sudah LOCKED.


---

# Q28 — CONFIGURATION, DEFAULTS & OVERRIDE ARCHITECTURE — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q28 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Configuration dan Policy dibedakan secara konseptual.
2. Configuration menentukan nilai/perilaku dalam ruang yang diizinkan.
3. Configuration tidak boleh melewati mandatory system/security constraints.
4. System Default dibedakan dari Mandatory Constraint.
5. Default dapat diubah hanya jika memang configurable.
6. Tenant hanya dapat mengubah configuration dalam tenant scope yang diizinkan.
7. Configuration tidak otomatis memberikan permission atau authority.
8. Agent configuration tidak dapat memperluas Agent Contract.
9. Workflow configuration tidak dapat menghilangkan safety/risk/approval boundary.
10. Configuration override harus eksplisit dan tervalidasi.
11. Tidak boleh ada implicit override yang menghasilkan privilege escalation.
12. Configuration harus melalui identity/tenant/scope validation.
13. Configuration harus melalui schema/value/policy/permission validation sesuai konteks.
14. Configuration penting memiliki lifecycle/status.
15. Configuration penting memiliki version/history ketika historical state diperlukan.
16. Perubahan configuration penting dapat memerlukan approval berdasarkan risk/authority.
17. Configuration change harus auditable.
18. Running workflow tidak boleh berubah perilakunya secara ambigu akibat perubahan configuration; execution boundary/version harus jelas.
19. Runtime state dan authoritative domain truth tetap dapat membatasi configuration.
20. **Configuration is not an authorization mechanism.**

## Conceptual Configuration Scope

Configuration dapat berada pada beberapa scope, antara lain:

```text
SYSTEM DEFAULT
      ↓
PLATFORM CONFIGURATION
      ↓
TENANT CONFIGURATION
      ↓
WORKFLOW / AGENT CONFIGURATION
      ↓
RUNTIME CONTEXT
```

Urutan tersebut bukan hierarchy override mutlak. Configuration pada scope lebih rendah hanya dapat berlaku apabila scope yang lebih tinggi memang mengizinkannya.

## Default vs Mandatory Constraint

**Default** adalah nilai/perilaku awal yang dapat diganti jika konfigurasi tersebut memang configurable.

**Mandatory Constraint** adalah batas yang tidak dapat dilewati melalui tenant configuration, agent configuration, workflow configuration, atau AI interpretation.

Contoh mandatory constraint dapat mencakup tenant isolation, security boundary, authorization requirement, mandatory approval, dan deterministic transaction truth sesuai keputusan lain yang telah dikunci.

## Configuration Validation

Perubahan configuration penting secara konseptual mengikuti:

```text
INPUT
→ IDENTITY / TENANT CHECK
→ SCOPE CHECK
→ SCHEMA / VALUE VALIDATION
→ POLICY CHECK
→ PERMISSION / AUTHORITY CHECK
→ DEPENDENCY CHECK
→ APPROVAL jika diperlukan
→ SAVE / VERSION
→ ACTIVATE
→ VERIFY
→ AUDIT
```

Tidak semua perubahan harus menggunakan seluruh tahap secara identik; kedalaman kontrol mengikuti konteks dan risk.

## Configuration Lifecycle & Version

Configuration penting dapat memiliki lifecycle/status seperti:

```text
DEFAULT
CUSTOM
INHERITED
OVERRIDDEN
LOCKED
DISABLED
INVALID
PENDING_APPROVAL
```

Daftar status tersebut merupakan model konseptual dan tidak mengunci seluruh implementasi.

Untuk configuration yang memengaruhi historical behavior, sistem harus dapat mengetahui configuration/version yang berlaku ketika kejadian atau workflow terjadi.

## Running Workflow Boundary

Perubahan configuration tidak boleh menyebabkan workflow yang sedang berjalan berubah secara ambigu.

Execution boundary/version harus jelas. Secara default, workflow yang sudah berjalan menggunakan configuration snapshot/version yang telah ditetapkan pada execution boundary, kecuali workflow tersebut secara eksplisit dirancang untuk membaca configuration terbaru.

## Non-Negotiable Boundary

Configuration tidak boleh digunakan untuk:

- memberikan permission baru secara implisit;
- memperluas authority agent;
- melewati Agent Contract;
- melewati tenant isolation;
- melewati mandatory security controls;
- melewati approval requirement;
- mengubah authoritative transaction truth;
- menghapus audit/evidence yang wajib dipertahankan;
- membuka akses lintas tenant;
- mengubah locked architecture secara diam-diam.

## Example

Jika tenant memiliki configuration:

```text
discount_limit = 10%
```

Customer meminta diskon 20%.

AI tidak boleh mengubah configuration menjadi 20% hanya karena customer meminta.

Jika configuration memang perlu diubah, perubahan harus melalui authority, policy, validation, approval jika diperlukan, versioning, activation, verification, dan audit sesuai risk.

## Future Design Artifacts

Q28 belum mengunci detail teknis dari:

- configuration schema;
- inheritance engine;
- database structure;
- exact override syntax;
- configuration UI;
- daftar lengkap setting yang configurable;
- daftar lengkap mandatory settings;
- exact immediate-vs-next-run behavior untuk setiap configuration;
- technical implementation of configuration snapshots/versioning.

Detail tersebut tetap menjadi pekerjaan desain/audit lanjutan.


---

# Q29 — EVENT, STATE & TRIGGER ARCHITECTURE — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q29 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Event, State, Trigger, Condition, dan Action dibedakan secara konseptual.
2. Event merepresentasikan kejadian; State merepresentasikan kondisi; Action merepresentasikan tindakan.
3. Event tidak otomatis menyebabkan Action tanpa trigger/condition yang berlaku.
4. Event resmi harus memiliki source yang dapat divalidasi.
5. Customer claim/conversation tidak otomatis menjadi authoritative event.
6. Event memiliki tenant/platform scope yang jelas.
7. Cross-tenant event processing default-deny.
8. Event source tidak otomatis berarti source memiliki authority untuk semua tindakan.
9. Event processing harus mendukung idempotency untuk side-effect yang relevan.
10. Duplicate event tidak boleh menghasilkan duplicate side effect.
11. Event/state transition harus menghormati dependency dan precondition.
12. Trigger harus dibatasi oleh policy, permission, authority, risk, resource limits, dan tenant scope.
13. AI tidak boleh membuat trigger/action yang melewati system constraints.
14. State resmi hanya dapat berubah melalui authoritative domain mechanism.
15. AI output tidak otomatis menjadi state resmi.
16. Event processing memiliki failure/unknown/retry/human-required handling.
17. Event causality/correlation harus dapat ditelusuri untuk proses penting.
18. Event replay harus aman terhadap duplicate dan side effect.
19. Event/workflow/agent loop harus memiliki batas eksekusi dan loop protection.
20. Human actions/approvals yang menjadi event harus attributable dan auditable.
21. Event payload dan processing harus mempertahankan security, tenant context, dan data boundaries.
22. Event processing penting harus dapat diverifikasi dan diaudit.

## Conceptual Event Flow

```text
EVENT
→ VALIDATE SOURCE
→ VALIDATE SCOPE
→ CHECK DUPLICATE / IDEMPOTENCY
→ CHECK CURRENT STATE
→ MATCH TRIGGER / CONDITION
→ POLICY CHECK
→ AUTHORITY / PERMISSION
→ RISK / APPROVAL
→ START ACTION
→ STATE CHANGE
→ VERIFY
→ EMIT RESULT EVENT
→ AUDIT
```

Tidak setiap event harus menjalankan seluruh tahap secara identik; kontrol mengikuti domain, risk, dan jenis event.

## Event vs Customer Claim

Customer statement seperti:

> "Saya sudah transfer."

tidak otomatis menjadi:

```text
PAYMENT_VERIFIED
```

Ia hanya merupakan customer claim/context sampai authoritative payment process menghasilkan event resmi.

## Platform vs Tenant Event Scope

Platform events dan tenant events dibedakan secara scope.

Contoh platform event:

- platform configuration change
- platform billing event
- platform incident

Contoh tenant event:

- customer message received
- order created
- payment verified
- stock updated

Tenant A event tidak boleh memicu atau memberikan akses ke Tenant B tanpa authority dan scope yang sah.

## State Transition

State resmi tidak boleh berubah hanya karena AI menyatakan kondisi baru.

Contoh:

```text
ORDER
DRAFT
→ PENDING_PAYMENT
→ PAID
→ FULFILLMENT
→ COMPLETED
```

Transition harus mengikuti domain rules, preconditions, authority, dan verification yang berlaku.

## Trigger & Loop Safety

Trigger merupakan aturan yang menentukan apakah event tertentu dapat memulai process/action.

Trigger harus tunduk pada:

- policy;
- permission;
- authority;
- tenant scope;
- risk/approval;
- rate/resource limits;
- idempotency;
- loop protection;
- workflow constraints.

Event → trigger → action → event chain tidak boleh berjalan tanpa batas.

Sistem harus memiliki konsep batas eksekusi, timeout, loop detection, causation tracking, dan safe stop sesuai kebutuhan.

## Event Causality & Correlation

Proses penting harus dapat ditelusuri secara kausal, misalnya:

```text
Customer Payment
→ Gateway Webhook
→ Payment Verified
→ Subscription Activation Workflow
→ Subscription Activated
→ Client Manager Onboarding
```

Konsep correlation/causation diperlukan untuk memungkinkan rekonstruksi proses penting dan audit, tanpa mengunci format teknis tertentu.

## Failure & Replay

Event processing harus mampu menangani kondisi seperti:

```text
SUCCESS
FAILED
RETRYABLE
BLOCKED
UNKNOWN
REQUIRES_HUMAN
```

Replay event historis tidak boleh secara otomatis mengulang side effect berbahaya. Replay harus mempertimbangkan idempotency, current state, authority, policy, dan historical context.

## Human Events

Human approval/rejection/cancellation/intervention yang menghasilkan event harus dapat ditelusuri kepada actor yang berwenang, scope, target, waktu, dan audit linkage yang sesuai.

## Future Design Artifacts

Q29 belum mengunci:

- final event schema;
- exact event taxonomy;
- Event Bus/queue technology;
- queue topology;
- event ordering implementation;
- event retention;
- replay implementation;
- dead-letter architecture;
- exact idempotency mechanism;
- exact loop/execution limits;
- event versioning format.

Detail tersebut tetap menjadi desain/audit lanjutan.


---

# Q30 — TRANSACTION, CONSISTENCY & ATOMICITY ARCHITECTURE — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q30 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Transaction, consistency, atomicity, concurrency, dan recovery dibedakan secara konseptual.
2. Setiap operasi penting memiliki transactional/consistency boundary yang jelas.
3. Operasi yang harus atomic harus diproses secara atomic dalam boundary yang memang dapat dijamin.
4. Sistem tidak boleh menganggap seluruh distributed workflow sebagai satu database transaction.
5. Partial success harus direpresentasikan secara eksplisit.
6. UNKNOWN bukan SUCCESS dan bukan FAILED tanpa verifikasi.
7. Transaction-critical domain menggunakan authoritative current state pada consistency boundary.
8. Stale AI/context data tidak boleh langsung digunakan untuk commit transaksi penting tanpa current validation.
9. Concurrent modification pada data penting harus dideteksi/dikendalikan.
10. Lost update pada data penting tidak boleh terjadi secara diam-diam.
11. Version-aware/concurrency-aware update dapat digunakan untuk mendeteksi konflik.
12. Conflict pada perubahan penting tidak boleh diselesaikan dengan silent overwrite.
13. Business operations dengan side effect yang relevan harus idempotent.
14. External side effect harus dapat direkonsiliasi ketika hasil request UNKNOWN.
15. Rollback database tidak dianggap mampu membatalkan external side effect secara otomatis.
16. Recovery dapat menggunakan retry, reconcile, resume, compensate, stop, atau human intervention sesuai konteks.
17. Business state dipisahkan dari secondary side effects seperti notification jika memang tidak berada dalam transactional boundary yang sama.
18. Financial operations membutuhkan deterministic, exact, idempotent, concurrency-safe, auditable, dan verified processing.
19. Cross-domain consistency harus mempertahankan Source of Truth dan authority masing-masing domain.
20. Sistem tidak boleh melakukan commit penting jika precondition, current state, authority, permission, policy, atau required approval sudah tidak valid.

## Conceptual Transaction Flow

```text
OPERATION
→ DEFINE BOUNDARY
→ READ CURRENT STATE
→ VALIDATE PRECONDITIONS
→ AUTHORITY / POLICY / RISK
→ CONCURRENCY CHECK
→ EXECUTE
→ COMMIT / EXTERNAL EFFECT
→ VERIFY
→ SUCCESS / UNKNOWN / FAIL
→ RECONCILE / RECOVER jika diperlukan
→ AUDIT / REPORT
```

Kedalaman dan bentuk flow dapat berbeda sesuai domain dan risk.

## Atomicity Boundary

Operasi yang memang harus diperlakukan sebagai satu kesatuan harus memiliki atomicity boundary yang dapat dijamin.

Namun distributed workflow yang melibatkan external provider, queue, event bus, atau service lain tidak boleh secara otomatis dianggap sebagai satu database transaction.

Jika sebuah proses hanya berhasil sebagian, state partial success harus direpresentasikan secara eksplisit dan ditangani melalui recovery/reconciliation yang sesuai.

## Current State & Stale Context

AI dapat menggunakan context, memory, cache, atau retrieved data untuk reasoning. Namun data tersebut tidak otomatis menjadi current authoritative transaction state.

Pada consistency boundary transaksi penting:

```text
AI / CONTEXT
→ CURRENT AUTHORITATIVE STATE
→ FINAL VALIDATION
→ COMMIT
```

Perubahan yang terjadi setelah AI melakukan reasoning tetapi sebelum commit harus dapat dideteksi dan ditangani.

## Concurrency & Conflict

Untuk data penting, concurrent update harus dikendalikan sehingga tidak menghasilkan silent lost update atau state corruption.

Jika versi/current state telah berubah:

```text
CONFLICT
→ DO NOT SILENTLY OVERWRITE
→ REFRESH / RE-EVALUATE
→ RESOLVE / RETRY / ESCALATE
```

Mekanisme teknis dapat berbeda menurut domain dan belum dikunci oleh Q30.

## External Side Effects & UNKNOWN

Jika external operation timeout atau hasilnya tidak dapat dipastikan:

```text
REQUEST
→ UNKNOWN
```

Sistem tidak boleh langsung menganggap FAILED lalu membuat operation kedua.

Sistem harus melakukan reconciliation/verifikasi terhadap external system sebelum melakukan side effect yang berpotensi duplicate.

## Rollback vs Compensation

Database rollback hanya membatalkan perubahan yang berada dalam transactional boundary tersebut.

Jika external side effect sudah terjadi, recovery dapat memerlukan:

- reconciliation;
- compensation;
- resume;
- controlled retry;
- stop;
- human intervention.

Tidak boleh mengasumsikan rollback internal otomatis mengembalikan external effect.

## Business State vs Secondary Side Effect

Business state dan secondary side effect seperti notification dapat memiliki transactional boundary berbeda.

Contoh:

```text
PAYMENT = PAID
NOTIFICATION = FAILED
```

Tidak otomatis berarti payment harus dibatalkan.

Notification dapat diproses ulang secara terpisah sesuai policy/workflow.

## Financial Integrity

Operasi finansial seperti payment, refund, invoice, subscription, dan usage billing harus menjaga deterministic processing, exact monetary representation, idempotency, concurrency safety, auditability, dan verification sesuai domain.

## Future Design Artifacts

Q30 belum mengunci:

- PostgreSQL isolation level;
- optimistic vs pessimistic locking secara universal;
- distributed transaction technology;
- Saga implementation;
- Outbox pattern;
- exact retry strategy;
- exact conflict resolution algorithm;
- exact transaction boundary setiap domain;
- database locking implementation;
- technical reconciliation architecture.

Detail tersebut tetap menjadi desain/audit lanjutan.


---

# Q31 — INTEGRATION & EXTERNAL SYSTEM TRUST ARCHITECTURE — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q31 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Semua external integrations melewati Universal Integration Foundation/adapter boundary.
2. Business logic tidak boleh bergantung langsung pada provider-specific implementation.
3. External input tidak otomatis dipercaya sebagai instruction, authorization, atau internal truth.
4. External input harus divalidasi authenticity/integrity sesuai kemampuan provider.
5. External input harus melalui deterministic tenant mapping.
6. Ambiguous tenant mapping → stop/reject/escalate, tidak boleh ditebak.
7. External provider hanya authoritative untuk fakta/domain yang memang menjadi tanggung jawab provider.
8. External provider state tidak otomatis menguasai seluruh internal AI BOS state.
9. Conflict external state vs internal authoritative state tidak boleh diselesaikan diam-diam.
10. External credentials harus tenant-scoped, integration-scoped, permission-controlled, dan lifecycle-aware.
11. Agent tidak mendapatkan direct unrestricted external API access.
12. External action harus melewati typed capability/tool dan applicable authority/permission/policy/risk controls.
13. Provider capability tidak otomatis menjadi Agent capability.
14. Webhook harus memiliki authenticity/integrity, tenant mapping, object/state validation, dan idempotency controls sesuai konteks.
15. External timeout/uncertain result harus dapat direpresentasikan sebagai UNKNOWN dan direkonsiliasi sebelum duplicate side effect.
16. Retry external operations harus bounded dan risk-aware.
17. External side effects penting harus dapat diverifikasi dan diaudit.
18. Integration connection memiliki lifecycle dan tidak dianggap ACTIVE hanya karena credential tersimpan.
19. External imported data tidak otomatis menjadi official business data sebelum validation/lifecycle controls terpenuhi.
20. Integration failure tidak otomatis berarti business transaction failure jika domain state sebenarnya sudah berhasil.
21. Integration architecture harus reusable dan provider-independent melalui adapter boundary.

## External System Trust Boundary

External systems merupakan pihak di luar control boundary AI BOS.

Secara konseptual:

```text
EXTERNAL SYSTEM
      ↓
AUTHENTICITY / INTEGRITY
      ↓
TENANT MAPPING
      ↓
SCHEMA / DOMAIN VALIDATION
      ↓
IDEMPOTENCY
      ↓
INTEGRATION ADAPTER
      ↓
UNIVERSAL CORE
      ↓
AUTHORITATIVE STATE / EVENT
      ↓
VERIFY
      ↓
AUDIT
```

Tidak semua external input menjadi official data atau instruction hanya karena berhasil masuk melalui integration.

## External Provider Authority

Provider dapat menjadi authoritative source untuk fakta yang memang berada dalam domain tanggung jawab provider.

Contoh:

- payment provider dapat memberikan evidence/status payment;
- calendar provider dapat memberikan state event kalender;
- messaging provider dapat memberikan delivery status.

Namun provider tidak otomatis memiliki authority untuk mengubah seluruh internal AI BOS state.

Internal domain tetap menentukan bagaimana external evidence diterima, dipetakan, divalidasi, dan diterapkan.

## Tenant Mapping

External event/request harus dapat dipetakan secara deterministic ke tenant dan internal object yang benar.

Jika mapping:

- tidak ditemukan;
- ambigu;
- tidak konsisten;
- tidak sesuai registered integration;

maka sistem tidak boleh menebak. Operasi harus ditolak, dihentikan, direkonsiliasi, atau dieskalasikan sesuai konteks.

## Webhook & External Input

Webhook/API response/imported data harus diperlakukan sebagai external data sampai kontrol validasi yang sesuai terpenuhi.

Konsep validasi dapat meliputi:

```text
AUTHENTICITY
→ INTEGRITY
→ EXPECTED SOURCE
→ TENANT MAPPING
→ OBJECT MAPPING
→ SCHEMA
→ DOMAIN STATE
→ IDEMPOTENCY
```

Kontrol aktual bergantung pada provider dan integration.

## External Credentials

Credential harus tetap berada dalam boundary credential management:

```text
TENANT
→ INTEGRATION
→ CREDENTIAL
→ CONTROLLED CAPABILITY
→ EXTERNAL PROVIDER
```

Agent tidak mendapatkan raw credential hanya karena membutuhkan kemampuan tertentu.

## Outbound Integration

Tindakan outbound mengikuti:

```text
AGENT / WORKFLOW
→ TYPED TOOL / CAPABILITY
→ PERMISSION
→ AUTHORITY
→ POLICY
→ RISK / APPROVAL
→ ADAPTER
→ EXTERNAL PROVIDER
→ VERIFY
→ RESULT
→ AUDIT
```

Integration tidak boleh menjadi jalan bypass terhadap Agent Contract, permission, authority, tenant isolation, policy, risk, atau approval.

## External State Conflict

Jika external provider menyatakan satu state sementara internal state menunjukkan kondisi berbeda:

```text
EXTERNAL STATE
vs
INTERNAL STATE
→ CONFLICT
→ RECONCILE / RESOLVE
```

Tidak boleh silent overwrite atau silent assumption.

## UNKNOWN & Reconciliation

External request yang timeout atau hasilnya tidak dapat dipastikan harus dapat menjadi:

```text
UNKNOWN
```

Sebelum side effect kedua dilakukan, sistem harus melakukan verification/reconciliation bila relevan.

Database rollback internal tidak dianggap otomatis membatalkan external side effect.

## Integration Lifecycle

Integration connection dapat menggunakan lifecycle konseptual:

```text
NOT_CONNECTED
→ CONNECTING
→ CONNECTED
→ VERIFYING
→ ACTIVE
```

Failure/disruption dapat direpresentasikan sebagai:

```text
FAILED
DISCONNECTED
EXPIRED
SUSPENDED
```

Exact state taxonomy dan implementation belum dikunci.

## Provider Independence

Universal Core tidak boleh dibangun dengan business logic yang melekat pada satu provider.

Contoh konseptual:

```text
PaymentProvider
├── Provider A Adapter
├── Provider B Adapter
└── Provider C Adapter
```

Pergantian provider tidak seharusnya memerlukan perubahan besar pada core business logic.

## Future Design Artifacts

Q31 belum mengunci:

- provider-specific protocol;
- exact webhook signature algorithm;
- exact OAuth implementation;
- credential vault technology;
- retry/backoff values;
- circuit breaker implementation;
- provider SLA;
- queue architecture;
- final adapter interface/schema;
- reconciliation engine implementation;
- permanent provider list for MVP.

Provider-specific production claims harus diverifikasi terhadap dokumentasi provider yang berlaku pada saat implementasi.

---

# Q33 — MULTI-TENANT SCALABILITY, CONCURRENCY & WORKLOAD ISOLATION — LOCKED

**Status:** LOCKED  
**Stage:** Stage 1 — Core Architecture & Governance  
**Decision:** Q33 LOCKED  
**Date:** 2026-09-14

## Locked Principles

1. Universal Core adalah logical/shared architecture, bukan satu physical process/server.
2. Satu Universal Core harus dapat melayani banyak tenant melalui concurrent execution.
3. Tenant tidak mendapatkan copy/codebase Universal Core terpisah sebagai requirement normal.
4. Tenant data, context, state, memory, knowledge, workflow, task, integration, credential, analytics, billing, dan authorization tetap tenant-scoped.
5. Jumlah registered tenant tidak menentukan jumlah worker/process secara langsung.
6. Execution capacity harus mengikuti workload aktual.
7. Independent workloads dapat diproses secara concurrent sesuai capacity dan controls.
8. Dependent operations harus mempertahankan ordering/synchronization yang diperlukan.
9. Conversation/customer state harus persistent/shared secara tepat dan tidak bergantung pada worker tertentu.
10. Worker affinity, jika digunakan, bukan security boundary.
11. Horizontal scaling harus dimungkinkan tanpa mengubah Universal Core/business logic.
12. Queue/scheduling dapat digunakan untuk menyerap burst workload.
13. Queue tidak boleh unlimited tanpa resource/safety boundary.
14. Tenant-aware rate limiting, quota, concurrency, dan fairness harus mencegah noisy neighbor.
15. Satu tenant tidak boleh menghabiskan resource platform sehingga tenant lain kehilangan operasi normal tanpa controlled policy.
16. Resource priority dapat digunakan untuk scheduling tetapi tidak boleh bypass security, tenant isolation, authority, permission, policy, atau approval.
17. AI Gateway harus dapat melayani concurrent AI requests tanpa menjadi logical single-request bottleneck.
18. AI usage/cost control tetap tenant-aware.
19. Database/storage access harus tenant-aware dan concurrency-safe.
20. Cache tidak boleh menjadi pengganti authoritative transaction truth.
21. Resource overload harus menghasilkan controlled degradation, queue, throttle, defer, block, atau scaling sesuai konteks, bukan uncontrolled failure.
22. Subsystem yang mengalami degradation tidak otomatis boleh menjatuhkan seluruh platform atau tenant lain.
23. Tenant dengan workload sangat besar dapat memperoleh bounded/dedicated capacity pada future tier tanpa memerlukan rewrite Universal Core.
24. Architecture harus mampu berkembang dari skala kecil menuju 100, 1.000, 10.000+ tenant melalui peningkatan execution capacity dan infrastructure tanpa mengubah prinsip Universal Core/multi-tenant.

## Universal Core vs Execution Capacity

Universal Core adalah logical reusable architecture. Penambahan workload tidak mengharuskan pembuatan Universal Core baru untuk setiap tenant.

```text
UNIVERSAL CORE
       │
       ├── Worker / Execution Instance A
       ├── Worker / Execution Instance B
       └── Worker / Execution Instance C
```

## Tenant Context Isolation

Setiap workload mempertahankan tenant/customer/conversation context yang relevan. Context tidak boleh bercampur hanya karena request diproses oleh worker atau instance yang sama.

## Concurrent vs Dependent Work

Independent workloads dapat diproses concurrent. Dependent operations harus mempertahankan ordering/synchronization yang diperlukan.

## Worker Model

```text
WORKER COUNT
≠ CUSTOMER COUNT
≠ REGISTERED TENANT COUNT
≠ CONCURRENT WORKLOAD
```

Worker adalah execution capacity, bukan identitas customer.

## Queue & Burst Handling

```text
INCOMING
→ TENANT / IDENTITY RESOLUTION
→ RATE / QUOTA / FAIRNESS
→ QUEUE / SCHEDULER
→ CONCURRENCY CONTROL
→ WORKER
→ UNIVERSAL CORE
→ RESULT
```

Queue harus memiliki batas dan failure handling.

## Noisy Neighbor Protection

Jika satu tenant mengalami workload berlebihan, platform dapat melakukan throttle/isolation/queue/limit terhadap tenant tersebut agar tenant lain tetap beroperasi dalam kapasitas wajar.

## AI Gateway Scalability

AIGateway tetap menjadi logical centralized AI access layer, tetapi execution tidak boleh bergantung pada satu physical single-request bottleneck.

## Stateful Conversation Handling

Conversation state penting harus berada pada persistent/shared state yang sesuai sehingga request berikutnya tidak bergantung pada worker tertentu. Worker affinity bukan security boundary.

## Graceful Degradation

Overload/degradation dapat ditangani dengan queue, throttle, defer, block, scale, fallback, atau escalation sesuai konteks. Degradation satu subsystem tidak otomatis mengubah authoritative business truth atau mematikan seluruh platform.

## Scale Model

```text
10 TENANTS
→ basic execution capacity

100 TENANTS
→ stronger concurrency/resource controls

1,000 TENANTS
→ horizontal execution + queue/scheduling + tenant fairness

10,000+ TENANTS
→ advanced capacity management / partitioning / dedicated capacity as needed
```

Angka tersebut adalah contoh skala konseptual, bukan capacity guarantee.

## Important Distinction

```text
REGISTERED TENANTS
≠ ACTIVE CONVERSATIONS
≠ CONCURRENT REQUESTS
≠ WORKER COUNT
```

Execution capacity harus dirancang berdasarkan workload, latency target, resource consumption, external provider constraints, dan safe operating limits.

## Future Design Artifacts

Q33 belum mengunci Kubernetes, Docker, Redis, Kafka, RabbitMQ, Celery, exact worker/queue architecture, database sharding, read replicas, autoscaling algorithm, exact concurrency/fairness/tenant capacity, dedicated infrastructure rules, cloud provider, atau load balancer technology.

Pemilihan teknologi dilakukan setelah workload dan capacity requirements tervalidasi dan tidak boleh mengubah prinsip Universal Core/multi-tenant.
