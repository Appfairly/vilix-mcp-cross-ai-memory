# Vilix MCP Configuration (Generic)

**What this is for:** The shared MCP configuration used by every supported
client, including Perplexity and any other MCP-compatible tool not covered by a
dedicated guide.

## Connection details

| Field | Value |
|-------|-------|
| MCP server URL | `https://api.getvilix.com/mcp/sse` |
| Transport | Server-Sent Events (SSE) endpoint, as published on the get started page |
| Authentication | OAuth (approve once in the connection flow — no tokens to store) |

> This endpoint is the one published publicly at
> [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs). It is the single URL used across all
> supported AI tools.

## Generic MCP server entry

Most MCP clients accept a server map similar to the placeholder below. The exact
schema is defined by each client and can change — always cross-check with that
client's MCP documentation and the
[Vilix get started page](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs):

```jsonc
{
  "mcpServers": {
    "vilix": {
      "url": "https://api.getvilix.com/mcp/sse"
      // OAuth is handled during the connection/approval flow.
    }
  }
}
```

## The Vilix MCP tool surface (high level)

Once connected, your AI client can call Vilix to:

- **Retrieve relevant context** before it answers
- **Save useful memories** after a meaningful exchange
- **Continue work across sessions and tools**

The full developer reference — transport, the two-tool surface, JSON-RPC,
errors, and best practices — is maintained in the official docs:
<https://getvilix.com/docs>. Internal implementation details are intentionally
out of scope for this repository.

## Recommended assistant instruction

To make memory use consistent, add an instruction like this to your client's
system/project prompt:

```
Before answering, retrieve relevant context from Vilix.
After a meaningful exchange, save what is worth remembering to Vilix.
Then return the answer.
```

## Perplexity and other MCP-compatible clients

For Perplexity and any other MCP-compatible client: add a new MCP connector,
use the server URL above, and complete the OAuth approval. The wording of the
connector UI varies by client and version — follow that client's current MCP
instructions plus the Vilix get started page.

**Get started:** [getvilix.com/get-started](https://getvilix.com/get-started?utm_source=github&utm_medium=repo&utm_campaign=mcp_docs)
