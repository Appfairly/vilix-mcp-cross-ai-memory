# Connect Vilix AI to Claude and Claude Code

Make saved decisions and context available when you move between Claude and
other Vilix-connected tools. Claude's remote connectors and Claude Code have
separate setup paths. Documentation checked September 10, 2026.

## Claude web and desktop

You need a [Vilix account](https://vilix.ai/get-started) and access to Claude
custom connectors. Anthropic currently lists Free, Pro, Max, Team, and Enterprise
support; Free is limited to one custom connector. Team/Enterprise owners must
make a connector available to their organization before members connect it.

1. Open **Customize → Connectors → + → Add custom connector**.
2. Name it **Vilix AI**, enter the following URL, and select **Add**:

   ```text
   https://api.vilix.ai/mcp
   ```

3. Select **Connect**, sign in to Vilix, and approve access through OAuth.
4. Enable Vilix AI for the conversation under **+ → Connectors**.
5. Add the [memory instructions](mcp-config.md#memory-instructions) to
   **Settings → Instructions for Claude**, or to the relevant Claude project.

For Team/Enterprise owners, the organization setup is **Organization settings →
Connectors → Add → Custom → Web**. Members then connect their own Vilix accounts.

### Phone access

Claude supports connectors on iOS and Android; installing them on mobile is
currently beta. Web and desktop remain the primary custom-connector setup path.
Connect there first if the mobile controls are unavailable, then enable Vilix
in the mobile conversation under the same Claude and Vilix accounts.

## Claude Code

Use a Claude Code account or billing option eligible to run the client. Add the
hosted server with HTTP transport; this does not install a local server:

```bash
claude mcp add --transport http --scope user vilix https://api.vilix.ai/mcp
```

Start Claude Code, open `/mcp`, select `vilix`, and complete the browser OAuth
sign-in. The `user` scope makes the connection available across your local
projects. Use project scope only when you intend that narrower configuration.

Add the [memory instructions](mcp-config.md#memory-instructions) to
`~/.claude/CLAUDE.md` for your projects, or the current project's `CLAUDE.md`.
Keep existing instructions and follow your repository's policy for shared files.

## Verify

Confirm the memory tools are connected, then use the
[fictional cross-tool example](../examples/sample-memory-workflow.md) in a demo
account. Check the actual save and retrieval tool results in both clients.

## References

- [Anthropic: custom connectors, plans, and setup](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)
- [Anthropic: connector and mobile availability](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)
- [Claude Code: MCP configuration and authentication](https://code.claude.com/docs/en/mcp)
- [Vilix's current setup selector](https://vilix.ai/get-started)

Need help? [support@vilix.ai](mailto:support@vilix.ai).
