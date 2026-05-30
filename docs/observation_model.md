# Observation Model

## Purpose

Observations represent raw evidence.

Observations are not considered truth.

They are inputs used to derive validated semantic relationships.

## Sources

- Public CTI reports
- ATT&CK procedure examples
- Incident response reports
- Malware analysis
- Community contributions
- Internal telemetry

## Properties

Each observation should capture:

- Source technique
- Target technique
- Environment
- Threat actor (if known)
- Evidence source
- Analyst notes
- Confidence
- Observation date

## Lifecycle

Observation
    ↓
Validation
    ↓
Aggregation
    ↓
Semantic Edge Candidate
    ↓
Reviewer Approval
    ↓
Semantic Edge
