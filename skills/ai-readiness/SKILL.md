---
name: ai-readiness
description: "Check or fix documentation pages for AI readability, so AI assistants, Ask AI, RAG pipelines, and other LLM retrieval systems can retrieve, chunk, and quote them accurately. Use when a writer asks whether docs are AI-ready or LLM-ready, how pages will chunk for retrieval, or to audit or fix pages for AI assistants. Runs checks A-1 to A-10 (description, opening paragraph, headings, empty sections, section length, tables, values in images, leading pronouns, link text, SUMMARY.md listing) and reports a pass or fail per page with the offending line."
---

# AI readability check

AI assistants answer questions from documentation by retrieving chunks of a page, not the whole page. A page is AI-readable when every chunk can stand on its own, the page says what it is about in the first lines, and the facts an agent needs are stated as plain, quotable sentences.

## Checks

Run each check against every page you are given. Report a pass or a fail with the line that fails.

| ID | Check | Why it matters |
|----|-------|----------------|
| A-1 | Frontmatter has a description of 50 to 160 characters that states what the page covers. | Retrieval systems index the description first. "Mock page for..." or an empty description fails. |
| A-2 | The first paragraph after the title answers "what is this and who is it for" in two sentences or fewer. | The opening chunk is the one most often retrieved. |
| A-3 | Every heading is specific enough to be understood out of context. "Overview" or "Details" fails; "Availability profile settings" passes. | Headings become chunk titles. |
| A-4 | No heading is immediately followed by another heading. | Empty sections produce empty chunks. |
| A-5 | Each section is between roughly 40 and 300 words. | Shorter sections lose context; longer ones split mid-thought. |
| A-6 | Tables have a header row and no empty cells; a cell that would be empty says "None". | Agents read tables row by row and drop rows with gaps. |
| A-7 | Technical values (field names, paths, limits, defaults) appear in prose or tables as literal text, not only in images. | Images are invisible to most retrieval. |
| A-8 | Pronouns at the start of a paragraph ("It", "This", "They") are replaced with the noun they refer to. | A chunk that starts with "This" has no subject once cut from its neighbor. |
| A-9 | Link text names the destination. "See below" or "here" fails. | Agents cannot follow "below." |
| A-10 | Every page is listed in `SUMMARY.md` and has no `hidden: true` unless it is deliberately hidden. | Unlisted pages are not indexed by the published site. |

> **Note:** A-10 applies to GitBook and other sites whose navigation is defined in `SUMMARY.md`. If the docs have no `SUMMARY.md`, mark A-10 as N/A.

## How to report

Produce one table per page with the ID, pass or fail, and the offending line for each fail. Then list the fixes in order of impact: A-1 and A-2 first, then A-3 and A-8, then the rest. If asked to fix, apply only the failing items and leave passing text alone.

Do not rewrite voice. Do not add marketing language. Do not invent facts to fill a description; derive it from the page body.
