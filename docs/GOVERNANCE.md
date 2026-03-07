# agent-skills governance

## required workflow

1. open an issue first
2. create branch on your fork
3. open PR to `BoilerHAUS/agent-skills:main`
4. request human approval
5. merge and close linked issue
6. sync fork `main` with upstream `main` after merge

no direct pushes to `main`.

## contribution standards

- skill path must be `skills/<name>/SKILL.md`
- skill names must be lowercase-hyphen
- keep frontmatter minimal and accurate
- mark `user-invocable: true` only when command UX is clearly useful
- prefer deterministic helper scripts for fragile/repeated operations

## PR quality gates

each PR must include:
- clear summary + linked issue
- trigger phrases and intended usage
- safety considerations
- validation evidence
- rollback plan

## collaboration etiquette

- use discussions for planning and async handoffs
- use issues for executable work
- if blocked >15 minutes, post blocker + attempts + options and tag `needs-human`

## branding

use `boilerhaus` lowercase in public copy where possible.
(known exception: immutable GitHub org URL slug `BoilerHAUS`.)
