# YAML Metadata Schema Specification

## Purpose

This document defines the YAML metadata schema for AIR Documents.

YAML metadata provides structured, machine-readable information that describes the semantic properties of a document.

The metadata forms part of the AIR Document and contributes to its semantic interpretation.

---

# Design Goals

The YAML schema is designed to be:

- human-readable
- machine-readable
- editor-independent
- extensible
- deterministic

Metadata should describe a document without depending on its visual presentation.

---

# Frontmatter

Every AIR Document should begin with a YAML Frontmatter block.

Example:

```yaml
---
title: Example Document

layer: L3
secondary_layers:
  - L6

type: assumption
status: draft

tags:
  - ai
  - reasoning

created: 2026-06-27
updated: 2026-06-27

author: John Doe
version: 1.0

summary: A short description of the document.

related:
  - Reality
  - Validation

source:
  - https://example.com
---
```

The Frontmatter precedes the Markdown body.

---

# Metadata Fields

The following fields are defined by the AIR Specification.

| Field | Type | Required | Description |
|--------|------|----------|-------------|
| `title` | String | Yes | Human-readable document title. |
| `layer` | Enum | Yes | Primary L7 semantic layer. |
| `secondary_layers` | List | No | Additional semantic classifications. |
| `type` | String | Yes | Document type. |
| `status` | String | Yes | Current lifecycle status. |
| `tags` | List | No | User-defined classification tags. |
| `created` | Date/Datetime | Yes | Creation timestamp. |
| `updated` | Date/Datetime | Yes | Last modification timestamp. |
| `author` | String | No | Document author. |
| `version` | String | Yes | Document version. |
| `summary` | String | No | Short document summary. |
| `related` | List | No | Related AIR Documents. |
| `source` | List | No | External references or evidence. |

---

# Title

The `title` field identifies the document.

Example:

```yaml
title: Reality Observation
```

Titles should be unique within a project whenever practical.

---

# Layer

The `layer` field specifies the document's primary semantic layer.

Example:

```yaml
layer: L1
```

Allowed values are defined in the L7 Specification.

Exactly one primary layer shall exist.

---

# Secondary Layers

The `secondary_layers` field provides optional semantic classifications.

Example:

```yaml
secondary_layers:
  - L6
  - L7
```

Secondary layers provide additional context but never replace the primary layer.

---

# Type

The `type` field identifies the document category.

Example:

```yaml
type: reality
```

Common examples include:

- reality
- problem
- assumption
- variables
- simulation
- validation
- meta

Applications may define additional types.

---

# Status

The `status` field represents the lifecycle state of the document.

Example:

```yaml
status: draft
```

Recommended values include:

- draft
- review
- approved
- archived

Applications may extend this list.

---

# Tags

Tags provide user-defined classification.

Example:

```yaml
tags:
  - ai
  - architecture
```

Tags are organizational metadata and do not affect AIR semantics.

---

# Created

The `created` field records when the document was originally created.

Example:

```yaml
created: 2026-06-27
```

Applications should preserve this value.

---

# Updated

The `updated` field records the latest modification time.

Example:

```yaml
updated: 2026-06-28
```

Applications may update this field automatically.

---

# Author

The `author` field records the document author.

Example:

```yaml
author: Alice
```

This field is informational and does not affect semantics.

---

# Version

The `version` field records the document version.

Example:

```yaml
version: 1.0
```

Version values are application-defined.

---

# Summary

The `summary` field provides a concise description of the document.

Example:

```yaml
summary: Records the observable facts before analysis.
```

Summaries improve discoverability but do not define document semantics.

---

# Related

The `related` field lists related AIR Documents.

Example:

```yaml
related:
  - Problem Statement
  - Validation Report
```

Applications may resolve these values into document references.

---

# Source

The `source` field records external evidence or references.

Example:

```yaml
source:
  - https://example.org
  - observation.csv
```

Sources improve traceability.

---

# Required Fields

The AIR Specification requires the following fields:

```yaml
title:
layer:
type:
status:

created:
updated:

version:
```

Required fields shall exist even if values are temporarily empty during authoring.

---

# Extensibility

Applications may define additional metadata fields.

Example:

```yaml
confidence: 0.82

owner: Planner

priority: High
```

Additional fields must not alter the semantics defined by the AIR Specification.

---

# Validation

Validators should verify:

- valid YAML syntax
- required fields exist
- valid L7 layer
- valid metadata types
- duplicate metadata keys
- invalid field values

Validation rules are defined in the Validation Specification.

---

# Compatibility

The YAML schema is intentionally conservative.

It should remain compatible with common Markdown editors that support YAML Frontmatter, including:

- Obsidian
- VS Code
- GitHub
- Hugo
- Jekyll

Applications may ignore unknown metadata fields while preserving them during serialization.

---

# Summary

The YAML metadata schema provides the structured semantic information required by AIR Documents.

Metadata complements the Markdown body by defining document identity, classification, lifecycle, and relationships in a machine-readable form while remaining simple for humans to author and maintain.