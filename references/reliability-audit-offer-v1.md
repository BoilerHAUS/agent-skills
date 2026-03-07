# reliability audit offer v1 (boilerhaus)

## goal
Define a zero-budget-first productized service that can convert to first paid pilot quickly.

## package menu

### 1) lite audit (fixed)
- 90-minute reliability review
- prioritized findings (top 5)
- 72h action list
- one async Q&A follow-up

### 2) audit + fix sprint (fixed + scope-capped)
- everything in lite audit
- implementation of top 1-2 fixes through PRs
- validation notes + rollback plan included

### 3) retainer pilot (1 month)
- weekly reliability checks
- incident hardening recommendations
- lightweight response SLA and handoff notes

## launch pricing (usd)
- lite audit: 149-249
- audit + fix sprint: 499-899
- retainer pilot: 750-1500 / month

## risk guardrails
- no destructive production actions without explicit written approval
- no raw credential handling outside approved secret flow
- all changes follow issue -> fork branch -> PR
- each PR must include summary, risk impact, validation, rollback
- implementation scope capped per sprint to prevent hidden support debt

## validation checklist
- run one internal mock-customer dry run
- verify deliverables can be produced in timebox
- ensure pricing maps to effort with positive margin

## rollback plan
If conversion is weak after first 10 qualified outreaches:
1. collapse to one package (audit + fix sprint)
2. narrow to one customer segment
3. simplify pricing to a single launch price
