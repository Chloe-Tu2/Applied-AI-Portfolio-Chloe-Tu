# Project 11 — Build and Evaluate a Small Knowledge Base

## Project Overview

This project builds a small knowledge base (KB) from scratch—a structured collection of entities, relationships, and facts—and then evaluates its quality by testing coverage, accuracy, and internal consistency.

## Problem Statement

Knowledge bases underpin question-answering systems, recommendation engines, and enterprise search. Building one forces decisions about scope, schema, entity resolution, and how to handle conflicting or incomplete information. Evaluating one forces measurement of the gaps that building alone does not reveal.

## Approach and Methodology

- Defined a narrow domain and scope for the KB
- Designed a schema: entity types, relationship types, and attribute types
- Populated the KB from source documents, making explicit decisions about disambiguation, normalization, and conflict resolution
- Evaluated by: checking coverage against a set of expected queries, verifying a sample of facts against sources, and testing for internal contradictions

## Results and Evaluation

The KB was populated with a defined number of entities and relationships. Evaluation against test queries revealed coverage gaps—questions the KB could not answer because the relevant entities or relationships were not included. A sample of facts was verified against sources, with a small number of errors found and corrected.

## Learning Outcomes & Reflection

- **Difficult:** Entity resolution (deciding when two mentions refer to the same entity) was the hardest part. Inconsistent naming across sources created ambiguity that required manual judgment.
- **What failed:** The initial schema was too broad—tried to cover too many entity types and ended up with shallow coverage of each. Narrowing scope improved depth.
- **What would change:** Would start with a set of target queries and work backward to determine what entities and relationships are needed, rather than trying to capture "everything" in the domain.

## Project Files

| File | Description |
|------|-------------|
| `P11-Build-and-Evaluate-a-Small-Knowledge-Base.pdf` | Knowledge base design, build, and evaluation document |

## Project Structure

```
Project-11-Build-and-Evaluate-a-Small-Knowledge-Base/
├── README.md
└── P11-Build-and-Evaluate-a-Small-Knowledge-Base.pdf
```

## Dependencies / Requirements

No code or special software required. PDF viewer only.

## Data Access

Source documents used to populate the KB are referenced in the deliverable. No data files are included.

## Course Context

**ITAI 3375 – Curating Data for A.I. Optimization**, Houston City College. Assignment on structured knowledge construction—relevant to roles in knowledge engineering and enterprise AI.
