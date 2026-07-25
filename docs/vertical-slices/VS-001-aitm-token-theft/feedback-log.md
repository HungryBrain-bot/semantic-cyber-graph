# 🗣️ VS-001 · Practitioner Feedback Log

> **Vertical Slice:** AiTM Token Theft → Mailbox Manipulation  
> **Purpose:** Preserve criticism, corrections, disagreements, and model changes  
> **Status:** Awaiting practitioner review

[← Telemetry & Coverage](telemetry-and-coverage.md) · [Back to VS-001](README.md)

---

## Why feedback is part of the model

This vertical slice is not validated because the documentation looks convincing.

It becomes more trustworthy only when experienced practitioners challenge:

- the attack sequence,
- the semantic edge types,
- the evidence quality,
- the telemetry assumptions,
- the detection coverage,
- and the expected investigation output.

> **Agreement is useful. Specific disagreement is more valuable.**

---

## Privacy rule

Do not publish a participant's name, employer, customer environment, incident details, or proprietary detection logic without explicit permission.

Use role-based descriptions by default:

```text
Senior Detection Engineer
Microsoft 365 Incident Responder
Threat Intelligence Analyst
Security Researcher
```

---

## Questions for the first review

### Experience-first questions

1. Can you walk through a real investigation involving stolen Microsoft 365 session access?
2. Which systems and data sources did you open?
3. Where was the most time lost?
4. Which connections did you have to make manually?
5. What evidence was missing or difficult to trust?

### Model-review questions

6. Is this attack boundary realistic?
7. Which stages are missing?
8. Which relationships are incorrectly labeled as causal, temporal, or likely?
9. Which behaviors are too campaign-specific to generalize?
10. What benign activity could resemble this progression?
11. Which telemetry assumptions are wrong?
12. Which Microsoft products already correlate part of this chain?
13. Would the proposed output change an investigation or detection decision?
14. What would prevent you from trusting it?

### Falsification question

> **What assumption in this vertical slice is most likely to be wrong?**

---

## Feedback summary dashboard

| ID | Reviewer role | Main challenge | Model impact | Status |
|---|---|---|---|---|
| `FB-001` | Pending | — | — | Not scheduled |
| `FB-002` | Pending | — | — | Not scheduled |
| `FB-003` | Pending | — | — | Not scheduled |

---

## Feedback session template

### FB-XXX · Review title

| Field | Value |
|---|---|
| Date | |
| Reviewer role | |
| Years of experience | |
| Environment focus | |
| Name publication approved | No |
| Employer publication approved | No |
| Recording approved | No |

#### 1. Real investigation described

Summarize the workflow without exposing sensitive details.

#### 2. What resonated

-

#### 3. What was incorrect or overstated

-

#### 4. Missing behaviors

-

#### 5. Missing or incorrect telemetry

-

#### 6. Existing tools or workflows mentioned

-

#### 7. Semantic-edge corrections

| Existing edge | Reviewer concern | Proposed change | Decision |
|---|---|---|---|
| | | | |

#### 8. Evidence requested

-

#### 9. Would the output improve a decision?

- [ ] Yes
- [ ] Partially
- [ ] No
- [ ] Cannot determine yet

**Reasoning:**

#### 10. Changes required

-

#### 11. Project decision

- [ ] No change
- [ ] Documentation correction
- [ ] Relationship type changed
- [ ] Edge moved back to hypothesis
- [ ] New evidence required
- [ ] Scope changed
- [ ] Hypothesis weakened
- [ ] Hypothesis rejected

#### 12. Changes implemented

-

---

## Decision log

Every material change caused by practitioner feedback should be recorded here.

| Decision | Previous model | New model | Evidence or feedback | Date |
|---|---|---|---|---|
| `FD-001` | — | — | — | — |

### Example decision format

```markdown
### FD-XXX · Relationship downgraded

**Previous**
Mailbox access CAUSALLY_ENABLES inbox-rule manipulation.

**Challenge**
The reviewer explained that mailbox access only provides the opportunity;
rule creation is objective-dependent and not causally required.

**Decision**
Change the edge to LIKELY_FOLLOWED_BY and restrict it to evidence-backed
campaign contexts.

**Affected files**
- attack-chain.md
- semantic-gaps.md
- evidence.md
```

---

## Contradictions register

Do not remove a disagreement merely because a final decision was made.

| ID | Claim | Supporting view | Conflicting view | Resolution |
|---|---|---|---|---|
| `CR-001` | Pending | — | — | Open |

---

## Validation targets

VS-001 should receive feedback from at least:

- [ ] One senior detection engineer
- [ ] One identity or Microsoft 365 incident responder
- [ ] One threat-intelligence analyst or security researcher

Ideal additional reviewers:

- [ ] Microsoft Sentinel content engineer
- [ ] Defender XDR specialist
- [ ] Exchange Online security specialist
- [ ] ATT&CK contributor or detection-content maintainer

---

## What good feedback looks like

Useful:

- “This relationship is correlation, not causality.”
- “That event is not available under the licensing assumptions.”
- “The actor often accesses SharePoint before Exchange.”
- “The same pattern appears during legitimate mailbox migration.”
- “Product X already correlates these two stages.”
- “The time window is unsupported.”
- “This output would not change my next action because...”

Less useful:

- “Looks great.”
- “Interesting idea.”
- “AI will solve this.”
- “Knowledge graphs are powerful.”

---

## Exit criteria

- [ ] At least two experienced practitioners review the model.
- [ ] Critical feedback is recorded faithfully.
- [ ] Every accepted change is linked to the relevant file.
- [ ] Remaining disagreements stay visible.
- [ ] The project states whether the original hypothesis became stronger, weaker, or was rejected.
- [ ] No reviewer identity or sensitive incident detail is published without permission.

---

<div align="center">

### The goal is not to defend the first model.  
### The goal is to make the final model defensible.

[← Back to VS-001](README.md)

</div>
