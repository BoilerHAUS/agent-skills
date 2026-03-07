# pilot metrics schema v1 (boilerhaus)

## purpose
Provide a canonical metrics schema and reporting cadence for pilot acquisition execution.

## owner model
- metric owner: person responsible for daily updates
- reviewer: person responsible for weekly conversion review

## canonical metric definitions
- `outreaches_sent`: number of first-touch messages sent that day
- `replies`: number of prospects who replied (any direction)
- `positive_replies`: replies with clear interest/next-step intent
- `discovery_calls_booked`: calls booked from outreach
- `pilots_offered`: explicit pilot offer proposals sent
- `pilots_closed_paid`: paid pilot agreements confirmed
- `revenue_usd`: total USD value of paid pilots closed

## optional supporting metrics
- `followups_sent`
- `no_response_count`
- `lost_count`
- `average_first_response_hours`

## status enum for outreach records
Use only:
- `queued`
- `sent`
- `followup_sent`
- `replied`
- `call_booked`
- `won`
- `lost`

## outcome_reason enum (suggested)
- `no_response`
- `not_a_priority`
- `no_budget`
- `bad_timing`
- `mismatch_scope`
- `converted_paid_pilot`

## reporting cadence
### daily update
Post in discussion #5 with:
- date
- outreaches_sent
- replies / positive_replies
- discovery_calls_booked
- pilots_offered / pilots_closed_paid
- revenue_usd
- top blocker (if any)

### weekly review
- summarize totals and conversion rates
- identify winning segment + message variant
- decide one copy iteration and one targeting iteration for next cycle

## blocker escalation format (>15m)
Use this exact structure with `needs-human`:
1. blocker
2. what was tried
3. options (2-3)
4. recommended option

## data hygiene rules
- update tracker rows before posting daily summary
- do not mix currencies in `revenue_usd`
- avoid free-text status values (use enum only)
- include timestamps for meaningful transitions when possible
