# Vilix AI MCP

> Persistent memory for ChatGPT, Claude, Cursor, Windsurf, Grok and every other MCP-compatible AI tool, on your phone and your laptop

Vilix AI gives your AI assistants a shared memory across tools and across devices, so you don't have to re-explain your projects, preferences, decisions, and workflow every time you change tools or devices.

**Plan on your phone. Continue on your laptop. Same memory, every time.**

[**Get started →**](https://vilix.ai/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs) &nbsp;·&nbsp;
[Website](https://vilix.ai) &nbsp;·&nbsp;
[Docs](https://vilix.ai/docs)

Questions, support, or partnership inquiries — visit [vilix.ai](https://vilix.ai).

---

## The problem

AI tools forget what you were talking about across chats, platforms, and devices. You sketch out a plan on ChatGPT mobile, then pull up Claude on your laptop for a second opinion, then open up Cursor to actually build it, but every single tool starts from zero. You re-paste the same background, re-explain the same decisions, re-describe the same preferences every time you switch between models, platforms, or devices.

## The solution

Vilix AI is a native Model Context Protocol memory layer for AI assistants and coding agents. It is built directly on the open MCP standard, not a browser extension, not a one-off plugin, not a proprietary bridge. One MCP connection, and any compliant client can read and write to the same memory. You save context once, and it is there everywhere, on any device.

## What makes Vilix AI different

**Phone-to-laptop continuity, not just cross-tool.** Most cross-AI memory tools solve switching between apps, Vilix AI solves switching devices. Start a conversation with Claude on your phone on the train, open up Claude Code on your laptop an hour later, and it already knows exactly where you left off.

**Built natively on MCP, an open standard, not a proprietary integration.** Vilix AI does not maintain a separate plugin per platform, it exposes standard MCP tools, so any current or future MCP-compatible client works automatically, no custom integration required.

**Real conversations, not just extracted facts.** Most memory tools distill your chats down into short bullet-point facts and throw away the rest, Vilix AI keeps the actual conversation history and context itself, retrievable and searchable, not just a lossy summary of it.

**Long-term by design, not a rolling window.** Vilix AI is not built to remember the last few days and quietly forget the rest, it is designed to hold years of accumulated context, so a decision from a year ago is just as retrievable as one from this morning.

**You control it.** Audit, edit, export or erase anything stored, anytime.

## Popular AI tools that support MCP

Vilix AI works with any MCP-compatible client.

**Available on both phone and laptop:**
- Claude by Anthropic
- ChatGPT by OpenAI
- Grok by xAI
- Perplexity

**Coding agents and IDEs, primarily desktop:**
- Cursor
- Codex
- Windsurf
- GitHub Copilot

If a client speaks MCP, Vilix AI works with it, this list will only keep growing.

## Quickstart

You will need a Vilix AI account. Setup takes about five minutes and uses OAuth, no API tokens to copy or store.

1. Create a Vilix AI account
2. Open the setup page
3. Connect your AI client on your phone, your laptop (or both!)
4. Add the Vilix AI MCP server
5. Start using persistent memory — your context now follows you across every tool and every device

### MCP server connection

The Vilix AI MCP server uses a single endpoint across every supported client:

```
https://api.vilix.ai/mcp
```

Authentication is handled through OAuth during the client connection flow, you approve access once, and there's no token to paste or store.

## Example use cases

- **Founder** — keeps startup context, strategy, and decisions consistent across ChatGPT and Claude, on the phone between meetings and on the laptop back at the desk.
- **Developer** — moves product decisions and architecture notes from a mobile chat with Claude right into Cursor on the laptop, so the coding agent already knows the plan.
- **Creator** — keeps brand voice, audience, and content plans available across every AI tool they write with, on any device.
- **AI power user** — stops repeating preferences and project background every time they change models, devices, or open a new chat.

## How the MCP tools work

- **Retrieve relevant context** — before answering, the assistant pulls the actual conversation history and context that matters for what you're working on, not a stripped-down fact list.
- **Save useful memories** — after a meaningful exchange, the assistant persists the real content of what happened, kept for the long term.
- **Continue work across sessions and devices** — the next tool you open, on whatever device, picks up exactly where the last one left off.

## Privacy and control

You control your saved memory. Audit, edit, export, and erase your stored content from the Vilix AI dashboard, anytime. Vilix AI is designed for portable AI context, your memory is yours to move, not locked into a single vendor. Conversations are stored for you, not used to train models.

## What this repository is and is not

This is a public documentation, setup, and distribution repository for Vilix AI MCP. It contains setup guides, example workflows, and community feedback channels. It does not contain the Vilix AI backend, production code, API secrets, database logic or internal infrastructure. The Vilix AI product itself is a hosted service, this repo is the developer-facing front door to it.

---

### About

Vilix AI is an MCP memory server providing persistent memory for AI: ChatGPT memory, Claude memory, Cursor memory, and AI agent memory in one place, built natively on the open MCP standard. It is a shared memory layer for AI assistants and a cross-platform, cross-device AI memory system that keeps real conversations, not just extracted facts, for as long as you need them.

**Ready to stop repeating yourself?**

**Start here: [vilix.ai/get-started](https://vilix.ai/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)**
