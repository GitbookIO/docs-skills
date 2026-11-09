---
name: prerequisite-gap-checker
description: "Planned: read a task page as a reader with no prior context and list the steps, permissions, accounts, installed tools, and other state the page assumes but never tells the reader to set up. Use when a writer asks whether a tutorial or how-to page is missing prerequisites, or what a new user might trip on. Scaffold only; not ready for use."
---

# Prerequisite gap checker

Find what a task page assumes the reader already has or has already done, so writers can state it or link to it.

## Status

Scaffold only — not ready for use.

## Planned

- Read the page in a subagent that sees only that page, so the model does not fill gaps from its own background knowledge
- List every piece of assumed state before judging the page: accounts, API keys, permissions, installed tools, earlier steps
- Mark each item as stated on the page, linked from the page, or missing
- Report missing items as things a reader might trip on, not as pass or fail, because the check over-flags
