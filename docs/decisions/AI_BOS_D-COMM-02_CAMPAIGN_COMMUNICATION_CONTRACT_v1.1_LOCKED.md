# AI BOS — D-COMM-02 CONTROLLED COMMUNICATION LIMITS CONTRACT
## Campaign / Broadcast / Follow-up — LOCKED v1.1

**Document ID:** AI_BOS_D-COMM-02_CAMPAIGN_COMMUNICATION_CONTRACT_v1.1  
**Status:** LOCKED — OWNER DECISION COMPLETED  
**Decision:** D-COMM-02 CLOSED FOR CURRENT MVP/PRO TARGET  
**Canonical Parent:** Q1–Q51 Locked Decisions  
**Scope:** Campaign, broadcast, follow-up and customer-facing outbound communication controls.  
**Commercial Scope:** Starter + Pro only.  
**Implementation Status:** Design decision only; implementation evidence is still required.

---

# 0. CLOSURE

D-COMM-02 was previously `PENDING`. The Human Owner has now explicitly requested that the remaining open fields be filled and locked using evidence, calculation and risk analysis rather than arbitrary guesses.

This document therefore locks the **AI BOS internal communication safety/commercial defaults**.

These values are not claims about Meta's hidden or adaptive limits. If WhatsApp/Meta/provider limits are stricter, the stricter limit wins automatically. If a provider changes its policy, the platform must fail closed or reduce sending rather than exceed the provider boundary.

Changes to the locked values require explicit change control.

---

# 1. EVIDENCE BASIS

## 1.1 WhatsApp policy

The current WhatsApp Business Messaging Policy states that businesses may contact people only when the business has the person's phone number and has obtained opt-in permission for further WhatsApp messages. It also requires businesses to honor requests to stop/block communications. WhatsApp may limit or remove access for policy violations or unauthorized bulk messaging. citeturn0search0

For WhatsApp Business Platform, business-initiated conversations require approved message templates. Within the 24-hour customer-service window, businesses can respond without templates; automation is allowed but a clear human escalation path is required. citeturn0search0

Meta also states that users can control business chats, and that WhatsApp limits the number of marketing messages a user can receive to reduce overload. Meta recommends monitoring frequency and engagement. citeturn3search0

## 1.2 Current pricing evidence used for economic safety

Current September 2026 third-party reproductions of Meta's published Indonesia rate card report approximately:

- Marketing: Rp586.33 per delivered message.
- Utility: Rp356.65 per delivered message.
- Authentication: Rp356.65 per delivered message.

The cited rate card is effective July 1, 2026; rates can change and must be re-verified before production commercial configuration. citeturn2search0turn2search1

This contract therefore does not assume unlimited marketing volume is economically safe.

## 1.3 Frequency-cap evidence

Meta's public materials establish that marketing-message frequency can be limited and that the limit is adaptive; third-party documentation consistently warns that a fixed universal per-user number should not be treated as canonical. Therefore AI BOS does **not** hard-code a claimed Meta per-user threshold.

Instead, AI BOS applies its own conservative recipient-level ceiling below the unknown provider ceiling.

---

# 2. DESIGN OBJECTIVE

The D-COMM-02 numbers are designed around four constraints:

1. Protect recipients from message fatigue.
2. Prevent tenant automation from accidentally generating a large paid-message bill.
3. Keep the first commercial implementation simple enough to audit.
4. Leave room for future evidence-based expansion without making today's MVP unsafe.

The values are therefore intentionally conservative launch defaults, not maximum provider capacity.

---

# 3. LOCKED PLAN BOUNDARY

## Starter

### Marketing campaigns
**NOT AVAILABLE**

### Marketing broadcasts
**NOT AVAILABLE**

### Marketing automated follow-up
**NOT AVAILABLE**

### Allowed communication

Starter may perform customer-service/transactional communication required by activated deterministic flows and customer-initiated conversations, subject to provider policy, tenant policy, opt-out and entitlement.

Starter must not expose a generic marketing broadcast/campaign engine.

---

## Pro

Pro may expose:

- bounded marketing campaigns;
- bounded broadcasts;
- bounded marketing follow-up;
- segmentation;
- scheduled automation;

subject to all controls in this document.

---

# 4. LOCKED NUMERIC LIMITS — PRO

## 4.1 Tenant monthly marketing delivery cap

**LOCKED: 1,000 delivered marketing messages per Tenant per rolling 30 days.**

This is the primary marketing budget guard.

The counter applies across:

- campaign;
- broadcast;
- marketing follow-up;
- re-engagement marketing.

It is **not** separate per feature.

### Economic calculation

Using the September 2026 Indonesia benchmark of Rp586.33 per delivered marketing message:

