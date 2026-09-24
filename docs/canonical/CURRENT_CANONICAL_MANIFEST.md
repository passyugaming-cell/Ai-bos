# AI BOS — CURRENT CANONICAL MANIFEST
Version: 1.1
Status: CURRENT — DOCUMENT CONTROL
Purpose: Single navigation and precedence point for implementation preparation.

## 1. Authority order

1. Q1–Q51 Locked Decisions — parent decision baseline.
2. Current Master Canonical Blueprint.
3. Current locked decision/closure contracts in `docs/decisions/`.
4. This manifest plus the Canonical Status Reconciliation Overlay for document-status conflicts.
5. Current readiness/audit documents.
6. Historical documents — traceability only.

No lower-level document silently overrides a higher-level document.

## 2. Current canonical documents

### Canonical
- `docs/canonical/AI_BOS_MASTER_CANONICAL_BLUEPRINT_v1.1_CURRENT.md`
- `docs/canonical/AI_BOS_MASTER_GAP_FREE_BUILD_CONTRACT_v1.2_FINAL_CANONICAL.md`
- `docs/canonical/CURRENT_CANONICAL_MANIFEST.md`
- `docs/canonical/CANONICAL_STATUS_RECONCILIATION_OVERLAY_v1.0.md`

### Locked decisions / closures
- `docs/decisions/AI_BOS_OWNER_DECISION_REGISTRY_v1.1_DCOMM02_LOCKED.md`
- `docs/decisions/AI_BOS_OWNER_PROXY_DECISION_CLOSURE_v1.0.md`
- `docs/decisions/AI_BOS_D-COMM-02_CAMPAIGN_COMMUNICATION_CONTRACT_v1.1_LOCKED.md`
- `docs/decisions/AI_BOS_D-DOC-01_READINESS_DOCUMENT_STATUS_RECONCILIATION_v1.0_LOCKED.md`
- `docs/decisions/AI_BOS_GAP-001_FINAL_PRO_TARGET_SCOPE_CONTRACT_v1.0_LOCKED.md`
- `docs/decisions/AI_BOS_GAP-005_BILLING_PAYMENT_CONTRACT_v1.0.md`
- `docs/decisions/AI_BOS_MASTER_CONTROLLED_CLOSURE_PACK_v1.0.md`

### Governance
- `docs/governance/AI_BOS_MASTER_AUDIT_KNOWLEDGE_BASE_CURRENT.md`

### Readiness / audit
- `docs/readiness/AI_BOS_FULL_PREBUILD_AUDIT_IMPLEMENTATION_GAP_MAP_v1.0.md`
- `docs/readiness/AI_BOS_5F_CHECKPOINT_01.md`
- `docs/readiness/CURRENT_BUILD_READINESS.md`

### Execution
- `docs/execution/JULES_PREBUILD_SPEC_REVIEW_GATE.md`
- `docs/execution/JULES_IMPLEMENTATION_WORK_PLAN.md`
- `docs/execution/DOCUMENT_SYNC_APPLY_PLAN.md`

## 3. Historical / superseded

The following are retained for traceability and are NOT current implementation authority:
- `docs/historical/AI_BOS_MASTER_BUILD_READINESS_TODO_v1.0_HISTORICAL.md`
- `docs/historical/AI_BOS_MASTER_LOCK_AND_SESSION_HANDOFF_v1.0_HISTORICAL.md`

Historical OPEN/PENDING labels must not be treated as current status when a later controlled decision/closure artifact supersedes them.

## 4. Non-negotiable status rules

- LOCKED ≠ IMPLEMENTED.
- DESIGN READY ≠ PRODUCTION READY.
- Documentation ≠ implementation evidence.
- PASS requires actual evidence.
- UNKNOWN remains UNKNOWN until verified.
- Conflicts must be surfaced, not silently reconciled.
- Q1–Q51 must not be silently changed.
- Provider/legal facts remain external verification inputs where not yet verified.

## 5. Current implementation position

The repository was audited as a pre-build documentation repository. Application implementation was not established by the audit. Testing/security/E2E/restore evidence is therefore still pending.

Jules must begin with the Pre-Build Specification Review Gate, not feature coding.
