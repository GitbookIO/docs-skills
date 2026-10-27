---
name: seo-aeo-documentation
description: Create, edit, or review product and technical documentation for content-level search engine optimization (SEO) and answer engine optimization (AEO) while preserving human readability, factual accuracy, and house style. Use when a docs task mentions SEO, AEO, search intent, answer engines, AI search or citations, LLM discoverability, or retrieval. Exclude technical SEO, crawl controls, schema, analytics, and marketing copy unless explicitly requested.
---

# SEO and AEO documentation

Make documentation easier for people to find in search and for answer engines to retrieve, interpret, and cite accurately. Content-level SEO and AEO rely on many of the same qualities: clear intent, descriptive titles and headings, direct answers, consistent terminology, useful links, and accurate information.

Improve the documentation itself rather than writing for a presumed algorithm. Optimization can improve discoverability and answerability; it cannot guarantee indexing, rankings, inclusion, traffic, or citations.

## Follow the source of truth

Before writing or editing:

- Read the relevant project instructions, style guide, terminology list, templates, and nearby documentation when available.
- Treat the user's requirements and supplied house style as authoritative. Preserve established voice, terminology, formatting, and content types unless the user asks to change them.
- Use product specifications, source code, existing canonical docs, or other supplied authoritative material for factual claims. Do not invent behavior, limits, examples, prerequisites, or availability.
- If authoritative sources conflict or omit a fact needed for an accurate answer, flag the issue instead of guessing.
- When a style guide uses numbered rule IDs, apply and cite its existing IDs during review. Do not create, reuse, or renumber IDs unless the user asks to update that guide.

## Establish the search and answer intent

Identify, from the request and available context:

- the audience and task;
- the primary question, topic, or task the page should address;
- the canonical product and feature terminology;
- relevant scope, such as plan, version, role, platform, environment, or configuration;
- the source that supports each material claim.

Use real search, support, or product-question data when the user supplies it. Do not invent demand, query volume, or user language. Otherwise, infer the answers above when the evidence is clear. Ask only when a missing answer would materially change the content.

## Edit for discoverability and answerability

Apply the following principles proportionally. Do not force every page into the same pattern.

### Lead with the useful answer

When a section answers a question, explains a concept, or resolves a task, give the answer or outcome before extended background. Include a necessary qualification in the opening answer when omitting it would make the answer misleading.

Do not add throat-clearing introductions, promotional framing, or generic summaries before the useful information.

### Use specific information architecture

- Give each page one primary intent and each section one coherent topic or task.
- Give each page a specific, descriptive title that identifies its primary topic, question, or task and distinguishes it from related pages. Avoid generic titles such as “Overview,” “Introduction,” or “Configuration” when they do not identify what the page covers.
- Use descriptive headings that identify the question, concept, action, or object covered.
- Keep a logical heading hierarchy. Use H2 headings for main sections and H3 headings for their subsections. Do not skip levels or choose a level merely for visual styling.
- Split content when independent answers are buried together. Keep tightly related information together when separating it would remove needed context.
- Do not turn every heading into a question. Use the clearest natural phrasing for the content.
- When a page description is part of the requested work, make it an accurate, factual summary of the page's primary intent. Do not promise information the page does not provide.

### Make passages clear with minimal surrounding context

- Name the subject instead of relying heavily on vague pronouns or phrases such as “this,” “it,” “the above,” or “as mentioned earlier.”
- Define an unfamiliar or product-specific term close to its first use.
- State relationships explicitly: what an action affects, creates, changes, requires, preserves, or does not affect.
- Introduce a common user term once alongside the official term when it improves matching or comprehension, such as “single sign-on (SSO).” Continue with the official term consistently.
- Give enough context for an important section to remain accurate when retrieved alone, but do not repeat information merely to make every paragraph fully standalone.

### Keep scope and qualifications attached

- State prerequisites, exceptions, limitations, and conditions explicitly and close to the claim or step they qualify.
- State when behavior varies by plan, version, role, platform, environment, region, or configuration.
- Avoid broad claims followed by a material exception much later on the page.
- Keep safety, security, data-loss, and compatibility warnings with the relevant action.