`1,000 × Rp586.33 = Rp586,330`

With an illustrative 11% tax scenario:

`Rp586,330 × 1.11 ≈ Rp650,826`

The subscription price is not treated as a guarantee that Meta/provider charges are included. The cap is primarily a safety ceiling against uncontrolled usage.

---

## 4.2 Maximum unique marketing recipients per rolling 24 hours

**LOCKED: 250 unique recipients per Tenant per rolling 24 hours.**

This is an AI BOS safety limit, not a statement of Meta's current platform limit.

The platform/provider may impose a lower effective limit. If so, the lower limit wins.

---

## 4.3 Maximum recipients per broadcast execution

**LOCKED: 250 unique recipients per broadcast execution.**

A broadcast cannot exceed this size.

A larger audience must be segmented and processed as separate governed executions, while still remaining subject to the same tenant-wide monthly and recipient-level caps.

Splitting an audience does **not** reset the recipient's frequency counter.

---

## 4.4 Broadcast frequency

**LOCKED: maximum 2 broadcast executions per Tenant per rolling 7 days.**

A broadcast execution that results in zero eligible recipients still counts as an execution attempt for anti-loop governance.

---

## 4.5 Active campaigns

**LOCKED: maximum 2 active marketing campaigns per Tenant.**

Draft/paused/completed campaigns do not consume the active-campaign count.

A campaign cannot create another campaign automatically unless that capability is explicitly added later through change control.

---

## 4.6 Campaign execution

**LOCKED: maximum 1 marketing execution per campaign per rolling 24 hours.**

Maximum eligible recipients per execution:

**250 unique recipients.**

Campaign execution remains subject to:

- monthly tenant cap;
- rolling 24-hour tenant cap;
- recipient-level frequency cap;
- consent;
- quiet hours;
- stop conditions;
- entitlement;
- provider constraints.

---

# 5. LOCKED RECIPIENT-LEVEL MARKETING FREQUENCY

## 5.1 Unified marketing counter

All AI BOS marketing messages to the same recipient count against one shared recipient-level marketing counter.

This includes:

- broadcast;
- campaign;
- marketing follow-up;
- re-engagement.

A tenant cannot bypass the limit by using another workflow or another marketing feature.

---

## 5.2 Marketing frequency ceiling

**LOCKED: maximum 3 delivered marketing messages to the same recipient in any rolling 30-day period.**

This is an AI BOS safety limit.

It is intentionally independent of Meta's adaptive limit.

---

## 5.3 Minimum marketing cooldown

**LOCKED: minimum 72 hours between delivered marketing messages to the same recipient.**

This applies across campaign, broadcast and marketing follow-up.

---

## 5.4 Engagement suppression

**LOCKED: after 2 consecutive marketing messages with no qualifying engagement, suppress further marketing messages to that recipient for 30 days.**

Qualifying engagement may include an explicit reply or an approved interaction signal.

A delivery receipt alone is not engagement.

Transactional/service communication does not count as marketing engagement.

---

# 6. FOLLOW-UP LIMITS

## 6.1 Marketing follow-up

**LOCKED: maximum 2 marketing follow-up messages per recipient per rolling 30 days.**

These follow-ups still count toward the global 3-marketing-messages-per-30-days recipient ceiling.

Therefore:

```text
Broadcast + Follow-up + Campaign
        ↓
ONE shared recipient marketing counter
```

---

## 6.2 Follow-up cooldown

**LOCKED: minimum 72 hours between marketing follow-ups to the same recipient.**

A follow-up cannot be sent simply because a timer expired.

Execution-time eligibility must be re-evaluated.

---

## 6.3 Abandoned-cart follow-up

For the current MVP/Pro target:

**LOCKED: maximum 2 automated abandoned-cart follow-ups per cart/customer sequence.**

They must stop when:

- order is created/confirmed;
- cart is no longer eligible;
- customer opts out;
- human takes over;
- customer responds in a way that requires human/customer-service handling;
- frequency/cap is reached;
- campaign/workflow expires;
- entitlement is lost.

If the messages are marketing-category messages, the global marketing counter applies.

---

# 7. QUIET HOURS

## 7.1 Default quiet hours

**LOCKED: 21:00–08:00 recipient-local time.**

Marketing messages must not be sent during this window.

---

## 7.2 Timezone resolution

Use:

1. verified recipient timezone, if available;
2. otherwise tenant configured timezone.

If neither is reliably available:

**Do not send marketing automatically.**

This prevents a timezone assumption from becoming an unwanted late-night message.

---

## 7.3 Transactional/service exception

Critical transactional/service communication may follow its own approved operational policy.

This exception must not be used to disguise marketing content as utility/service content.

---

# 8. COMMUNICATION CLASSIFICATION

