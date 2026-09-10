# Connect Vilix AI to Cursor

Bring saved product decisions into Cursor's agent without re-pasting the brief.
This guide covers the desktop editor and Cursor CLI. Documentation checked
September 10, 2026.

## Requirements

- A [Vilix AI account](https://vilix.ai/get-started).
- A current Cursor client with remote MCP enabled. Your organization may need
  to allow the server URL and tools.

## Configure the server

Open `~/.cursor/mcp.json` for your user, or `.cursor/mcp.json` for one project.
Create the file if needed. **Merge** this entry into the existing `mcpServers`
object; keep the other servers:

```json
{
  "mcpServers": {
    "vilix": {
      "url": "https://api.vilix.ai/mcp"
    }
  }
}
```

This is a Streamable HTTP connection with OAuth. No separate `/sse` URL or
local server command is needed.

### Cursor editor

1. Restart Cursor if the new entry is not visible.
2. Open **Customize → MCPs**, enable Vilix AI, and complete the OAuth sign-in.
3. Use Agent mode and confirm `get_context` and `save_turn` are available.
4. Add the [memory instructions](mcp-config.md#memory-instructions) under
   **Customize → Rules** as a User Rule, or use a project rule for a single
   project. Tool approvals still apply.

### Cursor CLI

The CLI reads Cursor's MCP configuration. Authenticate and inspect the server:

```bash
agent mcp login vilix
agent mcp list
agent mcp list-tools vilix
```

Complete the browser sign-in, then start a new agent session.

## Verify

Use [Plan in Claude, build in Cursor](../examples/coding-agent-workflow.md)
with fictional data in a demo account. Inspect the retrieval result in Cursor;
the expected decisions must actually appear before you rely on the answer.
This guide does not establish that a native phone app exposes the same setup
controls as the editor.

## References

- [Cursor: MCP configuration, OAuth, and policy](https://cursor.com/docs/mcp)
- [Cursor: CLI MCP commands](https://cursor.com/docs/cli/mcp)
- [Vilix AI's current Cursor setup](https://vilix.ai/get-started?tool=cursor&method=mcp&device=desktop)

Need help? [support@vilix.ai](mailto:support@vilix.ai).
