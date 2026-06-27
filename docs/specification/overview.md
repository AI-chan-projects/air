# AIR Specification Overview

## Purpose

This document provides an overview of the AIR (APOS Intermediate Representation) Specification.

AIR defines a semantic representation for knowledge that can be shared consistently between humans and AI systems.

The specification describes **what an AIR Document is**, **how it is represented**, and **how its semantics are preserved**, independent of any specific implementation.

---

# Objectives

The AIR Specification aims to:

- define a stable semantic document model
- separate semantics from presentation
- support human-authored knowledge
- enable machine interpretation
- remain independent of editors, storage formats, and AI models

AIR is intended to be implementation-independent.

---

# What is AIR?

AIR is a semantic intermediate representation for knowledge.

It serves as the layer between human-authored documents and systems that consume structured knowledge.

```text
Human Knowledge

↓

AIR Specification

↓

AIR Document

↓

Applications
```

Applications may include:

- APOS
- AI agents
- Editors
- Search systems
- Visualization tools
- Knowledge management platforms

---

# Core Principles

The AIR Specification is based on the following principles.

## Semantics Before Presentation

Meaning must not depend on formatting.

Presentation exists for readability.

Semantics exist for reasoning.

---

## Human-Readable

AIR Documents should remain easy to:

- read
- write
- review
- version

Humans remain the primary authors.

---

## Machine-Readable

AIR Documents should be parsed into structured semantic objects.

Applications should operate on structured AIR Documents rather than raw text whenever possible.

---

## Representation Independence

AIR defines semantics.

Serialization formats define representation.

Markdown is currently the primary serialization format, but AIR is not limited to Markdown.

---

## Explicit Knowledge

Knowledge should be represented explicitly rather than inferred from formatting or document layout.

Semantic intent should always be visible within the document model.

---

# Specification Components

The AIR Specification consists of several complementary documents.

| Document | Purpose |
|----------|---------|
| overview.md | Overview of the AIR Specification |
| markdown.md | Markdown serialization rules |
| yaml-schema.md | Metadata schema |
| l7.md | Semantic layer model |
| validation.md | Validation requirements |

Each document defines a separate aspect of AIR.

---

# AIR Document

An AIR Document consists of:

```text
YAML Metadata

↓

Markdown Content

↓

Semantic Layer

↓

References
```

The AIR Document is the canonical unit of knowledge within AIR.

Each document should describe one primary concept.

---

# Semantic Model

AIR organizes knowledge using the L7 Semantic Layer.

```text
L1 Reality

↓

L2 Problem

↓

L3 Assumption

↓

L4 Variables

↓

L5 Simulation

↓

L6 Validation

↓

L7 Meta
```

These layers classify the semantic role of documents rather than their storage location or visual appearance.

---

# Architecture

Conceptually, AIR occupies the layer between serialization and reasoning.

```text
Serialization

↓

AIR

↓

Applications
```

Applications consume AIR Documents instead of interpreting formatting directly.

---

# Conformance

An implementation conforms to the AIR Specification if it:

- correctly interprets AIR metadata
- preserves AIR semantics
- supports the required document model
- validates documents according to the specification

Implementations may extend AIR provided they do not alter its defined semantics.

---

# Versioning

The AIR Specification follows semantic versioning.

Major versions may introduce incompatible changes.

Minor versions extend the specification while preserving compatibility.

Patch versions clarify or correct the specification without changing semantics.

---

# Relationship with APOS

AIR was originally developed as part of APOS.

It is maintained as an independent specification so that any application may adopt AIR as its semantic document model.

```text
Knowledge

↓

AIR

↓

APOS

↓

Reasoning
```

APOS is one implementation that consumes AIR.

AIR itself is application-independent.

---

# Future Evolution

Future versions of AIR may introduce:

- additional serialization formats
- richer semantic metadata
- ontology integration
- query languages
- graph representations
- language server support

Such extensions should preserve the core semantic principles defined by this specification.

---

# Summary

The AIR Specification defines a stable, implementation-independent semantic representation for knowledge.

Its purpose is to ensure that knowledge retains the same meaning regardless of how it is authored, stored, rendered, or processed.

AIR separates **what knowledge means** from **how knowledge is represented**, providing a common foundation for collaboration between humans and AI systems.