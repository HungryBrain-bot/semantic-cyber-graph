# Semantic Edge Model

## Purpose

Semantic edges represent validated adversary behavioral knowledge.

Unlike observations, semantic edges are considered approved graph knowledge.

---

## Core Principles

1. Every semantic edge must originate from observations.

2. Every semantic edge must have evidence.

3. Every semantic edge must have confidence.

4. Every semantic edge must be reviewable.

5. Every semantic edge must be versioned.

---

## Components

### Relationship

Defines the behavioral connection.

Examples:

- TEMPORALLY_PRECEDES
- CAUSALLY_ENABLES
- REQUIRES
- OBSERVED_WITH
- SUPPORTS_OBJECTIVE

---

### Confidence

Represents belief strength.

Range:

0.0 - 1.0

Sources:

- Observation count
- Evidence quality
- Reviewer validation

---

### Context

Defines where the relationship applies.

Examples:

- Windows
- Azure AD
- Hybrid
- Kubernetes

---

### Evidence

Supports the relationship.

Examples:

- CTI report
- Malware analysis
- ATT&CK procedure example
- Incident response report

---

### Metadata

Tracks governance.

Examples:

- Created date
- Reviewer
- Schema version
- Edge version
