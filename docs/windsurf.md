# Vilix + Windsurf

**What this is for:** Give Windsurf's AI persistent memory through Vilix, so
your project context, preferences, and prior decisions follow you into Windsurf
from ChatGPT, Claude, and Cursor.

## Prerequisites

- A Vilix account — sign up at <https://getvilix.com/get-started>
- A Windsurf version that supports MCP servers

## Setup

1. Sign in to Vilix and open the setup page: <https://getvilix.com/get-started>
2. Open Windsurf's MCP / plugin settings and add a new MCP server.
3. Use the Vilix MCP server endpoint:

   ```
   https://api.getvilix.com/mcp/sse
   ```

4. Complete the **OAuth approval** when prompted. No token to copy or store.
5. Confirm Vilix shows as a connected MCP server in Windsurf.

### Example MCP server entry

Windsurf owns its MCP configuration format and it may change. Treat the block
below as a placeholder and follow Windsurf's current MCP docs and the
[get started page](https://getvilix.com/get-started):

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

Ask Windsurf's AI about a decision or preference you set in another tool. With
Vilix connected, it should retrieve that context automatically.

**Get started:** <https://getvilix.com/get-started>
