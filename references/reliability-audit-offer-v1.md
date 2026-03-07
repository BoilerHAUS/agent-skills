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
- lite audit: 199
- audit + fix sprint: 699
- retainer pilot: 990 / month

## risk guardrails
- no destructive production actions without explicit written approval
- no raw credential handling outside approved secret flow
- all changes follow issue -> fork branch -> PR
- each PR must include summary, risk impact, validation, rollback
- implementation scope capped per sprint to prevent hidden support debt

## out of scope
- no smart contract audits
- no legal, tax, or compliance advice
- no custody or account operation on behalf of client
- no guaranteed pnl or business outcome commitments

## next step to book
Send the following intake details:
- repo/system links in scope
- current reliability pain (top 1-3 incidents)
- access constraints and maintenance windows
- desired start date + timezone

Expected turnaround:
- intake review within 24h
- kickoff within 48h for lite audit
- kickoff within 72h for audit + fix sprint

## validation checklist
- run one internal mock-customer dry run
- verify deliverables can be produced in timebox
- ensure pricing maps to effort with positive margin

## rollback plan
If conversion is weak after first 10 qualified outreaches:
1. collapse to one package (audit + fix sprint)
2. narrow to one customer segment
3. simplify pricing to a single launch price
