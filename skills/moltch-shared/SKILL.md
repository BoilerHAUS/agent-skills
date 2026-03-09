---
name: moltch-shared
description: Shared execution and communication contract for boilermolt + boilerclaw in BoilerHAUS/moltch, optimized for autonomous coordination with minimal human relay.
user-invocable: true
metadata: {"openclaw":{"emoji":"🤝"}}
---

Apply this skill as the default contract for both agents in `BoilerHAUS/moltch`.

## contract metadata
- skill_version: v1.2.0
- last_updated_utc: 2026-03-09T03:06:00Z

## activation boundary
- active for all work in `BoilerHAUS/moltch`
- active for issue-linked workstreams that modify moltch docs/process/implementation artifacts

## source of truth
- repository docs: `https://github.com/BoilerHAUS/moltch/tree/main/docs`
- workflow contract overrides ad-hoc execution unless human explicitly supersedes

## autonomy default + no-relay rule
- agents coordinate directly by default on linked issues/PRs
- do not ask human to relay messages between agents unless tooling/channel is unavailable
- when tooling is unavailable, escalate once with concise context and continue once channel is restored

## single-thread communication default
- keep agent-to-agent coordination in the same issue/PR thread by default for one visible audit trail
- use side-channel/private messaging only for sensitive context
- after side-channel use, post an in-thread non-sensitive summary

## mandatory workflow
1. start with an Issue
2. work in fork branch (`<actor>/issue-<id>-<slug>`)
3. open PR to `BoilerHAUS/moltch:main`
4. include `Closes #<issue>` when fully delivered (`Refs #<issue>` when partial)
5. wait for human approval before merge
6. sync fork after merge

Hard rules:
- no direct pushes to `main`
- respect CODEOWNERS and required checks
- keep PRs narrowly scoped and reversible

## role lanes + cross-review
Primary lanes:
- **boilermolt**: product, governance, commercial, docs
- **boilerclaw**: technical architecture, deploy, repo plumbing

Cross-review:
- both agents review/comment on any PR
- anchor feedback to issue acceptance criteria + source-of-truth docs
- propose edits, avoid unilateral lane takeover

## discussion and implementation modes
- `discussion_only`: planning/architecture/policy; no implementation PR creation
- `implementation_allowed`: direct inter-agent execution is allowed without extra human relay

When mode is ambiguous, default to `discussion_only` and ask human to confirm transition.

## handoff SLA + template
SLA windows:
- active window: first response <= 30 minutes
- low-activity window: first response <= 12 hours

Required handoff block:
- objective
- current state
- exact ask
- expected output / acceptance check
- due window

## escalation threshold
Escalate with `needs-human` when any condition is true:
- SLA breach after 2 unanswered pings in active window
- policy ambiguity blocks safe execution
- blocker unresolved >15 minutes despite attempts

Escalation message MUST include:
- blocker
- attempts
- 2-3 options
- recommendation

## coordination heartbeat
For active execution issues/PRs, post concise in-thread updates:
- done
- next
- blocked

## merge-readiness gate
Before final merge request, verify and record:
- mergeability is clean
- required checks are passing
- issue linkage is correct (`Closes`/`Refs`)
- rollback note exists in PR body

## docs and decision hygiene
- use deterministic language for policy-sensitive sections
- governance/product/operations docs include:
  - `version`
  - `owner_role`
  - `review_cadence`
  - `next_review_due`

## operational KPI
Track weekly:
- `human_relay_touches_per_issue` (target: down week-over-week)

## skill change management
This skill is a living contract; update via Issue + PR only.

Versioning policy:
- **patch**: wording/clarity only
- **minor**: additive process guidance/lane clarifications
- **major**: breaking workflow contract changes

Skill-update PRs must include:
- rationale
- behavior changes
- migration notes for both agents
