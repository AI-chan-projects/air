# AIR Roadmap

## Purpose

This roadmap outlines the planned evolution of AIR (APOS Intermediate Representation).

The roadmap prioritizes validating the AIR Specification before expanding into advanced tooling or AI integration.

Each phase builds upon the previous one while keeping the AIR Specification stable and implementation-independent.

---

# Guiding Principles

Development follows these priorities:

1. Specification first
2. Reference implementation second
3. Tooling third
4. Ecosystem fourth

AIR should remain a semantic specification rather than an application.

---

# Phase 0 - Foundation

**Status:** Done

## Objectives

Establish the core identity of AIR.

### Deliverables

- Project repository
- Apache 2.0 License
- README
- Architecture documentation
- Philosophy documentation
- Roadmap
- Architecture Decision Records (ADRs)

---

# Phase 1 - AIR Specification

**Status:** Done

## Objectives

Define the complete AIR Specification.

### Deliverables

- Specification overview
- Markdown serialization specification
- YAML metadata schema
- L7 semantic layer specification
- Validation specification

### Success Criteria

- Stable document structure
- Stable metadata model
- Stable semantic model

---

# Phase 2 - Reference Implementation

**Status:** In Progress

## Objectives

Develop the first Python reference implementation.

### Deliverables

- Markdown parser
- YAML parser
- AIR Document model
- Validator
- Serializer
- Unit tests

### Success Criteria

- AIR Documents parse correctly
- Validation is deterministic
- Round-trip serialization preserves semantics

---

# Phase 3 - Editor Prototype

**Status:** Planned

## Objectives

Build a lightweight editor for AIR Documents.

### Deliverables

- Document browser
- Markdown editor
- YAML editor
- Live preview
- Validation panel

### Optional Features

- Graph view
- L7 layer filtering
- Document search

### Success Criteria

- AIR Documents can be created and edited without manual YAML management

---

# Phase 4 - AIR SDK

**Status:** Planned

## Objectives

Provide reusable libraries for working with AIR.

### Deliverables

- Python SDK
- Public API
- Documentation
- Example projects

### Possible APIs

- Parse AIR Documents
- Validate documents
- Serialize documents
- Query metadata

---

# Phase 5 - Ecosystem

**Status:** Planned

## Objectives

Enable third-party adoption.

### Possible Projects

- VS Code extension
- Obsidian plugin
- CLI tools
- Static documentation generator
- Graph visualization

### Success Criteria

AIR can be used independently of APOS.

---

# Phase 6 - APOS Integration

**Status:** Planned

## Objectives

Integrate AIR into APOS.

### Deliverables

- Planner support
- Observer support
- Memory integration
- Policy integration

### Success Criteria

APOS operates on AIR Documents rather than raw Markdown.

---

# Future Vision

Future AIR development may include:

- AIR Abstract Syntax Tree (AST)
- AIR Query Language
- Ontology support
- Graph-based knowledge representation
- Language Server Protocol (LSP)
- Multi-language reference implementations
- Additional serialization formats

These features should extend AIR without changing its core semantic model.

---

# Non-Goals

The AIR project does not aim to become:

- a note-taking application
- a knowledge management platform
- a workflow engine
- an AI agent framework
- a cloud synchronization service

These capabilities belong to applications that consume AIR.

---

# Milestones

| Milestone | Goal |
|-----------|------|
| M1 | AIR Specification v0.1 |
| M2 | Python Parser & Validator |
| M3 | Editor Prototype |
| M4 | AIR SDK v0.1 |
| M5 | AIR v1.0 Specification |
| M6 | APOS Integration |

---

# Long-Term Direction

AIR is intended to become a stable semantic representation for structured knowledge.

As AI systems evolve, AIR should provide a consistent foundation that remains:

- implementation-independent
- human-readable
- machine-readable
- interoperable
- extensible

The long-term success of AIR is measured not by the number of features it contains, but by the stability and clarity of the semantic model it provides.

---

# Summary

The AIR roadmap emphasizes incremental development:

```text
Foundation
      ↓
Specification
      ↓
Reference Implementation
      ↓
Editor
      ↓
SDK
      ↓
Ecosystem
      ↓
APOS Integration
```

By validating the specification before expanding the ecosystem, AIR can evolve into a reliable semantic foundation for knowledge representation across applications and AI systems.