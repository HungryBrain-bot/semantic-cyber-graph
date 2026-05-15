Architecture Vision
Core Principle

The graph is the source of truth.

LLMs are interface layers.

All reasoning must originate from validated graph relationships.

System Layers
Layer 1 — ATT&CK Foundation

MITRE ATT&CK provides:

techniques
sub-techniques
groups
malware
tools
mitigations
base relationships

ATT&CK acts as the foundational ontology.

Layer 2 — Observation Layer

Raw behavioral observations are ingested before semantic promotion.

Example:

{
  "source_technique": "T1059.001",
  "target_technique": "T1003",
  "source_report": "Mandiant 2023"
}

Observations are not automatically treated as truth.

This layer preserves:

provenance
evidence
uncertainty
analyst attribution
Layer 3 — Semantic Edge Layer

Multiple observations may contribute toward validated semantic relationships.

Example:

{
  "relationship": "TEMPORALLY_PRECEDES",
  "confidence": 0.82
}

Semantic edges contain:

confidence scoring
evidence metadata
operational context
environment taxonomy
temporal semantics
attacker objectives
Layer 4 — Traversal Layer

The graph becomes queryable through:

procedural traversal
confidence-weighted traversal
environment-aware filtering
objective-driven traversal
Layer 5 — AI Interface Layer

LLMs do not generate behavioral truth.

LLMs:

retrieve graph context
summarize intelligence
explain procedural relationships
convert natural language into graph queries

This architecture intentionally prevents hallucinated behavioral intelligence.

Design Philosophy
Semantic Discipline

Relationship vocabulary remains controlled.

Semantic meaning must remain stable.

Ontology growth must be governed.

Evidence Awareness

Every semantic relationship requires:

evidence
provenance
confidence
validation metadata
Incremental Evolution

The system evolves gradually.

Operational utility takes priority over ontology complexity.

Long-Term Direction

Potential future areas:

Graph RAG
semantic CTI enrichment
SIEM coverage analysis
procedural attack simulation
probabilistic traversal
ontology interoperability
JSON-LD / RDF experimentation
