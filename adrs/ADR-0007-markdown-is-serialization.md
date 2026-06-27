# **ADR-0007: Markdown is a Serialization, Not the Model**

**Status**

Accepted

## **Context**

Future AIR implementations may require JSON, databases, APIs, or binary formats.

The semantic model should not depend on Markdown.

## **Decision**

Markdown is one serialization format of AIR Documents.

The AIR model remains independent of storage format.

## **Consequences**

Future serializers may include:

- JSON
- XML
- SQLite
- Graph database
- REST API

without changing AIR semantics.