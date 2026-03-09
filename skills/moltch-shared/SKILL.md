---
name: moltch-shared
description: Shared operating contract for boilermolt and boilerclaw while working in BoilerHAUS/moltch. Use for issue triage, planning, execution handoffs, PR review behavior, conflict resolution, and skill-governance updates.
user-invocable: true
metadata: {"openclaw":{"emoji":"🤝"}}
---

Apply this skill as the default execution contract for both agents in `BoilerHAUS/moltch`.

## contract metadata
- skill_version: v1.1.0
- last_updated_utc: 2026-03-09T02:40:00Z

## activation boundary
- active for all work in `BoilerHAUS/moltch`
- active for issue-linked workstreams that modify `moltch` docs/process/implementation artifacts

## source of truth
- Repository docs: `https://github.com/BoilerHAUS/moltch/tree/main/docs`
- Project workflow contract is authoritative over ad-hoc chat instructions unless the human explicitly overrides.

## mandatory workflow
1. Start with an Issue.
2. Work in fork branch (`<actor>/issue-<id>-<slug>`).
3. Open PR to `BoilerHAUS/moltch:main`.
4. Include `Closes #<issue>` when scope is fully delivered (or `Refs #<issue>` when partial).
5. Wait for human approval before merge.
6. Sync fork after merge.

Hard rules:
- no direct pushes to `main`
- respect CODEOWNERS and required checks
- keep PRs narrowly scoped and reversible

## role lanes + cross-review
Primary lane ownership:
- **boilermolt**: product, governance, commercial, docs
- **boilerclaw**: technical architecture, deploy, repo plumbing

Cross-review policy:
- both agents are expected to review and can comment on any PR
- review comments should anchor to issue acceptance criteria and docs source-of-truth
- avoid lane ownership conflicts by proposing edits, not unilateral scope takeover

## blocker and escalation protocol
If blocked for >15 minutes, post a comment with:
- blocker
- attempts made
- 2-3 options
- recommendation
- `needs-human` tag

## conflict resolution protocol
When agents disagree:
1. default to issue acceptance criteria
2. then default to current `moltch/docs` source-of-truth
3. if ambiguity remains, post `needs-human` and pause implementation
4. include final decision link in PR body for audit traceability

## discussion and implementation modes
- `discussion_only`: planning/architecture/policy discussion; no implementation PR is opened yet
- `implementation_allowed`: execution is approved; issue-linked PR creation is allowed

When mode is ambiguous, default to `discussion_only` and ask human to confirm transition.

## PR quality bar
Every PR should include:
- Summary
- Risk impact
- Validation
- Rollback
- linked issue status (`Closes` or `Refs`)

## merge-readiness gate
Before requesting final merge, verify and record:
- mergeability is clean (no conflicts)
- required checks are passing
- issue linkage is correct (`Closes`/`Refs`)
- rollback note is present in PR body

## docs and decision hygiene
- prefer deterministic language (MUST/SHOULD/MAY when policy-sensitive)
- include metadata in governance/product/operations docs:
  - `version`
  - `owner_role`
  - `review_cadence`
  - `next_review_due`
- run docs checks when docs are touched

## skill change management
This skill is a living contract and must be updated through Issue + PR.

Versioning policy:
- **patch**: wording/clarity only
- **minor**: additive process guidance or lane clarifications
- **major**: breaking workflow contract changes

For skill updates, include:
- rationale
- behavior changes
- migration notes for both agents
