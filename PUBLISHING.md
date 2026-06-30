# Publishing the Blueink Codex Plugin

## How this marketplace works

This repository acts as a **custom Codex plugin marketplace**. Any Codex user who adds it with:

```bash
codex plugin marketplace add blueinkhq/blueink-codex-plugin
```

will be able to search for **Blueink** in the Codex Plugins tab and install it directly. No central approval is required for a custom marketplace – the GitHub repository URL itself is the marketplace identifier.

## Public marketplace repo pattern

This repo follows the same high-level packaging style as [`openai/codex-plugin-cc`](https://github.com/openai/codex-plugin-cc):

- keep the public repo small and install-focused
- store marketplace metadata at the repository root
- store plugin implementation/metadata under `plugins/<name>`
- provide concise install and usage docs
- keep private runtime/server implementation code out of the public plugin repo

`openai/codex-plugin-cc` targets Claude Code and therefore uses `.claude-plugin` metadata. This Blueink repository targets Codex and uses the Codex plugin metadata files:

- `.agents/plugins/marketplace.json`
- `plugins/blueink/.codex-plugin/plugin.json`
- `plugins/blueink/.mcp.json`

## Plugin entry point

The marketplace is defined in `.agents/plugins/marketplace.json`. It references the plugin located at `./plugins/blueink`, which in turn contains:

- `.codex-plugin/plugin.json` – plugin metadata (name, display name, description, etc.)
- `.mcp.json` – the MCP server endpoint that Codex connects to
- `assets/` – plugin logo and icon assets

## MCP server endpoint

The plugin connects to the Blueink remote MCP server. The endpoint is configured in `plugins/blueink/.mcp.json`. The current value points to the production endpoint:

```
https://mcp.blueink.com/mcp
```

If you are developing locally, replace the URL with your local dev server (e.g. `http://localhost:8787/mcp`). **Do not commit a localhost URL** to this public repository; it is only meaningful on the developer's machine and will break the plugin for all other users.

## Including Blueink in the default/global Codex marketplace

Being discoverable from a custom marketplace (this repo) is separate from being listed in the **default** Codex marketplace that ships with Codex out of the box. Getting into the default marketplace requires a separate review and approval process by OpenAI / the Codex marketplace curators. This repository alone does not achieve that.

## Releasing a new version

1. Update the relevant files (`plugin.json`, `.mcp.json`, assets, docs, etc.).
2. Commit and push to `main`.
3. Codex users who have already added this marketplace will receive the updated plugin metadata the next time Codex refreshes marketplace data.

No versioned releases or tags are strictly required, but tagging releases is recommended for auditability.
