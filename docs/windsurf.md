# Connect Vilix AI to Windsurf / legacy Cascade

Keep saved project context available to Cascade. Current vendor documentation
places the legacy Cascade agent in Devin Desktop; its MCP configuration differs
from the newer Devin Local agent. This guide covers **Cascade**, using its
Windsurf configuration path. Documentation checked September 10, 2026.

## Requirements

- A [Vilix account](https://vilix.ai/get-started).
- Cascade with remote MCP enabled. Enterprise users must enable MCP in settings;
  organization policies may require the server to be allowed.

## Setup

1. Open **Devin Settings → Cascade → MCP Servers**, or Cascade's MCPs control.
   Open the raw configuration at `~/.codeium/windsurf/mcp_config.json`.
2. Merge the following entry into `mcpServers`, keeping existing servers:

   ```json
   {
     "mcpServers": {
       "vilix": {
         "serverUrl": "https://api.vilix.ai/mcp"
       }
     }
   }
   ```

3. Save, refresh the server list, and complete the OAuth sign-in to Vilix.
   This URL uses Streamable HTTP; do not append `/sse`.
4. Enable the Vilix memory tools. If your team uses a server-ID allowlist, it
   must include `vilix` and permit this configuration.
5. Add the [memory instructions](mcp-config.md#memory-instructions) to the
   Cascade rules used by your workspace. Keep existing rules and tool approvals.

If you are using Devin Local rather than Cascade, follow
[Devin's separate MCP configuration](https://docs.devin.ai/cli/extensibility/mcp/configuration)
instead of pasting this file into the wrong client.

## Verify

Use the [fictional cross-tool example](../examples/sample-memory-workflow.md)
in a demo account. Confirm the actual save and retrieval results. If tools are
missing, check authentication, enabled tools, and team policy.

## References

- [Current Cascade MCP documentation](https://docs.devin.ai/desktop/cascade/mcp)
- [Vilix's current Cascade setup](https://vilix.ai/get-started?tool=windsurf&method=mcp&device=desktop)

Need help? [support@vilix.ai](mailto:support@vilix.ai).
