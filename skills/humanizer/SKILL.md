---
name: humanizer
description: "Review or rewrite documentation and docs-adjacent copy (guides, reference pages, release notes, changelogs, READMEs) so it reads like a skilled human technical writer wrote it, without changing meaning, facts, terminology, code, links, or UI labels. Use when a writer asks to humanize, de-AI, polish, tighten, or edit AI-drafted docs, or asks why a page sounds AI-generated, robotic, or generic. Detects AI-writing tells such as promotional vocabulary, filler intros and conclusions, rule-of-three padding, 'not just X but Y', hedging, excess em dashes, bold, emoji, and bullets, and either reports ranked findings or returns a clean rewrite with a short change summary."
---

# Humanizer

Make documentation read like a skilled technical writer wrote it for a specific reader with a specific task. AI-drafted prose tends toward the safest, most generic choice: inflated vocabulary, ceremonial intros and outros, padded lists, and decoration applied by habit. Readers learn to skim past it, and it hides the facts they came for.

Humanizing is editing, not disguising. The goal is clearer, more direct, more trustworthy docs. It is not to evade AI detectors, and it never trades accuracy for style.

## Ground rules

These rules override every stylistic suggestion in this skill.

- **Preserve meaning and facts.** Keep every claim, number, limit, default, version, plan, role, condition, warning, and exception. Do not strengthen or weaken a claim. If a sentence needs a fact that is missing, flag it; do not invent one.
- **Do not touch literal content.** Leave code blocks, inline code, commands, API names, field names, file paths, URLs and link targets, UI labels, error messages, frontmatter values, and quoted text exactly as written. You may change link text only when it does not name its destination.
- **Keep the team's terminology.** Use product names, feature names, and glossary terms exactly as the docs use them. Do not swap in synonyms for variety.
- **Defer to the house style guide.** When the user supplies a style guide, glossary, or nearby pages, follow them over this skill. If the style guide allows something this skill flags (for example, em dashes or a "Summary" section), keep it.
- **Keep legitimate structure.** Numbered steps, reference tables, parameter lists, admonitions, and headings that aid navigation are not tells. Remove structure only when it fragments prose that reads better as sentences.
- **Respect scope.** Edit only the files, pages, or passages the user asked about.

## Target voice

Unless the house style says otherwise:

- Lead with the answer, outcome, or action. Put background after it.
- Use active voice and second person ("you"). Use imperative mood for steps ("Select **Save**").
- Prefer plain, specific words: "use" over "leverage", "lets you" over "empowers you to", "fast" or a number over "blazing-fast".
- State things once, at the confidence the evidence supports.
- Vary sentence length naturally. Short sentences for actions and facts; longer ones for relationships and conditions.

## AI-writing tells

Check for these patterns. They are signals, not proof, and a single instance is rarely a problem. Fix the ones that cost the reader time or trust. See [TELLS.md](TELLS.md) for a longer catalogue with examples.

| Tell | What it looks like | Typical fix |
|------|-------------------|-------------|
| Promotional vocabulary | seamless, robust, powerful, leverage, delve, empower, unlock, elevate, streamline, cutting-edge, game-changer | Replace with the plain word or the concrete fact, or delete. |
| Ceremonial intro | "In this guide, we will explore...", "Welcome to...", "Let's dive in" | Start with what the page lets the reader do. |
| Recap conclusion | "In conclusion...", "In summary...", "By following these steps, you have..." | Delete, or replace with a real next step. |
| Rule-of-three padding | "fast, reliable, and scalable"; triplets where only one item has substance | Keep the items that carry information. |
| Negative parallelism | "It's not just X, it's Y", "not only... but also" | State Y directly. |
| Em dash overuse | Several em dashes per paragraph used as all-purpose punctuation | Use commas, colons, parentheses, or separate sentences. |
| Decoration overuse | Bold on every other phrase, emoji in headings or bullets, a heading for every two sentences | Bold only UI labels and critical warnings; remove emoji; merge thin sections. |
| Hedging stacks | "may potentially", "can generally help to", "it's important to note that" | Commit to the supported claim, or state the actual condition. |
| Vague attribution | "Many users find...", "Experts agree...", "It is widely considered..." | Name the source, or drop the claim. |
| Chatty or sycophantic tone | "Great question!", "Happy documenting!", "You've got this", "I hope this helps" | Delete. |
| Uniform rhythm | Every sentence the same length and shape; every paragraph three sentences | Vary length; combine or split sentences by meaning. |
| Over-bulleted prose | Reasoning or explanation chopped into fragments, bullets with bold lead-ins that repeat the heading | Write connected sentences; keep lists for parallel items and steps. |
| Significance inflation | "plays a crucial role", "a pivotal step", "stands as a testament to" | Say what it does. |
| Chat residue | "Certainly! Here's...", "As an AI...", "Let me know if you'd like..." | Delete. |

## Workflow

1. **Read the context.** Identify the content type (concept, procedure, reference, troubleshooting, release note, README), the reader, and any style guide or glossary. Read nearby pages if available to learn the house voice.
2. **Pick the mode.** If the user asks to review, check, audit, or explain, use review mode. If they ask to humanize, rewrite, fix, polish, or edit, use rewrite mode. If unclear, review first and offer to apply.
3. **Find the tells.** Mark every instance, then rank by impact: tells that hide or distort facts first, then tells that waste the reader's time, then cosmetic ones.
4. **Edit or report** using the output format for the mode.
5. **Run the self-check** before returning anything.

## Review mode

Return ranked findings, most impactful first. For each finding give:

- **Passage:** the exact text, quoted, with its location (file and heading or line).
- **Tell:** the pattern name from the table.
- **Why it matters:** one sentence on the cost to the reader (hides the answer, adds no information, undermines trust, breaks scanning).
- **Suggested rewrite:** the replacement text, preserving every fact.

Group repeated instances of the same tell into one finding with a count and two or three examples. Do not modify files in review mode.

## Rewrite mode

Return or apply the clean final content, then a brief change summary (three to six bullets) listing the main kinds of changes and anything you could not fix without more information, such as a vague claim that needs a source. Do not annotate the rewritten text itself.

## Example

**Before**

> ## 🚀 Unlocking the Power of Webhooks
>
> In this guide, we will delve into how webhooks can seamlessly empower your team to streamline workflows. Webhooks aren't just notifications — they're a robust, scalable, and flexible way to stay in sync. It's important to note that webhooks may potentially fail if your endpoint is unavailable.
>
> In conclusion, webhooks are a game-changer for your integrations. Happy building! 🎉

**After**

> ## Receive events with webhooks
>
> Webhooks notify your systems when events happen, so they stay in sync. If your endpoint is unavailable, delivery fails.

What changed: the heading names the task and loses the emoji; the intro now says what webhooks do; promotional words, the "not just" construction, the triplet, and the hedge stack are gone; the failure condition is stated directly; the recap and sign-off are removed. No facts were added or removed. (If the docs define retry behavior, the rewrite should link to it rather than guess.)

## Self-check

Before returning, confirm:

1. Every fact, number, condition, warning, and exception from the original is still present and no new claim was added.
2. Code, commands, links, UI labels, field names, and frontmatter are unchanged.
3. Product terminology matches the original and the glossary.
4. The house style guide wins wherever it conflicts with this skill.
5. Steps, tables, and navigation headings that help the reader are intact.
6. The first sentence of each section gives the answer or action.
7. No new tells were introduced, such as replacing em dashes with a different all-purpose punctuation habit.
8. The text reads naturally aloud.

## Reference

The tells above draw on Wikipedia's editor guide [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), adapted for technical documentation.
