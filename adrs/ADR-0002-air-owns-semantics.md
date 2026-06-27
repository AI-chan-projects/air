# **ADR-0002: AIR Owns Semantics**

**Status**

Accepted

## **Context**

Formatting should never influence reasoning.

Presentation and semantics must remain independent.

## **Decision**

AIR semantics are defined by:

- metadata
- document structure

Markdown formatting is presentation only.

## **Consequences**

AIR remains renderer-independent.

Multiple serializers may exist in the future.