# AI BOS — OWNER DECISION REGISTRY
## v1.1 — D-COMM-02 Closure

**Status:** CONTROLLED REGISTRY  
**Canonical Parent:** Q1–Q51 Locked Decisions

---

# D-COMM-02 — CAMPAIGN / BROADCAST / FOLLOW-UP LIMITS

**Status:** LOCKED — OWNER DECISION COMPLETED

## Locked commercial/safety values

| Decision | Locked value |
|---|---:|
| Starter marketing campaigns | Disabled |
| Starter marketing broadcasts | Disabled |
| Starter marketing automated marketing follow-up | Disabled |
| Pro monthly marketing deliveries | 1,000 / rolling 30 days / Tenant |
| Pro unique marketing recipients | 250 / rolling 24 hours / Tenant |
| Broadcast recipients | 250 / execution |
| Broadcast executions | 2 / rolling 7 days / Tenant |
| Active marketing campaigns | 2 / Tenant |
| Campaign executions | 1 / campaign / rolling 24 hours |
| Campaign recipients | 250 / execution |
| Marketing messages / recipient | 3 / rolling 30 days |
| Marketing cooldown / recipient | 72 hours |
| Consecutive unengaged marketing sends | 2 |
| Unengaged suppression | 30 days |
| Marketing follow-ups | 2 / recipient / rolling 30 days |
| Abandoned-cart follow-ups | 2 / sequence |
| Marketing quiet hours | 21:00–08:00 recipient-local |
| Marketing opt-in | Explicit + category-specific |
| Opt-out | Immediate suppression |
| Re-subscription | New explicit opt-in |
| Cap enforcement | BLOCK/SUPPRESS |

## Locked policy rules

1. All marketing features share one tenant-wide marketing counter.
2. Feature switching cannot bypass the recipient counter.
3. Marketing intent cannot be hidden by reclassifying content as utility/service.
4. Scheduled execution must re-check current state at execution time.
5. Human takeover suppresses conflicting automation.
6. UNKNOWN delivery requires reconciliation before duplicate retry.
7. AI cannot self-authorize marketing, bypass consent, reset counters or bypass entitlement.
8. Provider/law limits override AI BOS limits.
9. Effective limit is the minimum applicable limit.
10. No automatic paid overage or financial obligation is created.
11. Starter does not expose generic marketing campaign/broadcast/marketing-follow-up capability.
12. Pro exposes bounded marketing automation only inside the locked controls.

## Decision basis

The closure is based on:

- current WhatsApp Business policy requiring opt-in and honoring opt-out;
- current Meta guidance emphasizing message quality, frequency management and user control;
- current Indonesia WhatsApp pricing evidence used as an economic safety benchmark;
- explicit project requirements for bounded automation, tenant isolation, consent, frequency limits, stop conditions and human-handoff suppression;
- a conservative launch-control calculation rather than treating provider maximum capacity as product entitlement.

## Important distinction

These values are **AI BOS internal safety/commercial ceilings**.

They are not claims that Meta's adaptive or provider-specific limits equal these numbers.

If an external provider imposes a lower limit, the lower limit applies.

If a provider changes policy, AI BOS must adapt through the provider boundary and must not bypass the new restriction.

## Traceability

`D-COMM-02 → Communication Contract v1.1 → Campaign/Broadcast/Follow-up Requirements → Implementation Modules → Tests → Evidence`

Implementation evidence is still required.

---

# REGISTRY UPDATE

D-COMM-02 is removed from:

`OWNER DECISION REQUIRED / PENDING`

and moves to:

`LOCKED — OWNER DECISION COMPLETED`

No other previously open decision is silently closed by this update.

**Next controlled decision: D-DOC-01.**
