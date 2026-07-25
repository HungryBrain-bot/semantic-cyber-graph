# 📚 VS-001 · Evidence Register

> **Vertical Slice:** AiTM Token Theft → Mailbox Manipulation  
> **Role:** Source-of-evidence ledger for every behavioral claim  
> **Status:** Initial authoritative sources identified; detailed review pending

[← Semantic Gaps](semantic-gaps.md) · [Back to VS-001](README.md)

---

## Evidence policy

A URL is not evidence by itself.

Every accepted record must state:

- the exact behavioral claim supported,
- whether the behavior was directly observed or inferred,
- the environment and scope,
- the relevant section or passage,
- the relationship it may support,
- the limitations of the source,
- and the validation decision.

> **The evidence register supports the graph. The graph must not outrun the evidence register.**

---

## Validation states

| State | Meaning |
|---|---|
| `SOURCE IDENTIFIED` | Collected, but not fully reviewed |
| `UNDER REVIEW` | Exact claims and limitations are being extracted |
| `SUPPORTED` | The source directly supports the documented claim |
| `CORROBORATED` | Independent sources support the same relationship |
| `CONFLICTED` | Credible sources disagree or describe incompatible contexts |
| `REJECTED` | The source does not support the proposed claim |
| `OUTDATED` | The content no longer reflects the relevant platform or technique state |

---

## Source quality dimensions

Each evidence record should be judged across:

| Dimension | Questions |
|---|---|
| Authority | Is the publisher authoritative for the claim? |
| Directness | Was the behavior directly observed or inferred? |
| Specificity | Does the source describe the exact environment and behavior? |
| Independence | Is it independent of other cited sources? |
| Recency | Is the source still operationally relevant? |
| Reproducibility | Are timestamps, events, queries, or artifacts provided? |
| Bias | Is the source primarily product marketing or technical reporting? |

---

## Initial source inventory

These are **candidate sources**, not yet approved graph evidence.

### EV-001 · Microsoft Defender XDR session-cookie theft investigation guidance

- **Publisher:** Microsoft Learn
- **Type:** Product investigation guidance
- **URL:** https://learn.microsoft.com/en-us/defender-xdr/session-cookie-theft-alert
- **Potentially supports:**
  - AiTM phishing can be used to steal credentials or an authenticated session.
  - Defender XDR exposes alerts related to stolen session-cookie use and AiTM authentication.
  - Follow-on mailbox activity should be investigated.
- **Candidate relationships:**
  - AiTM authentication → session material theft
  - suspicious session use → mailbox investigation
- **Limitations:**
  - Product guidance does not establish population-level transition probability.
  - Alert logic and licensing must be documented separately.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-002 · MITRE ATT&CK T1539 — Steal Web Session Cookie

- **Publisher:** MITRE ATT&CK
- **Type:** Technique definition
- **URL:** https://attack.mitre.org/techniques/T1539/
- **Potentially supports:**
  - Session cookies can provide authenticated access without re-entering credentials.
  - Malicious proxies used in AiTM phishing can capture session cookies.
  - A stolen cookie may later be used through Web Session Cookie.
- **Candidate relationships:**
  - AiTM proxy → session-cookie theft
  - cookie theft → possible cookie use
- **Limitations:**
  - ATT&CK describes capability and procedures; it does not provide a transition probability for this slice.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-003 · MITRE ATT&CK T1550.004 — Web Session Cookie

- **Publisher:** MITRE ATT&CK
- **Type:** Technique definition
- **URL:** https://attack.mitre.org/techniques/T1550/004/
- **Potentially supports:**
  - Stolen session cookies may be reused to authenticate to cloud or web services.
  - Reused sessions can provide access to sensitive information and email.
- **Candidate relationships:**
  - session-cookie theft → session-cookie use
  - session-cookie use → authenticated resource access
- **Limitations:**
  - Does not prove that Exchange Online is accessed in every observed case.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-004 · Microsoft — From cookie theft to BEC

- **Publisher:** Microsoft Security Blog
- **Publication date:** 2022-07-12
- **Type:** Threat-research report
- **URL:** https://www.microsoft.com/en-us/security/blog/2022/07/12/from-cookie-theft-to-bec-attackers-use-aitm-phishing-sites-as-entry-point-to-further-financial-fraud/
- **Potentially supports:**
  - AiTM phishing can steal passwords and authenticated sessions despite MFA.
  - Stolen sessions may be used to access Exchange Online.
  - Follow-on activity may include business email compromise.
- **Candidate relationships:**
  - AiTM phishing → authenticated-session theft
  - session use → Exchange Online access
- **Limitations:**
  - Campaign-specific reporting must not be generalized without corroboration.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-005 · Microsoft — Multi-stage AiTM and BEC campaign abusing SharePoint

- **Publisher:** Microsoft Security Blog
- **Publication date:** 2026-01-21
- **Type:** Threat-research report
- **URL:** https://www.microsoft.com/en-us/security/blog/2026/01/21/multistage-aitm-phishing-bec-campaign-abusing-sharepoint/
- **Potentially supports:**
  - AiTM compromise can be followed by sign-in from another IP.
  - Post-compromise mailbox-rule activity may delete or conceal incoming email.
- **Candidate relationships:**
  - session compromise → later account access
  - account access → inbox-rule manipulation
