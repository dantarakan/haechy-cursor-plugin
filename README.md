# Haechy for Cursor

<img src="assets/logo.png" alt="Haechy" width="96" height="96">

Haechy puts the apps your AI assistant builds online for your team. Connect the remote MCP server, then ask in plain words: each app gets its own web address (`<name>.haechy.app`), its own Postgres database, sign-in for your colleagues (a one-time link sent to their email, no password and no AI account needed), email sending, API keys stored as environment variables, and nightly backups. Stacks: Node.js, Python and static files. Pick the region: US, EU, UK or Australia.

Outside services reach an app only after you approve them in the Haechy console. Your assistant can ask for access and cannot approve it.

Server URL: `https://mcp.haechy.com/mcp/i/cursor` (OAuth 2.1 with PKCE, dynamic client registration). 29 tools; every tool has a title and read-only, destructive and open-world hints.

## What this plugin contains

- `.cursor-plugin/plugin.json`: the plugin manifest.
- `mcp.json` (and an identical `.mcp.json`): adds the remote Haechy MCP server. No secrets, no local process.
- `assets/`: the logo.

## Use it in Cursor

Install the plugin, or add the server yourself under `mcpServers` in `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "haechy": { "url": "https://mcp.haechy.com/mcp/i/cursor" }
  }
}
```

Cursor opens the Haechy sign-in the first time a tool needs it. New accounts are created in the same window.
Then ask, for example: "Put this app online with Haechy and let my colleague sign in."

Guide: https://haechy.com/docs/connect/cursor

## Other assistants

- Claude on the web: add a custom connector with the URL above ([guide](https://haechy.com/docs/connect/claude-ai))
- Claude desktop: Settings, Connectors, add the URL ([guide](https://haechy.com/docs/connect/claude-desktop))
- Claude Code: `claude mcp add --transport http haechy https://mcp.haechy.com/mcp` ([guide](https://haechy.com/docs/connect/claude-code))
- ChatGPT: add a custom MCP server with the URL ([guide](https://haechy.com/docs/connect/chatgpt))
- Codex: `codex mcp add haechy --url https://mcp.haechy.com/mcp`, then `codex mcp login haechy` ([guide](https://haechy.com/docs/connect/codex))
- VS Code with GitHub Copilot: run MCP: Add Server, choose HTTP, paste the URL ([guide](https://haechy.com/docs/connect/vs-code))
- Gemini CLI: add the URL as an HTTP MCP server

Quickstart: https://haechy.com/docs/quickstart · Privacy: https://haechy.com/legal/privacy · Support: support@haechy.com

## License

MIT for the files in this repository. See [LICENSE](LICENSE).

Haechy is an independent product of DT Global Ventures Ltd. It is not made, sponsored or endorsed by Cursor or Anysphere.
