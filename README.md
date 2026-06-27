# AIR

> **APOS Intermediate Representation**
OR
> **AI Intermediate Representation**

AIR is a semantic document representation designed for AI-assisted reasoning systems.

It defines a structured way to represent knowledge independently of presentation, enabling humans and AI agents to share the same semantic understanding.

Markdown is treated as a serialization format, while AIR remains the source of semantic truth.

---

## Why AIR?

Traditional Markdown documents are optimized for human readers.

AIR extends Markdown with structured metadata and semantic rules so that both humans and AI systems can interpret documents consistently.

AIR is designed around four principles:

- Human-readable
- Machine-readable
- Git-friendly
- AI-native

---

## Core Concepts

An AIR document consists of:

- YAML metadata
- Markdown content
- L7 semantic classification
- Document references

AIR separates:

- **Semantics** (meaning)
- **Representation** (format)
- **Reasoning** (interpretation)

Formatting should never change meaning.

---

## L7 Semantic Layers

Every AIR document belongs to one primary semantic layer.

| Layer | Purpose |
|--------|---------|
| L1 | Reality |
| L2 | Problem |
| L3 | Assumption |
| L4 | Variables |
| L5 | Simulation |
| L6 | Validation |
| L7 | Meta |

Secondary layers are optional.

---

## Repository Structure

```text
docs/          Specifications

adrs/          Architecture Decision Records

templates/     Official AIR document templates

examples/      Example AIR documents

air/           Reference implementation

tests/         Parser and validator tests
```

---

## Project Goals

The first Proof of Concept focuses on:

- AIR document model
- Markdown parser
- YAML metadata
- L7 semantic layers
- Validation
- Reference implementation

The PoC intentionally excludes:

- AI agents
- Workflow execution
- Cloud synchronization
- APOS runtime

---

## Relationship with APOS

AIR is developed as an independent project.

APOS uses AIR as its semantic document representation.

```text
Markdown
      ↓

AIR

      ↓

APOS

      ↓

AI Agents
```

---

## License

Apache License 2.0

---

## Status

This project is currently in the Proof of Concept stage.

The specification may evolve before reaching version 1.0.