Every outbound message must have one canonical communication purpose before send:

- `TRANSACTIONAL`
- `SERVICE`
- `MARKETING`
- `AUTHENTICATION`

## Classification rule

Marketing intent must not be hidden inside a nominally utility/service message merely to avoid a marketing restriction.

If content contains promotional/re-engagement intent, it must be treated as marketing where the provider's policy requires that classification.

---

# 9. CONSENT MODEL

## 9.1 Marketing opt-in

**LOCKED: marketing communication requires explicit opt-in.**

The consent record must include, where available:

- customer identity;
- tenant;
- communication category;
- channel;
- consent state;
- source;
- timestamp;
- policy/terms version.

The consent must be understandable as permission to receive WhatsApp communication from the named business.

This follows the current WhatsApp Business policy requirement for opt-in and its recommendation to make category expectations clear. citeturn0search0

---

## 9.2 Category-specific consent

**LOCKED: marketing consent is separate from general service/transactional interaction permission.**

A customer contacting a business for support does not automatically become marketing-opted-in.

---

## 9.3 Opt-out

**LOCKED: explicit opt-out immediately suppresses marketing communication.**

Opt-out must be honored whether received:

- through WhatsApp;
- through another approved channel;
- through a tenant-managed preference mechanism.

---

## 9.4 Re-subscription

**LOCKED: marketing suppression can only be removed through a new explicit opt-in.**

Silence, purchase history, previous engagement or AI inference does not restore marketing permission.

---

# 10. LIMIT ENFORCEMENT

## 10.1 Marketing cap reached

**LOCKED enforcement: BLOCK/SUPPRESS.**

Do not silently queue a marketing message for the next period because doing so can create an unexpected future burst.

---

## 10.2 Temporary provider restriction

If the provider reports a temporary restriction:

**LOCKED: SUPPRESS/DEFER according to provider-safe retry policy.**

Do not repeatedly retry marketing sends against a known provider restriction.

---

## 10.3 UNKNOWN delivery

If delivery status is UNKNOWN:

```text
UNKNOWN
→ reconcile
→ determine delivered/not delivered where possible
→ update counter
→ decide retry/suppress
```

Blind retry is forbidden.

---

# 11. EXECUTION-TIME GATE

Before every automated marketing send:

```text
Tenant valid
→ Subscription valid
→ Entitlement valid
→ Recipient valid
→ Marketing opt-in valid
→ No opt-out
→ Current customer state eligible
→ No human takeover conflict
→ Campaign/workflow active
→ Rolling 24h tenant cap available
→ Rolling 30d tenant cap available
→ Recipient 30d cap available
→ Recipient 72h cooldown passed
→ Engagement suppression not active
→ Quiet hours passed
→ Provider/channel available
→ Template/policy validation passed
→ Idempotency check passed
→ Send
→ Verify result
→ Audit
```

Any failed gate means **no automatic send**.

---

# 12. TENANT-WIDE COST GUARD

At 1,000 marketing deliveries/month, the current published-rate benchmark is approximately Rp586,330 before any applicable tax/provider/platform fees. citeturn2search0turn2search1

Therefore:

**LOCKED: the AI BOS marketing cap is a safety boundary, not a promise that marketing messaging is included in the subscription price.**

The billing/usage system must separately record provider communication usage.

No automatic overage purchase is allowed.

---

# 13. WHAT COUNTS TOWARD THE COUNTERS

## Marketing monthly counter

**LOCKED:** count successful/delivered marketing messages.

## Recipient frequency counter

**LOCKED:** count successful/delivered marketing messages.

## Broadcast/campaign execution counter

**LOCKED:** count each initiated execution attempt, including an execution that ultimately produces zero eligible recipients.

## Failed sends

A provider-rejected send that is known not to have been delivered does not consume the delivered-message marketing budget.

However, repeated failed attempts remain auditable and may trigger anti-loop protection.

## UNKNOWN

UNKNOWN does not immediately assume zero.

It enters reconciliation before another potentially duplicate marketing send is authorized.

---

# 14. HUMAN HANDOFF

If a human takes over the conversation:

**LOCKED: conflicting automated marketing communication is suppressed.**

The automation may resume only after the governed handoff state permits it and the normal execution-time gate passes again.

---

# 15. AI AUTHORITY

AI may propose:

- audience;
- timing;
- copy;
- follow-up;
- campaign structure.

AI may execute only if:

- the Tenant is entitled;
- the operating mode permits it;
- policy permits it;
- consent is valid;
- caps are available;
- risk/authority checks pass.

AI cannot:

- self-grant marketing consent;
- override opt-out;
- bypass caps;
- reset counters;
- reclassify marketing as utility to evade controls;
- create a second campaign to bypass the active-campaign limit;
- delegate around a denied send.

