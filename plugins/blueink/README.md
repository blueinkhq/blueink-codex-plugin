# Blueink Plugin for Codex

The Blueink plugin lets Codex agents interact with the [Blueink](https://blueink.com) eSignature platform. Using this plugin, an agent can:

- Prepare and send signature packets (bundles) to one or more signers
- Retrieve the status of packets and individual signers
- List and search existing packets
- Cancel or void packets
- Download signed documents

## Requirements

- A Blueink account – sign up at [blueink.com](https://blueink.com)
- A Blueink API key – generate one from the Blueink dashboard under **Settings → API Keys**

## Authentication

When you install this plugin, Codex will prompt you for your **Blueink API key**. This key is stored securely and used to authenticate requests to the Blueink MCP server on your behalf.

## MCP Server

This plugin connects to the Blueink remote MCP server at:

```
https://mcp.blueink.com/mcp
```

All API calls are proxied through this server so your API key is never exposed in client-side code.

## Local Development

If you are running the Blueink MCP server locally (e.g. with `wrangler dev`), update `.mcp.json` to point to your local instance:

```json
{
  "mcpServers": {
    "blueink": {
      "url": "http://localhost:8787/mcp",
      "transport": "http"
    }
  }
}
```

> **Note:** Do not commit a localhost URL to this public repository. Local development configuration is machine-specific and will break the plugin for other users.

## Skills

- **blueink** – core eSignature skill (see `skills/blueink/SKILL.md`)
