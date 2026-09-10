# Vilix AI MCP

**Shared memory for AI assistants and coding agents.** Keep project context,
preferences, decisions, and saved conversations available when you switch tools
or devices.

Vilix AI is a hosted memory service built on the **Model Context Protocol
(MCP)**, the standard that lets an AI client call external tools. Connect each
supported client to the same Vilix account, then have it retrieve context before
answering and save the exchange before returning its reply.

[Get started](https://vilix.ai/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
· [Website](https://vilix.ai)
· [Dashboard](https://app.vilix.ai/)
· [Documentation](https://vilix.ai/docs)

## The problem Vilix solves

You plan a project in Claude, implement it in a coding agent, and ask ChatGPT
for another perspective. Each tool needs the same background. Vilix provides
shared memory that connected tools can retrieve instead of making you paste
that background again.

**Plan on your phone. Continue on your laptop.** Both clients must be connected
to your Vilix account and able to call its memory tools. Client plans, mobile
support, organization policies, and tool approvals can differ.

## Connect your tool

| Client | Setup guide | Connection |
| --- | --- | --- |
| Claude Code | [Claude Code setup](docs/claude.md#claude-code) | Streamable HTTP + OAuth |
| Cursor | [Editor and CLI setup](docs/cursor.md) | Streamable HTTP + OAuth |
| Codex | [Desktop, CLI, and IDE setup](docs/codex.md) | Streamable HTTP + OAuth or API key |
| ChatGPT | [Web developer-mode setup](docs/chatgpt.md) | Streamable HTTP + OAuth; eligible paid account |
| Claude | [Web, desktop, and mobile setup](docs/claude.md) | Remote connector + OAuth |
| Windsurf / Cascade | [Legacy Cascade setup](docs/windsurf.md) | Streamable HTTP + OAuth |
| Other clients | [Connection and authentication reference](docs/mcp-config.md) | Requires compatible remote MCP and authentication support |

For additional client guides, including OpenClaw and Hermes, use the
[current setup selector](https://vilix.ai/get-started). These are connection
guides, not claims of endorsement by the client vendors.

### Connection details

```text
https://api.vilix.ai/mcp
```

- **Transport:** Streamable HTTP. Use the full URL above; do not append `/sse`.
- **Authentication:** OAuth for clients with a browser sign-in flow. Vilix also
  offers revocable API keys for clients that support bearer headers. Follow
  your client's guide; authentication configuration is not interchangeable.
- **Account:** Sign in to the same Vilix account in each client. See
  [current plans](https://vilix.ai/pricing) for product limits.

You do not need to clone or run this repository to connect. Vilix hosts the MCP
server. Existing chats in another provider are not automatically imported by
adding a connector; memory must first be saved to Vilix or imported through an
available product workflow.

## Make memory part of each exchange

The core memory workflow uses two tools:

1. `get_context(user_prompt=...)` retrieves relevant saved context before the
   assistant composes its answer.
2. `save_turn(user_message=..., assistant_message=..., source=..., chat_id=...)`
   saves the finalized exchange before the assistant returns that same answer.

Reuse the returned `chat_id` within the same conversation. Vilix also exposes
other tools for search and managing context; the connected client's tool list
is the current reference.

Add the [memory instructions](docs/mcp-config.md#memory-instructions) to your
client's custom or project instructions, and allow the relevant tool calls.
Connecting a server alone does not guarantee the client calls it on every turn.

## Try a cross-tool workflow

- [Save a fictional project in one tool and recall it in another](examples/sample-memory-workflow.md)
- [Plan in Claude and implement in Cursor](examples/coding-agent-workflow.md)
- [Keep a founder's project decisions available across tools](examples/founder-workflow.md)

These examples are illustrative. Verify the actual `get_context` and
`save_turn` results in your client instead of relying on an assistant saying
“I remember.”

## Privacy and control

Use the dashboard to inspect and manage your saved context. Vilix's
[Privacy Policy](https://vilix.ai/privacy) describes retention, export,
deletion, and data handling; saved conversations are not used by Vilix to train
foundation models. Connected AI clients have their own data policies.

See [privacy and control](docs/privacy-and-control.md) and the
[security overview](https://vilix.ai/security). Keep API keys, personal
conversations, and account details out of public issues and pull requests.

## About this repository

This is the public **documentation and examples** repository for Vilix AI,
operated by Appfairly LLC. The hosted product, backend, database logic, and
production infrastructure are not included or open source. The
[license](LICENSE) applies to this repository's documentation and examples.

[Contributing](CONTRIBUTING.md) · [Security policy](SECURITY.md)
· [Changelog](CHANGELOG.md)

Setup help: [support@vilix.ai](mailto:support@vilix.ai).
