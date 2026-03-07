# outreach playbook v1 (boilerhaus)

## objective
Secure first paid pilot with zero-budget outreach for the reliability audit + implementation offer.

## target customer profiles (top 2)

### segment A — indie founder / solo builder
- owns a revenue-generating product
- reports recurring automation, uptime, or deployment pain
- can decide quickly on small fixed-fee services

### segment B — lean ops/engineering lead (small team)
- responsible for reliability and incident response
- has visible recurring operational friction
- values fast fixes over long consulting cycles

## qualification filter
A prospect is qualified if at least 3 are true:
- public signal of reliability pain in last 60 days
- active code/product operations
- clear owner/accountability visible
- likely budget for $199-$699 quick engagement
- open to async collaboration and scoped delivery

## distribution channels + cadence

### channels
- github issues/discussions where reliability pain is explicit
- direct outreach on x/linkedin/email (where contact is public)
- partner referrals from known operator circles

### cadence (first 7 days)
- day 1-2: source and qualify 20 prospects
- day 2-3: send 10 variant A + 10 variant B
- day 4-5: follow-up to non-responders (+48h)
- day 6-7: book discovery calls and run qualification

### minimum personalization rule
Before sending any message, include at least one specific reference to the prospect’s context:
- a concrete pain signal they posted
- a repo/system artifact they own
- a recent incident or reliability complaint

## outreach message variants

### variant A (short)
"hey {name} — saw your note on {pain signal}. we run a fixed-scope reliability audit + fix sprint for teams with recurring ops friction. want me to send the 3-point plan for your stack?"

### variant B (long)
"hi {name}, noticed {specific incident/pain}. we help small teams reduce repeat reliability issues with a fixed-scope workflow: quick audit, prioritized fixes, and rollback-safe PR delivery. want me to send a concrete 72h plan tailored to your repo/process?"

## first 20-prospect tracker format
Use `references/first-20-prospect-tracker.csv` for execution.

Required fields:
- date
- segment
- prospect_name
- profile_or_url
- source_channel
- pain_signal
- message_variant
- status
- response_timestamp
- outcome_reason
- next_action_date
- estimated_deal_usd
- notes

Status enum (use only these values):
- queued
- sent
- followup_sent
- replied
- call_booked
- won
- lost

## follow-up loop + conversion logging
1. send initial outreach (A/B split)
2. if no response in 48h, send one concise follow-up
3. if response is positive, move to discovery-call-booked
4. log outcome by variant and segment
5. after first 10 responses, tighten copy to best-performing variant

## success criteria (issue #4)
- 20 qualified outreaches sent
- >=3 discovery conversations booked
- >=1 paid pilot opportunity identified

## risk + rollback
Risk: message-market mismatch and low response.

Rollback after first 10 low-signal outreaches:
1. narrow to one segment
2. use single best-performing message angle
3. simplify CTA to one offer + one next step
