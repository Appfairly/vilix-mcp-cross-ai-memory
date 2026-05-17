# Vilix + ChatGPT

**What this is for:** Give ChatGPT persistent memory through Vilix, so the
context you build in ChatGPT is available later in Claude, Cursor, Windsurf, and
other MCP-compatible tools — and vice versa.

## Prerequisites

- A Vilix account — sign up at [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
- A ChatGPT plan/tier that supports adding MCP connectors

## Setup

1. Sign in to Vilix and open the setup page: [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
2. In ChatGPT, add a new MCP connector / custom connector.
3. Use the Vilix MCP server endpoint:

   ```
   https://api.getvilix.com/mcp/sse
   ```

4. Complete the **OAuth approval** when prompted. There is no token to paste —
   you approve access once and the connection is established.
5. (Recommended) Add a short system instruction so the assistant uses memory
   consistently:

   ```
   At the start of a task, retrieve relevant context from Vilix.
   After a meaningful exchange, save what is worth remembering to Vilix.
   ```

## Verify it works

Ask ChatGPT to recall something you established in another session or another
tool. If Vilix is connected, it should retrieve that context instead of asking
you to repeat it.

## Notes

- The exact connector UI wording in ChatGPT can change between releases. Follow
  the in-product steps on the [get started page](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs),
  which stays current.
- See [mcp-config.md](mcp-config.md) for the generic MCP configuration shared by
  all clients.

**Get started:** [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
