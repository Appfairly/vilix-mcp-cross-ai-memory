# Connect Vilix AI to Codex

Use saved context from your other AI tools in Codex's desktop, CLI, and IDE
clients. These local clients share MCP configuration on the **same host**.
ChatGPT web uses a [separate setup](chatgpt.md). Documentation checked
September 10, 2026; command syntax also checked with Codex CLI 0.147.0.

## Requirements

- A [Vilix account](https://vilix.ai/get-started).
- A current Codex client with remote MCP access allowed by your workspace.
- Browser access for OAuth, or an API key for the bearer-token alternative.

Choose one authentication path for the `vilix` server. If it is already
configured, inspect the existing entry first and update it instead of adding
duplicate servers.

## OAuth with the CLI

```bash
codex mcp add vilix --url https://api.vilix.ai/mcp
codex mcp login vilix
```

Complete the browser sign-in to the same Vilix account you use in other tools.
Run `codex mcp list`, then use `/mcp` in a Codex session to check the connection.

## Desktop app or IDE extension

1. Open **Settings → MCP servers → Add server** in the desktop app, or the
   IDE extension's **gear menu → MCP servers → Add server**.
2. Name it `vilix`, choose **Streamable HTTP**, and enter
   `https://api.vilix.ai/mcp`.
3. Save and restart the server/client as prompted. Select **Authenticate** and
   complete OAuth. In the IDE, use **Restart extension** when prompted.

The same configuration can be expressed in `~/.codex/config.toml`. Merge the
table without replacing your other settings:

```toml
[mcp_servers.vilix]
url = "https://api.vilix.ai/mcp"
```

Project-scoped `.codex/config.toml` is supported for trusted projects. A different
machine or hosted environment needs its own configuration and authentication;
local settings are not automatically installed everywhere.

## API-key alternative

For a client environment where OAuth is unsuitable, create a key in
[Vilix Agents](https://app.vilix.ai/agents). Make it available as the environment
variable `VILIX_API_KEY` to the process running Codex, using your normal secret
management method. Never commit the value.

```bash
codex mcp add vilix --url https://api.vilix.ai/mcp --bearer-token-env-var VILIX_API_KEY
```

Equivalent TOML:

```toml
[mcp_servers.vilix]
url = "https://api.vilix.ai/mcp"
bearer_token_env_var = "VILIX_API_KEY"
```

Codex sends the value in the `Authorization: Bearer` header. A desktop app may
not inherit an environment variable set in a terminal; use OAuth there unless
you have configured the app's environment. Do not run OAuth login for this
key-based path, and do not put the key in the URL.

## Enable consistent memory use

Add the [memory instructions](mcp-config.md#memory-instructions) to your existing
`~/.codex/AGENTS.md` for all projects, or an `AGENTS.md` in one project. Preserve
existing guidance. Use `source="Codex"` when saving and reuse `chat_id` within
the same conversation. Start a new Codex session after changing instructions.

Verify the connection with the [fictional cross-tool example](../examples/sample-memory-workflow.md)
in a demo account. Inspect the actual tool results. If tools are unavailable,
check `/mcp`, authentication, enabled-tool filters, and workspace policy before
assuming memory was retrieved or saved.

## References

- [OpenAI: MCP setup and supported authentication](https://learn.chatgpt.com/docs/extend/mcp)
- [OpenAI: AGENTS.md instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Vilix's current Codex setup](https://vilix.ai/get-started?tool=codex&method=cli&device=desktop)

Need help? [support@vilix.ai](mailto:support@vilix.ai).
