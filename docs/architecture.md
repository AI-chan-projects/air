# AIR Architecture

## Overview

AIR (APOS Intermediate Representation) is a semantic document representation designed for both humans and AI systems.

Rather than treating Markdown as the source of truth, AIR separates semantic meaning from presentation.

Markdown is one possible serialization format.

AIR is the semantic model.

---

# Design Goals

The architecture is designed around the following principles:

- Human-readable
- Machine-readable
- Git-friendly
- AI-native
- Editor-independent
- Serialization-independent

---

# High-Level Architecture

```text
             Human Author
                   │
                   ▼
          Markdown + YAML
                   │
                   ▼
              AIR Parser
                   │
                   ▼
             AIR Document
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
  Validator    Serializer   AI Agents
        │                      │
        ▼                      ▼
  Diagnostics            Reasoning
```

The parser is responsible for transforming serialized documents into AIR Documents.

Once parsed, downstream systems operate on AIR rather than raw Markdown.

---

# Core Components

## Markdown

Markdown is the primary serialization format for AIR.

Responsibilities:

- Human editing
- Version control
- Documentation

Markdown does not define semantics.

---

## YAML Metadata

YAML provides structured metadata for AIR Documents.

Examples include:

- title
- layer
- type
- status
- tags
- related
- source

Metadata is machine-readable and forms part of the document semantics.

---

## Parser

The parser converts serialized AIR documents into structured AIR objects.

Responsibilities:

- Read Markdown
- Parse YAML Frontmatter
- Parse document body
- Extract Wiki Links
- Build AIR Document

The parser performs transformation, not validation.

---

## AIR Document

AIR Document is the canonical in-memory representation.

Example:

```text
AIRDocument
├── metadata
├── content
├── links
├── layer
├── secondary_layers
└── references
```

All downstream components operate on AIR Documents.

---

## Validator

The validator verifies that AIR Documents conform to the AIR Specification.

Examples:

- required metadata
- valid layer
- broken references
- duplicate identifiers
- schema validation

Validation never modifies documents.

---

## Serializer

A serializer converts AIR Documents into external representations.

Possible serializers include:

- Markdown
- JSON
- YAML
- XML
- Database records

Markdown is only one serializer.

---

# Semantic Layers

Every AIR Document belongs to one primary semantic layer.

```text
L1 Reality
L2 Problem
L3 Assumption
L4 Variables
L5 Simulation
L6 Validation
L7 Meta
```

Secondary semantic layers are optional.

Semantic layers classify reasoning rather than document formatting.

---

# Document Lifecycle

```text
Markdown

↓

Parser

↓

AIR Document

↓

Validator

↓

Consumer
```

Consumers may include:

- APOS
- Editors
- Search
- Visualization
- AI agents

---

# Repository Organization

```text
Specification

↓

Reference Implementation

↓

Applications
```

The AIR repository contains:

- specifications
- templates
- parser
- validator
- serializers
- examples

Applications should depend on AIR instead of implementing independent document models.

---

# Architectural Principles

## Semantics Before Presentation

Formatting must never alter semantic meaning.

AIR owns semantics.

Markdown owns presentation.

---

## One Primary Concept per Document

Each AIR Document represents one primary concept.

Relationships between concepts are expressed through references rather than deeply nested documents.

---

## Structured Metadata

Metadata is part of the document model.

Metadata should never be inferred from formatting.

---

## Explicit Relationships

Documents communicate through explicit references.

Examples:

```text
[[Reality]]

[[Validation]]

[[Design Principles]]
```

Relationships should remain visible and machine-readable.

---

## Separation of Concerns

AIR separates distinct responsibilities.

```text
Markdown
    │
Serialization

↓

Parser
    │
Transformation

↓

AIR
    │
Semantics

↓

Validator
    │
Verification

↓

Applications
    │
Reasoning
```

Each layer has a single responsibility.

---

# Future Extensions

Future versions of AIR may include:

- AIR AST
- Query Language
- Graph Model
- Multiple serializers
- Schema evolution
- Plugin system
- Language Server Protocol (LSP)

These extensions should preserve backward compatibility with the AIR Specification whenever possible.

---

# Summary

AIR is a semantic representation layer positioned between human-authored documents and AI reasoning systems.

Its purpose is to provide a stable, structured, and implementation-independent representation of knowledge.

Applications such as APOS consume AIR Documents rather than raw Markdown, ensuring that reasoning remains independent of presentation.