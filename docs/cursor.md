# Vilix + Cursor

**What this is for:** Give Cursor's AI persistent memory through Vilix, so the
product decisions and architecture you discussed in ChatGPT or Claude are
already available when you start implementing in Cursor.

## Prerequisites

- A Vilix account — sign up at [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
- A Cursor version that supports MCP servers

## Setup

1. Sign in to Vilix and open the setup page: [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
2. Open Cursor's MCP settings and add a new MCP server.
3. Use the Vilix MCP server endpoint:

   ```
   https://api.getvilix.com/mcp/sse
   ```

4. Complete the **OAuth approval** when prompted. No token to paste or store.
5. Confirm the Vilix MCP server appears as connected in Cursor's MCP settings.

### Example MCP server entry

Cursor configures MCP servers via its settings UI / `mcp.json`. The exact
schema is owned by Cursor and may change — treat the block below as a
placeholder and follow Cursor's current MCP docs and the
[get started page](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs):

```jsonc
{
  "mcpServers": {
    "vilix": {
      "url": "https://api.getvilix.com/mcp/sse"
      // Authentication is completed via OAuth in the connection flow.
    }
  }
}
```

## Verify it works

Ask Cursor's AI to summarize the plan or decisions you made earlier in another
tool. With Vilix connected, it should pull that context rather than starting
from zero.

See [examples/coding-agent-workflow.md](../examples/coding-agent-workflow.md)
for an end-to-end "decide in Claude, build in Cursor" flow.

**Get started:** [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
