---
name: checkdisc
description: Check and optionally reply to a GitHub Discussion in BoilerHAUS/.github. Use when user says /checkdisc with a discussion number, URL, or shorthand like -4. Fetch the discussion, summarize recent context, and draft or post a reply.
user-invocable: true
metadata: {"openclaw":{"emoji":"💬","requires":{"bins":["gh"]}}}
---

When invoked, treat command input as a discussion target.

Accepted input forms:
- `4`
- `-4`
- `#4`
- full URL like `https://github.com/orgs/BoilerHAUS/discussions/4`
- no input (default to latest updated discussion in `BoilerHAUS/.github`)

Workflow:
1. Resolve a discussion number from input.
2. Fetch discussion details and recent comments from `BoilerHAUS/.github`.
3. Provide a short summary.
4. If user asks to respond, post a concise reply aligned with current org rules:
   - issue-first + PR-gated workflow
   - lowercase `boilerhaus` branding in copy
   - use `needs-human` when blocked >15 minutes

Preferred commands:
- Read discussion:
  - `gh api graphql -f query='query { repository(owner:"BoilerHAUS", name:".github") { discussion(number:N) { id number title url body comments(first:20) { nodes { author { login } bodyText publishedAt url } } } } }'`
- Reply to discussion:
  - use GraphQL `addDiscussionComment` with discussion id

Reply style:
- Be direct and short.
- If posting publicly, avoid exposing internal-only details.
