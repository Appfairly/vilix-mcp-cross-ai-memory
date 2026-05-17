# Vilix MCP

> Persistent memory for ChatGPT, Claude, Cursor, Windsurf, and MCP-compatible AI tools.

Vilix gives your AI assistants shared memory across tools, so you do not have to
re-explain your projects, preferences, decisions, and workflow every session.

**Start in ChatGPT. Continue in Claude. Finish in Cursor. Without repeating yourself.**

[**Get started →**](https://getvilix.com/get-started) &nbsp;·&nbsp;
[Website](https://getvilix.com) &nbsp;·&nbsp;
[Docs](https://getvilix.com/docs) &nbsp;·&nbsp;
[Privacy](https://getvilix.com/privacy)

---

## The problem

AI tools forget context across chats and platforms.

You start a plan in ChatGPT, move to Claude for a second opinion, then implement
in Cursor — but each tool starts from zero. You re-paste the same background,
re-explain the same decisions, and re-describe the same preferences every time
you switch models or open a new chat.

## The solution

**Vilix is an MCP-native persistent memory layer for AI assistants and coding agents.**

You save context once, and reuse it everywhere. Vilix gives your AI tools a
shared memory layer through the [Model Context Protocol (MCP)](https://modelcontextprotocol.io),
so relevant project history, decisions, and preferences travel with you across
ChatGPT, Claude, Cursor, Windsurf, Perplexity, and other MCP-compatible clients.

This is **cross-platform AI memory**: one persistent memory for AI, instead of a
separate, broken version of you inside every tool.

## Features

- **Shared memory across MCP-compatible clients** — one memory layer, every tool
- **Save and retrieve user and project context** — decisions, preferences, and history
- **Works with AI assistants and coding agents** — from chat to code, same context
- **OAuth-based setup** — connect with a sign-in approval, no manual token wrangling
- **User-controlled memory** — you can audit, edit, export, and erase what is stored
- **Built for founders, developers, creators, and AI power users**

## Supported tools

| Tool | Status | Setup guide |
|------|--------|-------------|
| ChatGPT | Supported | [docs/chatgpt.md](docs/chatgpt.md) |
| Claude | Supported | [docs/claude.md](docs/claude.md) |
| Cursor | Supported | [docs/cursor.md](docs/cursor.md) |
| Windsurf | Supported | [docs/windsurf.md](docs/windsurf.md) |
| Perplexity | Supported | [docs/mcp-config.md](docs/mcp-config.md) |
| Other MCP-compatible clients | Supported | [docs/mcp-config.md](docs/mcp-config.md) |

> Support reflects the MCP-compatible clients Vilix is designed to work with.
> "Supported" does not imply an official partnership unless stated by that vendor.

## Quickstart

You will need a Vilix account. Setup takes about five minutes and uses OAuth —
no API tokens to copy or store.

1. **Create a Vilix account** — sign up at <https://getvilix.com/get-started>
2. **Open the setup page** — follow the in-product steps at <https://getvilix.com/get-started>
3. **Connect your AI client** — pick your tool (ChatGPT, Claude, Cursor, Windsurf, Perplexity)
4. **Add the Vilix MCP server** — use the connection details below
5. **Start using persistent memory** — your context now follows you across tools

### MCP server connection

The Vilix MCP server uses a single endpoint across every supported client
(this URL is published on the [get started page](https://getvilix.com/get-started)):

```
https://api.getvilix.com/mcp/sse
```

Authentication is handled through OAuth during the client connection flow — you
approve access once, and there is no token to paste or store. See
[docs/mcp-config.md](docs/mcp-config.md) for client-specific configuration, and
the per-tool guides in [`docs/`](docs/).

**Links**

- Website: <https://getvilix.com>
- Get started: <https://getvilix.com/get-started>
- Docs: <https://getvilix.com/docs>

## Example use cases

- **Founder** — keeps startup context, strategy, and decisions consistent across
  ChatGPT and Claude without recapping each session.
  ([examples/founder-workflow.md](examples/founder-workflow.md))
- **Developer** — moves product decisions and architecture notes from Claude into
  Cursor so the coding agent already knows the plan.
  ([examples/coding-agent-workflow.md](examples/coding-agent-workflow.md))
- **Creator** — keeps brand voice, audience, and content plans available across
  every AI tool they write with.
- **AI power user** — stops repeating preferences and project background every
  time they switch models or open a new chat.
  ([examples/sample-memory-workflow.md](examples/sample-memory-workflow.md))

## How the MCP tools work

At a high level, Vilix exposes a small MCP tool surface that your AI client calls
automatically once connected:

- **Retrieve relevant context** — before answering, the assistant pulls the
  context that matters for what you are working on.
- **Save useful memories** — after a meaningful exchange, the assistant persists
  what is worth remembering.
- **Continue work across sessions** — the next tool you open picks up where the
  last one left off.

The full developer-facing reference (transport, tool surface, OAuth, and best
practices) lives in the official docs: <https://getvilix.com/docs>. Internal
implementation details are intentionally not part of this repository.

## Privacy and control

- **You control your saved memory.** You can audit, edit, export, and erase your
  stored content from the Vilix dashboard.
- **Vilix is designed for portable AI context** — your memory is yours to move,
  not locked into a single vendor.
- Conversations are stored for you, not used to train models.

Read the full policy: <https://getvilix.com/privacy> · See also
[docs/privacy-and-control.md](docs/privacy-and-control.md).

## What this repository is (and is not)

This is a **public documentation, setup, and distribution repository** for Vilix
MCP. It contains setup guides, example workflows, and community feedback
channels.

It does **not** contain the Vilix backend, production code, API secrets,
database logic, or internal infrastructure. The Vilix product itself is a hosted
service — this repo is the developer-facing front door to it.

---

### About

Vilix is an **MCP memory server** providing **persistent memory for AI**:
**ChatGPT memory**, **Claude memory**, **Cursor memory**, and **AI agent
memory** in one place. It is a **shared memory layer for AI assistants** and a
**cross-platform AI memory** system for anyone who works across multiple AI
tools.

**Ready to stop repeating yourself?**

**Start here: <https://getvilix.com/get-started>**
