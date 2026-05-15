Procedural Semantics Gap
Overview

MITRE ATT&CK is one of the most valuable cybersecurity knowledge frameworks ever created.

It successfully standardizes:

attacker techniques
tactics
malware
tools
intrusion sets
mitigations
detections

However, ATT&CK primarily models adversary behavior as categorized techniques.

It does not deeply model:

procedural sequencing
probabilistic attack flow
operational dependencies
environment-aware behavior
attacker intent progression
temporal semantics

This project refers to that missing layer as:

The Procedural Semantics Gap
Why This Matters

Security operations are fundamentally behavioral.

Analysts rarely investigate isolated techniques.

They investigate:

attack chains
behavioral progression
likely next steps
operational objectives
procedural attacker movement

Example:

An analyst observes:

PowerShell execution
suspicious authentication behavior

The analyst immediately begins reasoning:

What commonly follows this?
Is credential dumping likely next?
Is lateral movement probable?
Which detections should be enabled immediately?

ATT&CK alone does not answer these questions.

Analysts infer them manually.

Current Industry Problem

Most procedural attack knowledge exists in:

CTI reports
IR case notes
analyst experience
threat hunting playbooks
red team knowledge

This knowledge is:

unstructured
fragmented
difficult to reuse
difficult to validate
difficult to operationalize

Organizations repeatedly rediscover the same behavioral patterns.

Example Gap

ATT&CK can represent:

APT29 uses PowerShell

But not deeply:

In hybrid Azure AD intrusions,
PowerShell execution is commonly observed
before credential dumping activity
with moderate-to-high confidence
within a 1-10 hour operational window.

That procedural knowledge currently lives mostly in analyst reasoning.

Proposed Direction

This project explores whether procedural adversary behavior can become:

graph-native
semantic
evidence-backed
queryable
operationally useful

The system introduces semantic relationships such as:

TEMPORALLY_PRECEDES
CAUSALLY_ENABLES
REQUIRES
LIKELY_FOLLOWED_BY

These relationships include:

confidence
evidence
environment
temporal characteristics
attacker objectives
validation metadata
Intended Outcome

The goal is not predictive AI.

The goal is structured behavioral intelligence.

Eventually the graph should support:

procedural traversal
threat-informed defense analysis
detection coverage analysis
operational reasoning
graph-backed natural language querying
