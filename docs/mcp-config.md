# Vilix AI MCP connection and authentication

Documentation checked against current client references on **September 10,
2026**. This is configuration guidance; it is not a claim that every client,
account, or mobile app has been tested.

## Connection details

| Field | Value |
| --- | --- |
| Server URL | `https://api.vilix.ai/mcp` |
| Transport | Streamable HTTP |
| OAuth | Sign in to Vilix AI and approve access in the client's browser flow |
| API key | For clients supporting custom bearer headers; manage keys in [Agents](https://app.vilix.ai/agents) |

Use the full `/mcp` URL. Vilix AI is a hosted server, not a local stdio process,
and its current configuration does not use a separate `/mcp/sse` endpoint.
Streamable HTTP may stream responses using SSE; that does not make it the
older separate SSE transport.

## Choose authentication for your client

**OAuth:** Add the server URL, select OAuth if asked, then complete the browser
sign-in and consent flow. The client manages its OAuth credentials. If sign-in
expires, use the client's Authenticate or login action again.

**API key:** Create a key in the Vilix AI dashboard's Agents page when your client
requires or supports static credentials. Send it as an HTTP header:

```http
Authorization: Bearer YOUR_VILIX_API_KEY
```

Use a client-supported secret or environment-variable setting where available.
Do not put a key in the server URL, a public repository, a screenshot, or a
chat transcript. Headers can still be exposed by local configuration, shell
history, or debug logging, so treat the key like a password. Revoke and replace
an exposed key in the dashboard.

ChatGPT's web guide uses OAuth; do not select “No Authentication” or put a Vilix AI
API key into OAuth Client ID/Client Secret fields. Client configuration keys
also differ: Cursor uses `url`, Cascade supports `serverUrl`, and Codex uses a
TOML server table. Use an exact guide instead of pasting a generic JSON block.

## Client guides

- [Claude and Claude Code](claude.md)
- [Cursor editor and CLI](cursor.md)
- [Codex desktop, CLI, and IDE](codex.md)
- [ChatGPT web](chatgpt.md)
- [Windsurf / legacy Cascade](windsurf.md)
- [Other supported client paths](https://vilix.ai/get-started)

Remote MCP support alone is not enough: the client must support Vilix AI's
transport, its chosen authentication method, and read/write tool calls. Your
workspace administrator may also need to allow the server.

## Memory instructions

Add this to the client instructions for conversations where you want Vilix AI
memory. Preserve your other instructions. Client permissions and tool approvals
still apply.

```text
Use Vilix AI memory for each exchange unless I explicitly request stateless mode.

1. Before composing a reply, call get_context with user_prompt set to my exact
   latest message. Use the returned relevant context and instructions.
2. Finalize the answer internally.
3. Before returning it, call save_turn with my exact user_message, that exact
   assistant_message, and an honest source label for this AI client. Reuse the
   returned chat_id for later turns in the same conversation.
4. Return the same answer that was saved.

If a required memory call fails or is unavailable, tell me. Do not claim that
context was retrieved or the exchange was saved when it was not.
```

The names above are Vilix AI's tool names; some clients display a namespaced
version. `get_context` and `save_turn` form the core workflow, while other
available tools cover search and context management.

## Verify the connection

1. Confirm Vilix AI appears connected and that `get_context` and `save_turn` are
   available in the client.
2. In a demo account, follow the [cross-tool example](../examples/sample-memory-workflow.md)
   using fictional information. Inspect the actual save result.
3. Connect a second client to that same account, ask for the fictional project,
   and inspect the retrieval result. It should contain what you saved.

If no context is found, check the account, source conversation, save result,
and whether the client called the tools. Saved context is retrieved selectively;
it is not a guarantee that every past message will be included in every answer.

For connection failures, first check the exact URL, chosen authentication,
client version, enabled tools, and workspace policy. Share a redacted error with
[support@vilix.ai](mailto:support@vilix.ai), never a credential or private memory.
