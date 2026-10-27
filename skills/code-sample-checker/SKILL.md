---
name: code-sample-checker
description: "Planned: verify that code samples in documentation are syntactically valid, use current APIs and package versions, are consistent across languages, and run where possible. Use when a writer asks to test, validate, or update code snippets, examples, or quickstarts in docs. Scaffold only; not ready for use."
---

# Code sample checker

Find and check every code sample in a docs set so that copied examples work for readers and agents.

## Status

Scaffold only — not ready for use.

## Planned

- Extract fenced code blocks with their language tags and surrounding context
- Lint or parse each sample for its language and flag missing language tags
- Flag deprecated APIs, outdated package versions, and placeholder values that are not explained
- Run safe, self-contained samples in a sandbox when the user allows it
- Check that equivalent samples in different languages do the same thing
