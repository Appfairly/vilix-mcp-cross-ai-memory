# Example: Decide in Claude, Build in Cursor

This shows how a developer moves product decisions from a planning tool into a
coding agent — without re-briefing it.

## Scenario

You are a developer. You plan architecture with Claude and implement with
Cursor. Normally you copy-paste the plan into Cursor every time. With Vilix, you
do not.

## Step 1 — Make decisions in Claude

In Claude (connected to Vilix):

> "For the Lumen API, we decided: Postgres over SQLite, REST not GraphQL, and
> auth via short-lived JWT with refresh tokens. Remember these decisions."

Vilix persists the architectural decisions.

## Step 2 — Implement in Cursor

Open Cursor (connected to Vilix) in your project:

> "Scaffold the auth module according to the architecture decisions we made for
> Lumen."

Cursor's AI retrieves the decisions from Vilix — Postgres, REST, short-lived
JWT with refresh — and scaffolds consistently with the plan, instead of
inventing its own approach or asking you to re-explain.

## Step 3 — Decisions evolve, memory follows

Later, back in Claude:

> "We're switching refresh tokens to rotating refresh tokens. Update that
> decision."

Next time Cursor works on auth, the updated decision is already there.

## Why this matters

- The coding agent acts on **your** decisions, not guesses.
- No drift between "what we planned" and "what got built."
- One memory spans planning and implementation tools.

Setup: [../docs/claude.md](../docs/claude.md) ·
[../docs/cursor.md](../docs/cursor.md)

**Try it:** <https://getvilix.com/get-started>
