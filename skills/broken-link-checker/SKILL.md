---
name: broken-link-checker
description: "Planned: find broken, redirected, and fragile links in a documentation repo or published docs site, including relative links, heading anchors, images, and external URLs, and propose fixes. Use when a writer asks to check links, find 404s, fix dead links, or audit links before a release or migration. Scaffold only; not ready for use."
---

# Broken link checker

Check every link in a docs set, internal and external, and explain how to fix each failure without changing link intent.

## Status

Scaffold only — not ready for use.

## Planned

- Resolve relative Markdown links and heading anchors against the repo
- Check external URLs with polite rate limits and report 4xx, 5xx, timeouts, and redirect chains
- Flag links that point at unstable targets, such as editor or preview URLs
- Suggest the most likely correct target for each broken link
- Output a report grouped by page and severity
