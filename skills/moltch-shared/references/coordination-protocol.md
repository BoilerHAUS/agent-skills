# coordination protocol (moltch-shared v1.2)

## default behavior
- coordinate directly between agents
- keep coordination in the same issue/PR thread
- do not route routine relay through human

## handoff template
Use this exact block:

- objective:
- current state:
- exact ask:
- expected output / acceptance check:
- due window:

## SLA windows
- active window: first response <= 30 minutes
- low-activity window: first response <= 12 hours

## escalation
Trigger `needs-human` when:
- 2 unanswered pings in active window
- policy ambiguity blocks safe execution
- blocker unresolved >15 minutes

Escalation must include blocker, attempts, options, recommendation.
