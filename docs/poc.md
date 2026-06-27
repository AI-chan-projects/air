# **AIR Proof of Concept (PoC)**

## **Purpose**

This document defines the scope of the first Proof of Concept (PoC) for AIR (APOS Intermediate Representation).

The objective is **not** to build APOS.

The objective is to validate that structured Markdown documents can be interpreted as AIR while preserving semantic meaning.

---

# **Goals**

The PoC should demonstrate that:

- Markdown documents can represent AIR safely.
- YAML metadata can provide semantic information.
- L7 semantic layers can classify documents.
- AIR documents can be parsed into a structured representation.
- AI agents can understand AIR without relying on document formatting.

---

# **Scope**

Included

- Markdown parser
- YAML frontmatter parser
- L7 semantic layers
- Wiki link parser (`[[Document]]`)
- AIR document model
- Basic validation
- Document browser/editor

Excluded

- Planner
- Memory
- Multi-agent execution
- Workflow engine
- Cloud synchronization
- Policy engine

---

# **Core Concepts**

## **AIR Document**

An AIR document consists of:

```
YAML Metadata

↓

Markdown Content

↓

Semantic Layer

↓

Links
```

Each document represents a single primary concept.

---

## **Semantic Layer**

Every AIR document shall belong to one primary L7 layer.

```
L1 Reality

L2 Problem

L3 Assumption

L4 Variables

L5 Simulation

L6 Validation

L7 Meta
```

Optional secondary layers may also exist.

---

## **Source of Truth**

AIR semantics are determined by

- YAML metadata
- document structure

Markdown formatting is presentation only.

Formatting must never alter AIR meaning.

---

# **Architecture**

```
Markdown File

↓

Parser

↓

AIR Document

↓

Validator

↓

Editor / Viewer
```

---

# **AIR Document Model**

```
AIRDocument

├── metadata

├── content

├── links

├── layer

├── secondary_layers

├── references
```

---

# **Validation Rules**

The validator should verify:

- YAML exists
- required metadata exists
- valid L7 layer
- valid document type
- valid markdown
- broken links
- duplicated document title

---

# **Editor Features**

Minimum editor functionality:

- open project folder
- browse documents
- edit markdown
- edit YAML
- preview markdown
- save document

Optional

- graph view
- semantic layer filter
- validation panel

---

# **Directory Structure**

```
project/

    documents/

        L1/

        L2/

        ...

    assets/

    templates/

    .air/
```

---

# **Future Extensions**

Not included in PoC:

- AIR AST
- AIR DSL
- AIR Query Language
- AI-assisted editing
- Knowledge graph
- Cloud sync
- APOS integration

---

# **Success Criteria**

The PoC is considered successful if:

- Markdown documents can be parsed into AIR objects.
- Metadata is interpreted correctly.
- L7 classification works.
- Documents can reference each other.
- Validation detects malformed documents.
- The editor can create, modify, and save AIR documents.

---

# **Design Philosophy**

AIR is a semantic representation.

Markdown is one possible serialization.

The PoC exists to validate the AIR model before integrating it into APOS.