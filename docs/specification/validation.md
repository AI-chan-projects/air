# AIR Validation Specification

## Purpose

This document defines the validation rules for AIR Documents.

Validation ensures that AIR Documents conform to the AIR Specification while preserving semantic consistency.

The purpose of validation is to detect errors, omissions, and inconsistencies without modifying the document itself.

---

# Objectives

Validation should ensure that AIR Documents are:

- syntactically valid
- structurally complete
- semantically consistent
- internally coherent
- safely interpretable by applications

Validation is deterministic and independent of any AI model.

---

# Validation Model

Validation operates on AIR Documents after parsing.

```text
Markdown

↓

Parser

↓

AIR Document

↓

Validator

↓

Validation Report
```

The validator does not parse Markdown directly.

It validates the structured AIR Document produced by the parser.

---

# Validation Categories

Validation is divided into four categories.

| Category | Purpose |
|----------|---------|
| Syntax | Verify document syntax. |
| Structure | Verify document structure. |
| Semantics | Verify AIR semantics. |
| References | Verify document relationships. |

---

# Syntax Validation

The validator should verify:

- valid UTF-8 encoding
- readable file
- valid YAML Frontmatter
- valid Markdown
- parsable document

Failure in syntax validation prevents further processing.

---

# Metadata Validation

The validator shall verify required metadata fields.

Example:

```yaml
title:
layer:
type:
status:
created:
updated:
version:
```

Required fields shall exist even if their values are empty.

Applications may define additional required fields.

---

# Layer Validation

Every AIR Document shall define exactly one primary semantic layer.

Example:

```yaml
layer: L3
```

The validator shall verify:

- layer exists
- layer is valid
- exactly one primary layer

If `secondary_layers` exists, every entry shall be a valid L7 layer.

Duplicate layers should be reported.

---

# Document Type Validation

The validator shall verify that the document type is valid.

Example:

```yaml
type: assumption
```

Applications may extend supported document types.

---

# Structural Validation

The validator should verify:

- one YAML Frontmatter block
- readable document body
- one primary concept per document (where detectable)
- supported Markdown constructs
- valid heading hierarchy (optional)

Structure validation focuses on document organization rather than writing style.

---

# Reference Validation

AIR Documents may reference other documents.

Example:

```text
[[Reality]]

[[Validation]]
```

The validator should detect:

- broken references
- self references
- duplicate references
- malformed references

Reference validation may require access to the project.

---

# Metadata Consistency

The validator should verify consistency between metadata fields.

Examples include:

- duplicated titles
- duplicated identifiers
- invalid status values
- incompatible metadata combinations

Project-specific rules may extend this validation.

---

# Serialization Validation

The validator should ensure that serialization preserves AIR semantics.

Changing formatting must never alter:

- metadata
- semantic layer
- document relationships
- document meaning

---

# Validation Report

Validation produces diagnostics rather than modifying documents.

Each diagnostic should contain:

- severity
- location
- message
- validation rule

Example:

```text
ERROR

Missing required metadata field:

layer
```

Example:

```text
WARNING

Broken document reference:

[[Variables]]
```

---

# Severity Levels

AIR defines three validation levels.

| Level | Meaning |
|--------|---------|
| Error | The document does not conform to the AIR Specification. |
| Warning | The document is valid but may contain problems. |
| Info | Informational recommendation. |

Applications may introduce additional diagnostic categories.

---

# Extensibility

Applications may implement custom validation rules.

Examples include:

- project conventions
- organization policies
- naming conventions
- required metadata
- domain-specific constraints

Custom validation must not redefine AIR semantics.

---

# Validation Principles

Validation follows these principles.

## Deterministic

The same AIR Document should always produce the same validation result.

---

## Non-destructive

Validation never modifies documents.

Correction belongs to editors or applications.

---

## Specification-driven

Validation verifies compliance with the AIR Specification.

It does not evaluate the quality of ideas or reasoning.

---

## Implementation-independent

Validation rules remain consistent regardless of:

- editor
- parser implementation
- storage format
- operating system

---

# Conformance

An implementation conforms to this specification if it:

- validates AIR Documents according to the defined rules
- preserves AIR semantics
- produces deterministic validation results

Implementations may extend validation while remaining compatible with this specification.

---

# Future Extensions

Future versions of AIR validation may support:

- schema evolution
- semantic consistency checks
- ontology validation
- graph integrity validation
- cross-project validation
- confidence scoring

These extensions should complement, not replace, the core validation model.

---

# Summary

Validation ensures that AIR Documents remain structurally correct, semantically consistent, and interoperable across implementations.

Its purpose is to verify conformance with the AIR Specification while preserving the independence of semantics from presentation and implementation.