---

# 16. LOCKED D-COMM-02 VALUES

| Control | Locked value |
|---|---:|
| Starter marketing campaigns | Disabled |
| Starter marketing broadcasts | Disabled |
| Starter marketing automated follow-up | Disabled |
| Pro monthly marketing deliveries | **1,000 / rolling 30 days / Tenant** |
| Pro unique marketing recipients | **250 / rolling 24 hours / Tenant** |
| Broadcast recipients | **250 / execution** |
| Broadcast executions | **2 / rolling 7 days / Tenant** |
| Active campaigns | **2 / Tenant** |
| Campaign executions | **1 / campaign / rolling 24 hours** |
| Campaign recipients | **250 / execution** |
| Marketing messages / recipient | **3 / rolling 30 days** |
| Marketing cooldown / recipient | **72 hours** |
| Consecutive unengaged marketing sends | **2** |
| Unengaged suppression | **30 days** |
| Marketing follow-ups | **2 / recipient / rolling 30 days** |
| Abandoned-cart follow-ups | **2 / sequence** |
| Marketing quiet hours | **21:00–08:00 recipient-local** |
| Marketing opt-in | **Explicit, category-specific** |
| Opt-out | **Immediate suppression** |
| Re-subscription | **New explicit opt-in** |
| Cap enforcement | **BLOCK/SUPPRESS** |

---

# 17. WHY THESE VALUES ARE LOCKED

These values are not presented as universal WhatsApp limits.

They are AI BOS launch safety limits chosen from:

### A. Provider-policy constraint

WhatsApp requires opt-in, requires respect for opt-out, uses approved templates for business-initiated conversations, and can restrict businesses for poor-quality or unauthorized bulk messaging. citeturn0search0

### B. Recipient-protection constraint

Meta explicitly states that it limits marketing messages to users and recommends monitoring frequency, engagement and cooldowns. citeturn3search0turn3search12

Therefore a per-recipient AI BOS limit is mandatory even though Meta's adaptive internal threshold is not a suitable canonical project number.

### C. Economic constraint

At the current Indonesia benchmark of roughly Rp586.33 per delivered marketing message, 1,000 messages is approximately Rp586k before applicable tax/provider fees. citeturn2search0turn2search1

That is a materially safer launch ceiling than allowing several thousand automated marketing deliveries without an explicit usage budget.

### D. Operational simplicity

A 250-recipient execution ceiling makes every campaign/broadcast auditable, restartable and easier to protect against accidental mass sends.

### E. Anti-bypass design

The limits are intentionally overlapping:

```text
Tenant monthly cap
        +
Tenant rolling-24h cap
        +
Recipient rolling-30d cap
        +
Recipient 72h cooldown
        +
Feature execution cap
        +
Consent
        +
Opt-out
        +
Human takeover
```

An individual control failing must not expose the tenant to unlimited sending.

---

# 18. PROVIDER LIMIT OVERRIDE RULE

The following precedence is LOCKED:

```text
Applicable law / mandatory regulation
        ↓
WhatsApp / provider policy and technical limit
        ↓
AI BOS platform security/safety ceiling
        ↓
Tenant policy
        ↓
Campaign/workflow configuration
```

A lower layer cannot override a higher layer.

Therefore:

`Actual Effective Limit = MIN(all applicable limits)`

This applies even if the AI BOS configured value is higher.

---

# 19. CHANGE CONTROL

The following values are now locked for the current target:

- 1,000 monthly marketing deliveries;
- 250 unique recipients/24h;
- 250 recipients/execution;
- 2 broadcasts/7 days;
- 2 active campaigns;
- 1 campaign execution/24h;
- 3 marketing messages/recipient/30d;
- 72-hour recipient cooldown;
- 2 unengaged sends → 30-day suppression;
- 2 marketing follow-ups/recipient/30d;
- 2 abandoned-cart follow-ups/sequence;
- 21:00–08:00 quiet hours;
- explicit category-specific marketing opt-in;
- immediate opt-out;
- new explicit opt-in for re-subscription;
- block/suppress at cap.

Any modification requires:

`Change Proposal → Impact Audit → Owner Approval → Canonical Registry Update → Traceability Update → Tests`

---

# 20. FINAL STATUS

**D-COMM-02: CLOSED / LOCKED FOR CURRENT MVP/PRO TARGET**

This closure does not claim:

- provider limits are permanent;
- legal policy is permanently settled for every jurisdiction;
- implementation exists;
- tests have passed;
- production is ready.

It means the AI BOS product has a deterministic internal communication-control contract that can now be implemented and tested without inventing numeric campaign/follow-up limits.

**Next controlled work: D-DOC-01.**
