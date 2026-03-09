# User Guide & Tutorial Template

Use this template for task-oriented documentation: how-to guides, tutorials, walkthroughs,
and conceptual explainers. Distinguish between:

- **Tutorial** — learning-oriented, hand-holds the reader through a complete example
- **How-to guide** — task-oriented, assumes competence, gets to the point fast
- **Conceptual guide** — understanding-oriented, explains why and how something works

Match the format to the intent.

---

## Tutorial Template

Tutorials have a beginning, middle, and end. The reader should accomplish something real by the end.

```markdown
# Tutorial: [What You'll Build or Accomplish]

In this tutorial, you'll [specific outcome]. By the end, you'll have [concrete artifact or capability].

**Time:** ~15 minutes  
**Prerequisites:** [List specific knowledge or setup required. Link to setup docs.]

## What you'll build

Brief description and optionally a screenshot or diagram of the end result.

## Step 1: [Verb phrase describing the action]

Explain what this step accomplishes before showing commands. One sentence is enough.

```bash
command --flag value
```

Expected output:

```
Output the user should see if this worked
```

If something might go wrong here, call it out:

> **Note:** If you see `Error: X`, make sure you've done Y first.

## Step 2: [Next action]

...

## Step N: [Final action]

...

## What you built

Summarize what was accomplished. Optionally show the complete working code or config.

## Next steps

- Link to related how-to guides
- Link to API reference for deeper customization
- Link to advanced topics
```

---

## How-To Guide Template

Get to the point. No hand-holding. Each guide answers one specific question.

```markdown
# How to [Specific Task]

[One sentence on what this guide covers and any important prerequisites.]

## [First action or section]

```bash
command
```

## [Second action]

...

## Troubleshooting

| Problem | Cause | Fix |
|---------|-------|-----|
| Error message verbatim | Root cause | Step to resolve |
```

---

## Conceptual Guide Template

```markdown
# [Concept Name]

One-paragraph plain-language explanation of what this is and why it matters.

## How it works

Explain the mechanism. Use diagrams or code snippets where they clarify. Avoid analogies
that require more explanation than the concept itself.

## Key terms

| Term | Definition |
|------|------------|
| `term` | Precise definition in context of this system |

## When to use it

Describe the use cases where this concept applies, and where it doesn't.

## Related concepts

- Link to related doc
- Link to related doc
```

---

## Style Notes for Guides and Tutorials

- **Number your steps.** Unnumbered steps feel optional. Steps are not optional.
- **Show expected output.** After every command, show what success looks like.
- **One action per step.** If a step requires two commands, consider splitting it.
- **Call out destructive actions.** Use a `> **Warning:**` block for anything irreversible.
- **End every tutorial with a "next steps" section.** Give the reader somewhere to go.
- **Avoid "we".** Write "you" and "the system", not "we". The reader is doing this alone.
- **For AI agents:** Structure steps as numbered lists with explicit input/output pairs.
  Prose walkthrough is secondary; the machine-readable action sequence is primary.