- **Limitations:**
  - One campaign cannot define a universal behavioral sequence.
  - Precise timing and victim environment must be extracted during review.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-006 · MITRE ATT&CK T1114.002 — Remote Email Collection

- **Publisher:** MITRE ATT&CK
- **Type:** Technique definition
- **URL:** https://attack.mitre.org/techniques/T1114/002/
- **Potentially supports:**
  - Office 365 or Exchange services can be accessed remotely using credentials or access tokens to collect email.
- **Candidate relationships:**
  - authenticated cloud access → remote email collection
- **Limitations:**
  - Technique applicability does not establish likelihood after session reuse.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-007 · MITRE ATT&CK T1114.003 — Email Forwarding Rule

- **Publisher:** MITRE ATT&CK
- **Type:** Technique definition
- **URL:** https://attack.mitre.org/techniques/T1114/003/
- **Potentially supports:**
  - Adversaries may create forwarding rules to collect sensitive information.
  - Rules may support continued access to messages after credential remediation.
- **Candidate relationships:**
  - mailbox access → forwarding-rule creation
- **Limitations:**
  - Does not quantify frequency or prove the rule follows every mailbox compromise.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-008 · MITRE ATT&CK T1564.008 — Email Hiding Rules

- **Publisher:** MITRE ATT&CK
- **Type:** Technique definition
- **URL:** https://attack.mitre.org/techniques/T1564/008/
- **Potentially supports:**
  - Inbox rules may be used to delete, move, or hide email.
  - Rule manipulation may conceal security messages or attacker activity.
- **Candidate relationships:**
  - mailbox access → email-hiding-rule creation
- **Limitations:**
  - Must distinguish ordinary mailbox automation from adversarial concealment.
- **Status:** `SOURCE IDENTIFIED`

---

### EV-009 · Microsoft Purview audit records for Exchange activity

- **Publisher:** Microsoft Learn
- **Type:** Product telemetry documentation
- **URL:** https://learn.microsoft.com/en-us/purview/audit-log-exchange-properties
- **Potentially supports:**
  - Exchange audit records expose operations relevant to mailbox access and inbox-rule activity.
  - Operations such as `New-InboxRule`, `Set-InboxRule`, and `MailItemsAccessed` may support investigation.
- **Candidate relationships:**
  - mailbox behavior → observable audit evidence
- **Limitations:**
  - Availability, fields, licensing, retention, and audit configuration require validation.
  - An event records activity; it does not independently prove malicious intent.
- **Status:** `SOURCE IDENTIFIED`

---

## Evidence-to-edge matrix

| Evidence | Proposed source behavior | Relationship | Proposed target behavior | Current decision |
|---|---|---|---|---|
| EV-001, EV-002 | AiTM-proxied authentication | `CAUSALLY_ENABLES` | Session material theft | Hypothesis |
| EV-002, EV-003 | Session material theft | `LIKELY_FOLLOWED_BY` | Session reuse | Hypothesis |
| EV-003, EV-004 | Session reuse | `CAUSALLY_ENABLES` | Authenticated Microsoft 365 access | Hypothesis |
| EV-004, EV-006 | Authenticated cloud access | `LIKELY_FOLLOWED_BY` | Remote email collection | Hypothesis |
| EV-005, EV-007 | Mailbox access | `LIKELY_FOLLOWED_BY` | Forwarding-rule manipulation | Hypothesis |
| EV-005, EV-008 | Mailbox access | `LIKELY_FOLLOWED_BY` | Email-hiding-rule manipulation | Hypothesis |
| EV-001, EV-009 | Mailbox behavior | `OBSERVABLE_IN` | Microsoft security and audit telemetry | Hypothesis |

---

## Detailed review template

Copy this section for every source after reading it completely.

```markdown
### EV-XXX · Source title

**Publisher:**  
**Publication date:**  
**URL:**  
**Source type:**  
**Reviewer:**  
**Review date:**  

#### Exact behavioral claim

State only what the source supports.

#### Source passage or section

Record the relevant section, figure, event sequence, or timestamp.

#### Candidate semantic edge

Source behavior
    └── RELATIONSHIP_TYPE
        └── Target behavior

#### Environment

- Platform:
- Identity configuration:
- Mail platform:
- Campaign or actor:
- Known controls:
- Unknown controls:

#### Observation type

- [ ] Directly observed
- [ ] Reported by responders
- [ ] Derived from telemetry
- [ ] Inferred by the source
- [ ] Inferred by this project

#### Limitations

-

#### Contradictory evidence

-

#### Decision

- [ ] Supported
- [ ] Corroborated
- [ ] Conflicted
- [ ] Rejected
- [ ] Unknown
```

---

## Review backlog

- [ ] Extract exact ordered behaviors from EV-004.
- [ ] Extract timestamps and mailbox actions from EV-005.
- [ ] Confirm whether EV-001 describes required investigation telemetry.
- [ ] Verify current ATT&CK versions and technique boundaries.
- [ ] Identify at least two independent non-Microsoft campaign sources.
- [ ] Separate vendor product guidance from campaign evidence.
- [ ] Identify benign explanations for each mailbox activity.
- [ ] Record contradictory or non-sequential observations.

---

## Navigation

[← Semantic Gaps](semantic-gaps.md) ·
[Back to VS-001](README.md) ·
[Telemetry & Coverage →](telemetry-and-coverage.md)
