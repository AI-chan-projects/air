# **ADR-0001: Adopt Markdown as the Primary AIR Serialization**

**Status**

Accepted

## **Context**

AIR requires a human-readable document format that integrates well with version control and existing tooling.

The format should:

- be plain text
- support long-form documentation
- be Git-friendly
- allow metadata
- remain independent of proprietary software

## **Decision**

Markdown with YAML frontmatter is adopted as the primary serialization format for AIR Documents.

## **Consequences**

Positive

- Human-readable
- Git-friendly
- Large ecosystem
- Easy AI parsing
- Editor independent

Negative

- Markdown lacks semantic meaning by itself.
- Additional validation is required.