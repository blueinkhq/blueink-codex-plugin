# Blueink Plugin for Codex

The Blueink plugin lets Codex agents interact with the [Blueink](https://www.blueink.com) eSignature platform. Using this plugin, an agent can:

- Search envelopes with pagination.
- Retrieve envelope details.
- Inspect signer status.
- List document templates.
- Create envelopes from templates or documents and signers.
- List completed bundle files.
- Download completed bundle PDF data.

## Requirements

- A Blueink account.
- Access to the Blueink remote MCP server configured in `.mcp.json`.

## Authentication

The Blueink MCP server is an OAuth protected resource. When Codex connects without credentials, the server advertises Blueink OAuth metadata through the standard `WWW-Authenticate` flow so the client can complete authorization.

## MCP Server

This plugin connects to the Blueink remote MCP server at:

```
https://mcp.blueink.com/mcp
```

All Blueink operations are routed through this remote MCP server.

## Local Development

If you are running the Blueink MCP server locally (e.g. with `wrangler dev`), update `.mcp.json` to point to your local instance:

```json
{
  "mcpServers": {
    "blueink": {
      "type": "http",
      "url": "http://localhost:8787/mcp",
      "title": "Blueink",
      "description": "Connect to the local Blueink MCP server."
    }
  }
}
```

> **Note:** Do not commit a localhost URL to this public repository. Local development configuration is machine-specific and will break the plugin for other users.

## Plugin metadata

This plugin is MCP-only. It does not bundle Codex skills; behavior is driven by the remote Blueink MCP server plus the plugin manifest metadata.
