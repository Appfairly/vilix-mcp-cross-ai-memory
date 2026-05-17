# Vilix + Claude

**What this is for:** Give Claude (Claude apps and Claude Code) persistent
memory through Vilix, so decisions and context you create in Claude carry over
to ChatGPT, Cursor, Windsurf, and other MCP-compatible tools.

## Prerequisites

- A Vilix account — sign up at [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
- A Claude client that supports MCP connectors (Claude desktop/web with
  connectors, or Claude Code)

## Setup

1. Sign in to Vilix and open the setup page: [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
2. In Claude, add a new MCP connector (or add the server to your Claude Code
   MCP configuration).
3. Use the Vilix MCP server endpoint:

   ```
   https://api.getvilix.com/mcp/sse
   ```

4. Complete the **OAuth approval** when prompted. No token needs to be copied
   or stored.
5. (Recommended) Add a memory instruction to your project or system prompt:

   ```
   Before answering, retrieve relevant context from Vilix.
   After a meaningful exchange, save what is worth remembering to Vilix.
   ```

### Claude Code (CLI) note

If you use Claude Code, add the Vilix MCP server to your MCP configuration and
authenticate via the OAuth flow. The same endpoint above applies. Refer to the
official docs for the current configuration format: <https://getvilix.com/docs>.

## Verify it works

Start a new Claude conversation and ask it to continue something you began in
ChatGPT or another tool. With Vilix connected, Claude should retrieve that
context automatically.

**Get started:** [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
