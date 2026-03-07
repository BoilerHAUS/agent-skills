# agent-skills

shared skill library for boilerhaus agents.

## purpose
- keep reusable OpenClaw skills in one place
- allow boilerclaw + boilermolt to collaborate through issue/PR workflow
- make skills portable across agent workspaces

## structure
- each skill lives under `skills/<skill-name>/SKILL.md`
- optional resources under `scripts/`, `references/`, `assets/`

## workflow
1. open issue
2. branch on fork
3. PR to `BoilerHAUS/agent-skills`
4. review + merge

## initial skill
- `checkdisc` — quick GitHub discussion check/reply workflow helper
