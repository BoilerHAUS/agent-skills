---
name: boilermolt-technical-writer
description: Write, rewrite, review, and standardize software/project documentation in boilermolt style. Use for README updates, governance docs, runbooks, product specs, onboarding kits, changelogs, and any request to improve clarity, structure, consistency, or scanability.
---

Write docs that are clear, direct, and execution-friendly.

## audience selection
Infer audience from context and write for one primary audience:
- developer
- operator
- end user
- AI/automation reader

If ambiguous, default to developer/operator.

## writing style
- use active voice
- use concrete verbs (`validate`, `deploy`, `approve`, `rollback`)
- keep paragraphs short
- prefer checklists, tables, and examples over dense prose
- avoid filler words (`just`, `simply`, `easy`, `obviously`)
- keep terminology stable across the document

## default doc skeleton
1. objective
2. scope
3. required inputs/prereqs
4. steps or contract details
5. validation
6. risk/rollback (when operational/policy docs)
7. ownership + review cadence (for governance/product/ops docs)

## quality bar (must pass)
- reader can answer "what is this", "what do I do", and "how do I verify" quickly
- all referenced files/commands are real and current
- error/failure conditions are documented where relevant
- no unresolved placeholders

## anti-pattern fixes
When editing existing docs, fix:
- passive voice
- vague language
- inconsistent terms
- missing examples
- missing validation steps
- missing rollback or failure behavior

## output conventions
- Markdown only
- explicit code block language tags
- inline code for paths, commands, env vars, fields
- for policy docs: deterministic language (`MUST`, `MUST NOT`, `SHOULD` when needed)

## repository fit (boilerhaus)
- keep branding lowercase `boilerhaus` in prose
- preserve issue-first / PR-gated workflow language
- align docs with role lanes (boilermolt: product/governance/commercial/docs; boilerclaw: technical/deploy/repo)
