# AI BOS — TEST SUITE 04 — TENANT STAFF / OPERATOR

# AI BOS — FULL TEST SPECIFICATION

## Test status convention
- NOT EXECUTED = test specification exists but no running system/repository evidence yet.
- PASS = executed and evidence recorded.
- FAIL = executed and actual behavior violates expected behavior.
- BLOCKED = execution cannot proceed because required implementation/dependency is missing.
- UNKNOWN = evidence is insufficient.
- N/A = formally out of scope with evidence.

## Source discipline
This test suite is derived from the AI BOS canonical blueprint candidate, Master Build-Ready Blueprint, Master Audit Knowledge Base, locked decision/handoff material, and the completed E2E system map.
It does not invent implementation facts. Where the blueprint intentionally leaves a value configurable/open, the test checks that the system treats it as configurable rather than pretending a fixed value is canonical.

## Universal expected controls
Every applicable test must consider:
1. identity
2. authentication
3. tenant resolution
4. authorization
5. permission
6. entitlement
7. policy
8. authority
9. risk
10. source of truth
11. state transition
12. side effect
13. idempotency
14. audit
15. observability
16. failure/recovery
17. tenant isolation
18. AI boundary
19. human escalation
20. evidence


## Perspective
**Actor/System under test:** Tenant Staff / Operator

## Execution rule
This is a test specification, not a claim that the current repository passes. Every case begins as `NOT EXECUTED` until actual implementation evidence is available.

## Test Cases

### STA-AUTH
**Scenario:** Staff authentication

**Expected result:** Own Account required; role membership is explicit.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-SCOPE
**Scenario:** Staff accesses assigned tenant

**Expected result:** No cross-tenant access.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-CUSTOMER
**Scenario:** View customer

**Expected result:** Only permitted customer fields are visible.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-CONV
**Scenario:** Handle conversation

**Expected result:** Conversation state and assignment rules are respected.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-HANDOFF
**Scenario:** Accept AI handoff

**Expected result:** Handoff state changes correctly; AI does not conflict with human handling.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-RESUME
**Scenario:** Resolve and resume AI

**Expected result:** Resume requires permitted state transition and refreshed context/authorization.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-PROD
**Scenario:** Answer product/price/stock question

**Expected result:** Authoritative data is used; stale/AI-inferred values are not presented as fact.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-ORDER
**Scenario:** View/update permitted order

**Expected result:** State transition guards and permissions apply.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-REFUND
**Scenario:** Attempt refund without authority

**Expected result:** Denied or routed for required approval.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-KNOW
**Scenario:** Edit knowledge without approval

**Expected result:** Draft/review/approval lifecycle is enforced.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-WORK
**Scenario:** Run workflow

**Expected result:** Execution requires granted capability and does not inherit admin authority.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-AUDIT
**Scenario:** View audit data

**Expected result:** Only permitted audit scope; secrets/private chain-of-thought excluded.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-INVITE
**Scenario:** Invite/change user access without permission

**Expected result:** Denied.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`


### STA-CROSS
**Scenario:** Access another tenant by manipulating identifiers

**Expected result:** Denied server-side; client-supplied tenant identifiers are not authorization truth.

**Required checks:** identity, tenant scope, permission, entitlement, authority, policy, state, source of truth, side effect, idempotency, audit, observability, failure/recovery, and isolation where applicable.

**Evidence required:** test input, actual result, logs/audit/correlation reference, state before/after, and PASS/FAIL reason.

**Status:** `NOT EXECUTED`



## Completion condition
All applicable cases must be executed. A suite is not PASS merely because the happy path works; negative, boundary, concurrency, failure, recovery, isolation and abuse cases must also be evidenced.
