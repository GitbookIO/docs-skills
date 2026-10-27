---
name: docs-freshness-audit
description: "Planned: find stale documentation by comparing pages against changelogs, release notes, version numbers, and last-updated history, and flag content that references removed, renamed, or outdated features. Use when a writer asks which docs are out of date, what needs updating after a release, or for a content freshness or maintenance audit. Scaffold only; not ready for use."
---

# Docs freshness audit

Prioritize documentation maintenance by finding pages most likely to be wrong after product changes.

## Status

Scaffold only — not ready for use.

## Planned

- Read changelogs, release notes, or merged PR titles for a given range
- Match changed features to pages that mention them
- Flag outdated version numbers, screenshots, UI labels, and deprecated features
- Rank pages by staleness risk using last-updated history and traffic when available
- Output a prioritized update list with the evidence for each item
