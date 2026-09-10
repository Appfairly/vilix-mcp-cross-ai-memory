# Connect Vilix AI to ChatGPT web

Share saved project context between ChatGPT and your other connected AI tools.
This guide covers **ChatGPT in a browser using developer mode**, not Codex or
an OpenAI API integration. Documentation checked September 10, 2026.

## Requirements

- A [Vilix account](https://vilix.ai/get-started).
- ChatGPT Plus, Pro, Business, Enterprise, or Education with developer mode
  available. Workspace policies can restrict access.
- A browser. Do not assume the same setup controls exist in native mobile apps.

## Setup

1. In ChatGPT, open **Settings → Security and login** and turn on
   **Developer mode**.
2. Open [Plugins](https://chatgpt.com/plugins), select **+**, and create a
   developer-mode app. Name it **Vilix AI**.
3. Enter this remote MCP URL and choose **OAuth**:

   ```text
   https://api.vilix.ai/mcp
   ```

4. Finish creation, sign in to your Vilix account, and approve access. Your app
   appears under **Drafts**. Do not paste a Vilix API key into the OAuth client
   credentials fields or choose “No Authentication.”
5. In the conversation's **+ → Developer mode** menu, select **Vilix AI**.
   Confirm its memory tools are enabled.
6. Add the [memory instructions](mcp-config.md#memory-instructions) to your
   ChatGPT custom instructions under **Settings → Personalization**.

ChatGPT may ask you to confirm write tools such as `save_turn`. Review and
approve the intended save. Custom instructions do not bypass tool permissions.

## Verify

Use the [fictional cross-tool example](../examples/sample-memory-workflow.md)
with a demo account. Expand the tool calls to confirm that ChatGPT saved the
exchange and the second client retrieved it from the same Vilix account.
Connecting the app does not import every existing ChatGPT conversation.

## References

- [OpenAI: developer mode, eligibility, setup, and tool approvals](https://developers.openai.com/api/docs/guides/developer-mode)
- [Vilix's current ChatGPT setup](https://vilix.ai/get-started?tool=chatgpt&method=mcp&device=desktop)
- [Connection and authentication reference](mcp-config.md)

Need help? [support@vilix.ai](mailto:support@vilix.ai).
