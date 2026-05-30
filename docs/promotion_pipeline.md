# Promotion Pipeline

## Purpose

The promotion pipeline governs how observations become validated semantic relationships.

The graph does not accept behavioral relationships directly.

All semantic edges must originate from observations.

---

## Lifecycle

Observation
→ Validation
→ Aggregation
→ Edge Candidate
→ Reviewer Approval
→ Semantic Edge

---

## Stage 1: Observation

Requirements:

- Source technique exists in ATT&CK
- Target technique exists in ATT&CK
- Evidence source provided
- Relationship type proposed

Status:
OBSERVED

---

## Stage 2: Validation

Checks:

- Technique IDs valid
- Environment taxonomy valid
- Relationship type exists
- Source document accessible

Status:
VALIDATED

---

## Stage 3: Aggregation

The system groups similar observations.

Example:

T1059.001 → T1003

observed in:

- Mandiant 2023
- Microsoft 2024
- CrowdStrike 2024

Status:
AGGREGATED

---

## Stage 4: Candidate Edge

Requirements:

- Minimum observations: 3
- Minimum unique sources: 2
- Minimum confidence threshold: 0.70

Status:
CANDIDATE

---

## Stage 5: Reviewer Approval

Reviewer checks:

- Evidence quality
- Attribution quality
- Relationship appropriateness
- Confidence score

Status:
APPROVED

---

## Stage 6: Semantic Edge

Relationship becomes part of the graph.

Status:
ACTIVE
