# AI-writing tells in documentation

A longer catalogue for the `humanizer` skill. Each entry lists the pattern, examples, why it hurts docs, and a fix. Treat these as signals: a single instance is rarely a problem, and a house style guide always takes precedence.

## Vocabulary

### Promotional and inflated words

Examples: seamless, seamlessly, robust, powerful, cutting-edge, state-of-the-art, best-in-class, blazing-fast, effortless, game-changer, revolutionary, comprehensive, holistic, leverage, utilize, delve, empower, unlock, unleash, elevate, supercharge, streamline, harness, foster, navigate (figurative), landscape, realm, journey, ecosystem (when not literal), tapestry, testament.

Why it hurts: these words assert value without information. Readers skim past them, and they make docs sound like marketing.

Fix: replace with the plain verb ("use", "help", "let you") or the concrete fact ("responds in under 50 ms"). Often the word can be deleted.

### Significance inflation

Examples: "plays a crucial role in", "is a pivotal step", "serves as a cornerstone", "it's essential to understand that", "stands as a testament to".

Fix: say what the thing does. "The token authenticates each request."

### Intensifiers and filler adverbs

Examples: truly, really, incredibly, simply, easily, just, basically, actually, essentially.

Why it hurts: "simply" and "easily" also alienate readers who find the step hard.

Fix: delete.

## Openings and closings

### Ceremonial intros

Examples: "In this guide, we will explore...", "Welcome to the X documentation!", "Let's dive in.", "Whether you're a beginner or an expert...", "In today's fast-paced world...".

Fix: open with what the page lets the reader do or know. "Use API keys to authenticate requests to the REST API."

### Recap conclusions

Examples: "In conclusion,", "In summary,", "To wrap up,", "By following these steps, you have successfully...", "Now you're ready to...".

Fix: delete, or replace with a concrete next step and link.

### Sign-offs and chat residue

Examples: "Happy coding!", "I hope this helps!", "Let me know if you have questions.", "Certainly! Here is the updated page:", "As of my last update...", "Great question!".

Fix: delete.

## Sentence patterns

### Negative parallelism

Examples: "It's not just a tool, it's a platform.", "Not only does it X, but it also Y.", "This isn't about X. It's about Y."

Fix: state the positive claim directly.

### Rule-of-three padding

Examples: "fast, reliable, and secure"; "plan, build, and ship"; three adjectives where one carries the meaning.

Fix: keep only the items with substance. Two items or four are fine when that is what is true.

### Hedging stacks

Examples: "may potentially", "could possibly", "can generally help to", "it's worth noting that", "it's important to remember that", "in some cases, it might".

Fix: if the behavior is conditional, state the condition. "Requests fail if the token has expired." Otherwise commit to the claim.

### Vague attribution

Examples: "Many developers prefer...", "Industry experts recommend...", "It is widely regarded as...", "Studies show...".

Fix: cite the specific source or remove the claim.

### False ranges and empty contrasts

Examples: "from small startups to large enterprises", "from simple scripts to complex pipelines".

Fix: state who or what is actually supported.

### Uniform rhythm

Every sentence is 15 to 20 words with the same subject-verb-object shape, and every paragraph has three sentences.

Fix: vary length by meaning. Use short sentences for actions and facts.

## Formatting

### Em dash overuse

Several em dashes per paragraph, used for asides, lists, and emphasis.

Fix: use commas, colons, parentheses, or two sentences. Keep an occasional em dash if the house style allows it.

### Bold overuse

Bold on key phrases in every paragraph, or bold lead-ins on every bullet ("**Speed:** It's fast.").

Fix: bold UI labels (if the style guide says so) and genuine warnings only.

### Emoji

Emoji in headings, bullets, or callouts (🚀 ✅ 💡 🎉).

Fix: remove unless the house style uses them.

### Heading inflation

A heading for every one or two sentences; title case headings full of promotional words.

Fix: merge thin sections; write descriptive headings that name the task or concept.

### Over-bulleted prose

Explanations or trade-offs broken into fragment bullets that lose the connections between ideas.

Fix: write connected sentences. Keep lists for parallel items, options, and steps.

## Release notes and changelogs

- "We're excited to announce..." and "We've been working hard to..." → state the change.
- "Various bug fixes and improvements" → list the user-visible fixes, or omit.
- "This powerful new feature empowers you to..." → "You can now..."

## READMEs

- Badges and emoji walls before the one-line description of what the project does.
- "Features" lists of adjectives instead of capabilities.
- "Contributions are welcome! 🙌" with no contribution steps → link to CONTRIBUTING or give the steps.

## Source

Adapted for technical documentation from Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).
