# Example: Founder Keeps Startup Context Across Tools

This is an illustrative workflow, not a recorded founder or customer session.
Use a demo account with fictional company information, connect both clients to
that account, and add the [memory instructions](../docs/mcp-config.md#memory-instructions).
Check the actual save and retrieval results rather than assuming the calls ran.

This shows how a founder keeps strategy and decisions consistent across ChatGPT
and Claude, getting multiple model perspectives without losing the thread.

## Scenario

You are a founder. You use ChatGPT for fast drafting and Claude for a second
opinion. You want both to know your company, your strategy, and your latest
decisions — without a recap every time.

## Step 1 — Brief once in ChatGPT

> "Company: Vilix — persistent AI memory via MCP. GTM right now: developer
> distribution through a public GitHub repo and a ChatGPT onboarding funnel.
> Remember this as my current strategy."

## Step 2 — Get a second opinion in Claude

In a fresh Claude session (connected to Vilix):

> "Given my current GTM strategy, what are the biggest risks and what would you
> prioritize this month?"

Claude already knows the company and the GTM plan from Vilix. You get a genuine
second perspective on the *same* context — not a re-briefed, lossy summary.

## Step 3 — Decisions accumulate

> "Decision: prioritize the GitHub repo first, the ChatGPT funnel second.
> Remember that."

Whichever tool you open next continues from this decision.

## Why this matters

- Strategy stays consistent across models and sessions.
- You can deliberately compare model viewpoints on identical context.
- Decisions compound into a durable memory instead of scattered chat history.

See also: [sample-memory-workflow.md](sample-memory-workflow.md)

**Try it:** [vilix.ai/get-started](https://vilix.ai/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
