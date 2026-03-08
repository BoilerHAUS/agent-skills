# pilot metrics schema v1 (boilerhaus)

## purpose
Provide a canonical metrics schema and reporting cadence for pilot acquisition execution.

## owner model
- metric owner: person responsible for daily updates
- reviewer: person responsible for weekly conversion review

## canonical metric definitions
- `outreaches_sent`: number of first-touch messages sent that day
- `replies`: count unique prospects who replied that day (multiple messages from the same prospect in one day count as 1)
- `positive_replies`: unique replying prospects with clear interest/next-step intent
- `discovery_calls_booked`: calls booked from outreach
- `pilots_offered`: explicit pilot offer proposals sent
- `pilots_closed_paid`: paid pilot agreements confirmed
- `revenue_usd`: total USD value of paid pilots closed

## derived KPI definitions (weekly scoreboard)
- `reply_rate_pct` = `replies / outreaches_sent * 100`
- `positive_reply_rate_pct` = `positive_replies / outreaches_sent * 100`
- `call_book_rate_pct` = `discovery_calls_booked / outreaches_sent * 100`
- `pilot_close_rate_pct` = `pilots_closed_paid / pilots_offered * 100` (0 if `pilots_offered` is 0)

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
### timezone + reporting cutover
- Use UTC as the canonical timezone.
- Daily reporting window is `00:00-23:59 UTC`.
- Post one daily update after cutoff to avoid mixed-day counts.

### daily update
Post in discussion #5 with:
- date (UTC)
- outreaches_sent
- replies / positive_replies
- discovery_calls_booked
- pilots_offered / pilots_closed_paid
- revenue_usd
- top blocker (if any)
- discussion_update_url
- tracker_snapshot_ref

### weekly review
- summarize totals and conversion rates
- identify winning segment + message variant
- decide one copy iteration and one targeting iteration for next cycle

## week-1 baseline targets
- outreaches_sent: 20
- positive_replies: >=3
- discovery_calls_booked: >=1
- paid pilot path identified: >=1

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