### Choose structures that preserve meaning

- Use numbered lists for sequences, bullets for related items, and tables for consistent comparisons or attributes.
- Introduce lists, tables, code blocks, examples, and callouts so their purpose is clear.
- Give tables descriptive column headings. Avoid rows or values whose meaning depends entirely on preceding prose.
- Put examples close to the concept they demonstrate. For code, identify the language and explain important inputs, outputs, placeholders, and constraints.
- Do not force prose into a list, table, FAQ, or rigid template when another form is clearer.
- Do not make an image, video, or screenshot the only source for an instruction, label, or constraint; include the essential information in text.

### Preserve canonical answers

- Prefer one authoritative explanation of a fact. Link to it with descriptive link text from related pages instead of maintaining conflicting copies.
- Link required prerequisites, concepts, procedures, and reference material to their canonical pages at the point they become relevant. Do not add repeated or loosely related links solely for optimization.
- Include the minimum information needed to understand or complete the current task before linking elsewhere; do not use a link as a substitute for the answer.
- Check nearby or linked documentation for contradictions introduced by the edit. When several pages answer substantially the same question, suggest consolidating them or clarifying their audience, scope, or purpose. Change other pages only when the user authorized that scope.
- Flag content that appears stale, internally inconsistent, or unsupported.

### Adapt to the documentation type

- For a concept, open with a concise definition, then explain purpose, relationships, and important limits.
- For a procedure, state the outcome and prerequisites, give ordered actions, and include a clear success check when useful.
- For reference content, specify types, accepted values, defaults, constraints, side effects, and version or plan scope where applicable.
- For troubleshooting, connect the observable symptom to likely causes, corrective actions, and a way to verify the fix.

## Run the SEO and AEO review

Before finishing, test every material answer:

1. **Intent test:** Does the page clearly satisfy one primary user question, topic, or task?
2. **Answer test:** Does the relevant section provide the answer or outcome early enough?
3. **Title and heading test:** Do the page title and headings identify the exact content they introduce and distinguish it from related content?
4. **Passage test:** If only this section were retrieved, would it remain accurate with minimal additional context?
5. **Qualification test:** Would the answer still be retrieved with any condition or exception that materially changes it?
6. **Scope test:** Is the applicable plan, version, role, platform, environment, region, or configuration clear?
7. **Terminology test:** Are official terms defined and used consistently, with useful reader language introduced naturally?
8. **Structure test:** Are steps, tables, lists, code, and examples labeled and understandable without hidden context?
9. **Canonical content test:** Does the edit create duplication, contradiction, an unsupported claim, or a missed link to required context?
10. **Human test:** Is the result clearer and more useful to a person, not merely more repetitive or machine-like?

Fix issues within the authorized scope. Report unresolved accuracy or source questions.

## Avoid SEO and AEO folklore

Do not:

- stuff keywords or repeat synonyms unnaturally;
- add an FAQ, question heading, summary, glossary, table, or arbitrary section-length limit by default;
- rewrite clear prose into fragments solely to make it look “extractable”;
- force exact-match search phrases into titles, headings, or prose when natural language would be clearer;
- make unsupported claims about what a particular search engine, model, crawler, or answer engine prefers;
- sacrifice nuance, accuracy, accessibility, or the house style for presumed search or AI visibility;
- promise that an edit will produce indexing, rankings, citations, or traffic;
- change structured data, canonical URLs, redirects, robots directives, sitemaps, `llms.txt`, publishing settings, performance configuration, or analytics unless the user requests site-level work.

## Deliver the result

- When asked to write or edit, provide or apply the clean final content. Summarize only the material SEO and AEO decisions and unresolved questions.
- When asked to review, prioritize findings by impact. Point to the affected passage, explain the discoverability or answerability risk, and propose a concrete fix.
- Distinguish factual or house-style violations from judgment-based suggestions. Cite existing style-guide rule IDs when they apply.
- Preserve the user's requested format and avoid an unnecessary SEO or AEO score unless the user asks for one.
