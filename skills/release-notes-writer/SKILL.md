---
name: release-notes-writer
description: "Draft clear, user-facing release notes and changelog entries from merged pull requests, commits, tickets (Linear, Jira, GitHub issues), diffs, or internal notes, grouped by impact and written in the team's existing voice. Use when a writer asks to write release notes, a changelog entry, a what's-new update, or a summary of what shipped between two tags, dates, or versions. Filters out internal-only changes, calls out breaking changes and deprecations with migration steps, links entries to docs, and never invents behavior the sources do not support."
---

# Release notes writer

Release notes tell users what changed in the product, why it matters to them, and what they need to do. Engineering records describe the same changes from the inside: ticket IDs, refactors, branch names, and internal jargon. This skill turns those records into accurate notes a user can scan in under a minute.

Every entry must be traceable to a source. If a change's user impact is unclear from the sources, ask or flag it; do not guess.

## Gather the inputs

Confirm the range first: two tags, two versions, a date range, or a milestone. Then collect every change in that range.

- **Commits:** `git log v1.4.0..v1.5.0 --no-merges --pretty=format:'%h %s'`
- **Merged pull requests:** `gh pr list --state merged --base main --search "merged:2026-10-01..2026-10-30" --json number,title,body,labels,url --limit 200`
- **Pull requests in a release:** `gh release view v1.5.0` or `gh api repos/{owner}/{repo}/compare/v1.4.0...v1.5.0`
- **Tickets:** issues or Linear and Jira tickets linked from PR bodies, or filtered by release, milestone, or cycle.
- **Diffs:** read the diff when a title is vague ("fix bug", "update handler") and the impact is not stated elsewhere.

Read PR descriptions and labels, not only titles. Labels such as `breaking`, `feature`, `bug`, `internal`, or `skip-changelog` often decide where an entry goes.

## Match the existing changelog

Before writing, look for an existing changelog, `CHANGELOG.md`, release page, or past release notes. If one exists, match it over this skill:

- section names and order, heading levels, and date or version format;
- tense and person ("Added" vs. "You can now");
- entry length, use of bold, links, PR numbers, and contributor credits;
- product and feature names exactly as the docs use them.

If there is no existing format, use the template at the end of this skill.

## Filter the changes

Keep a change only if a user can see it, use it, or must react to it. Leave out:

- refactors, tests, CI, build tooling, dependency bumps, and code style changes with no user-visible effect;
- internal admin tools, feature-flagged work that is not yet available, and reverted changes;
- fixes for bugs that never shipped to users.

Keep security fixes, performance changes users will notice, and dependency updates that change supported versions or behavior. Merge several PRs that make up one feature into a single entry. When unsure whether a change is user-facing, list it separately for the user to decide.

## Group by impact

Use these groups, in this order, and omit any that are empty:

| Group | What goes in it |
|-------|-----------------|
| Breaking changes | Anything that requires users to change code, configuration, or workflow. |
| New | Features, endpoints, options, or integrations that did not exist before. |
| Improved | Changes that make existing features faster, clearer, or more capable. |
| Fixed | Bugs users could have hit, described by the symptom they saw. |
| Deprecated | Features that still work but will be removed, with the removal date or version if known. |

Order entries within a group by how many users they affect.

## Write for users

- **Lead with the benefit or outcome.** "You can now export reports as CSV" beats "Added CSV serializer to ReportService."
- **Use plain verbs.** Add, remove, fix, rename, speed up, support. Avoid "leverage", "enhance", "streamline", and "robust".
- **Describe fixes by symptom.** "Fixed search returning no results for queries with accents," not "Fixed Unicode normalization bug."
- **Drop internal jargon.** No ticket IDs, branch names, code names, or class names unless users see them. Keep API names, config keys, and UI labels exactly as written, in code or bold.
- **Be specific.** Give numbers, limits, versions, and plan or platform scope when they apply ("Available on Pro and Enterprise plans").
- **Keep tense consistent** across the whole release. Follow the existing changelog; otherwise use past tense for changes and present tense for what users can now do.
- **One change per entry, one or two sentences each.** No intros, outros, hype, emoji, or "We're excited to announce."
- **Do not overstate.** Do not call something faster, safer, or easier unless the sources say so.

## Breaking changes and migrations

Put breaking changes first and make each one self-contained:

1. What changed and which users are affected.
2. Why, in one sentence, if the sources say.
3. What to do, as concrete steps or a before-and-after code sample.
4. When it takes effect, and how long the old behavior keeps working.

Treat removed options, renamed fields, changed defaults, new required permissions, and dropped platform or version support as breaking even if the PR does not label them that way. Link to a migration guide when one exists; flag when one is needed and missing.

## Link to docs

Link each New, Improved, and Breaking entry to the docs page that explains it, with link text that names the destination. If a feature has no docs page yet, flag it as a docs gap instead of linking to the PR. Link PRs or issues only if the existing changelog does.

## Template

```markdown
## v1.5.0 — 2026-10-30

### Breaking changes

- **`timeout` is now in seconds, not milliseconds.** Update any value you set in `config.yml`, for example `timeout: 30000` becomes `timeout: 30`. See [Configuration reference](link).

### New

- You can now export reports as CSV from **Reports** > **Export**. See [Export reports](link).

### Improved

- Search results load up to 2x faster on large workspaces.

### Fixed

- Fixed search returning no results for queries with accented characters.

### Deprecated

- The `/v1/users` endpoint is deprecated and will be removed in v2.0. Use [`/v2/users`](link) instead.
```

## Deliver the result

Return the release notes ready to paste. After them, list briefly:

- changes you left out as internal, so the user can confirm;
- entries whose user impact you could not confirm from the sources;
- breaking changes missing a migration guide, and features missing docs.
