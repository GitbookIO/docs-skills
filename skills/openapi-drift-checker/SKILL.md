---
name: openapi-drift-checker
description: "Planned: compare documentation pages against an OpenAPI specification and report drift such as missing or renamed endpoints, parameters, fields, enums, defaults, status codes, auth requirements, and stale examples. Use when a writer asks to check docs against an API spec, find API doc inconsistencies, or verify API docs after a spec change. Scaffold only; not ready for use."
---

# OpenAPI drift checker

Treat the OpenAPI spec as the source of truth for API surface and find where prose guides, tutorials, and reference pages disagree with it.

## Status

Scaffold only — not ready for use.

## Planned

- Load an OpenAPI 3.x or Swagger 2.0 spec from a file or URL
- Extract operations, parameters, schemas, enums, defaults, and auth schemes
- Find endpoint, parameter, and field mentions in Markdown docs and code samples
- Report drift by severity: removed or renamed items, wrong types or values, undocumented new items
- Propose doc edits and flag cases where the spec itself may be wrong
