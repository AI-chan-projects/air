# **ADR-0008: AI Consumes AIR Objects**

**Status**

Accepted

## **Context**

LLMs and APOS agents should not directly interpret Markdown formatting.

## **Decision**

Markdown is parsed into AIR Objects before being consumed by AI components.

## **Consequences**

The parser becomes the single source of semantic interpretation.

AI components operate on structured AIR data instead of raw Markdown.