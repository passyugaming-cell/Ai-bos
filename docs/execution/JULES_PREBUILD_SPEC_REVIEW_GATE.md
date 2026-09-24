# AI BOS — JULES PRE-BUILD SPECIFICATION REVIEW GATE
Version: 1.1
Status: CURRENT

## Inputs

Use `docs/canonical/CURRENT_CANONICAL_MANIFEST.md` first.
Then review the current canonical blueprint, locked decision contracts, current readiness, gap map, 5F checkpoint, and test specifications.

## Required checks

1. Document control: no conflicting CURRENT instructions.
2. Q1–Q51 preservation.
3. Universal Core / Owner AI / Tenant AI boundaries.
4. Deterministic source-of-truth boundaries.
5. Tenant scope through API/event/workflow/task/tool/provider/audit paths.
6. Typed tool authorization and fail-closed security.
7. Transaction boundary: authoritative state → final validation → commit.
8. UNKNOWN external results reconciled before duplicate side effects.
9. Every implementation slice has requirements, affected modules, migrations, permissions, tenant/state/event impact, tests, rollback/recovery, observability and acceptance criteria.

## STOP conditions

Stop before coding for P0/P1 blockers, unresolved canonical contradiction, unclear source of truth, unclear authority/permission, tenant-isolation ambiguity, payment/identity ambiguity, unsafe secrets/tools, or missing critical failure/recovery paths.

## Required output

Produce specification review result, contradiction list, implementation gap list, implementation sequence, affected modules, migration plan, test plan, rollback/recovery plan, acceptance criteria, and explicit assumptions/unknowns.
