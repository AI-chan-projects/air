# Markdown Serialization Specification
## Purpose
This document defines how AIR Documents are serialized using Markdown.
Markdown is the primary human-readable serialization format for AIR. It provides a convenient way to author, review, and version knowledge while preserving AIR semantics.
Markdown is **not** the AIR model itself.
---
# Design Principles
The Markdown serialization follows these principles:
- Human-readable
- Machine-readable
- Git-friendly
- AI-friendly
- Editor-independent
- Semantic-preserving
Markdown exists to serialize AIR Documents without altering their meaning.
---
# Document Structure
An AIR Markdown document consists of two parts:
```text
YAML Frontmatter
↓
Markdown Body
```
The YAML Frontmatter contains structured metadata.
The Markdown Body contains the human-readable content.
---
# YAML Frontmatter
Every AIR Document should begin with YAML Frontmatter.
Example:
```yaml
---
title: Example
layer: L3
type: assumption
status: draft
tags: []
created:
updated:
author:
version: 1.0
summary:
related: []
source: []
---
```
The metadata defines the semantic properties of the document.
---
# Markdown Body
The document body contains the knowledge associated with the metadata.
Markdown formatting exists only to improve readability.
Examples include:
- headings
- lists
- tables
- blockquotes
- code blocks
These elements do not define AIR semantics.
---
# Headings
Headings organize content for human readers.
Example:
```md
# Overview
## Context
### Observation
```
Heading levels should remain shallow whenever possible.
Deeply nested heading structures should be avoided.
---
# One Concept per Document
Each AIR Document should describe one primary concept.
Large topics should be decomposed into multiple linked documents.
Example:
```text
Reality
↓
Problem
↓
Assumption
```
Rather than:
```text
One document
├── Reality
├── Problem
├── Assumption
├── Validation
```
---
# One Representation per Section
Each section should contain one representation style.
Examples:
- conceptual explanation
- pseudocode
- configuration
- JSON
- YAML
- tables
Avoid mixing multiple representations within the same section.
If multiple representations are required, create separate documents and reference them.
---
# Code Blocks
Fenced code blocks are supported.
Example:

```python
print("AIR")
```

Nested fenced code blocks should be avoided.

If nested examples are necessary, escape the fences or move the example into another document.

⸻

# Tables

Tables may be used to improve readability.

Example:

| Name | Description |
|------|-------------|
| L1 | Reality |

Tables do not carry additional semantic meaning.

⸻

# Lists

Ordered and unordered lists are supported.

Example:

- Reality
- Problem
- Assumption

Lists should remain concise and readable.

⸻

# Blockquotes

Blockquotes may be used for:

* quotations
* design principles
* important notes

Example:

> AIR owns semantics.

⸻

# Wiki Links

AIR supports wiki-style document references.

Example:

[[Reality]]
[[Validation]]
[[Architecture]]

Applications may resolve these references into AIR Document relationships.

Broken references should be reported by validators.

⸻

# External Artifacts

Large structured artifacts should exist as independent files.

Examples:

* YAML
* JSON
* DSL
* Graph definitions
* Configuration files

Documents should reference these artifacts rather than embedding them.

Example:

policy.dsl
execution_graph.yaml
knowledge.json

⸻

# Images and Media

Images may be embedded using standard Markdown syntax.

Example:

![Architecture](architecture.png)

Images are presentation assets.

Semantic information should always exist as text.

Images must never be the only representation of important knowledge.

⸻

# HTML

Raw HTML should be avoided whenever possible.

AIR aims to remain renderer-independent.

If HTML is required for compatibility, it should not alter document semantics.

⸻

# Formatting

Formatting is presentation only.

Examples include:

* bold
* italic
* strikethrough
* inline code
* horizontal rules

Changing formatting must never change AIR meaning.

⸻

# AIR-safe Markdown

An AIR-safe Markdown document should:

* contain valid YAML Frontmatter
* describe one primary concept
* belong to one primary L7 layer
* use one representation style per section
* avoid nested code fences
* use explicit document references
* preserve semantic meaning independently of formatting

⸻

# Validation

Validators should verify:

* valid Markdown
* valid YAML Frontmatter
* readable document structure
* valid document references
* unsupported constructs (optional)

Validation concerns document correctness rather than writing style.

⸻

# Compatibility

AIR Markdown aims to remain compatible with common Markdown tooling, including:

* Obsidian
* GitHub Markdown
* VS Code
* Markdown editors
* Static site generators

Applications may provide additional features without modifying AIR semantics.

⸻

# Summary

Markdown is the primary serialization format for AIR Documents.

Its role is to make AIR Documents easy to write, read, review, and version while preserving the semantic model defined by AIR.

Presentation may evolve.

Semantics must remain stable.