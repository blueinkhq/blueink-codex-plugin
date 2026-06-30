# Blueink Codex Plugin Marketplace

This is the public Blueink plugin marketplace repository for [OpenAI Codex](https://openai.com/codex). It allows users to discover and install the Blueink eSignature plugin directly from the Codex Plugins tab.

This repository follows the same public marketplace-repo pattern as [`openai/codex-plugin-cc`](https://github.com/openai/codex-plugin-cc): small public packaging repo, marketplace metadata at the repo root, plugin files under `plugins/<name>`, clear install docs, and no private server implementation code.

## What You Get

- A `blueink` Codex plugin entry in this marketplace.
- A remote MCP connection to Blueink at `https://mcp.blueink.com/mcp`.
- Agent guidance for working with Blueink envelopes, signers, templates, and completed bundle files.

## Requirements

- Codex with plugin support.
- A Blueink account with access to the deployed Blueink MCP/OAuth flow.

## Install

Add the marketplace in Codex:

```bash
codex plugin marketplace add blueinkhq/blueink-codex-plugin
```

Install the plugin:

```bash
codex plugin add blueink@blueink
```

After adding this marketplace you can also search for **Blueink** in the Codex Plugins tab and install it from there.

## Usage

After installation, ask Codex to work with Blueink. Example prompts:

```text
Find Blueink envelopes waiting on signatures.
Search Blueink envelopes for a customer.
Create a test Blueink envelope from a template.
```

## What is Blueink?

Blueink is an eSignature platform that lets you send, sign, and manage documents programmatically. This Codex plugin exposes Blueink through a remote MCP (Model Context Protocol) server so Codex agents can search envelopes, inspect signer status, list templates, create envelopes, and retrieve completed bundle files.

## Repository Structure

```text
blueink-codex-plugin/
  .agents/
    plugins/
      marketplace.json        # Marketplace metadata consumed by Codex
  plugins/
    blueink/
      .codex-plugin/
        plugin.json           # Plugin metadata
      .mcp.json               # MCP server endpoint configuration
      README.md               # Plugin-level documentation
      assets/                 # Plugin logo and icon assets
  README.md                   # This file
  PUBLISHING.md               # Notes on how this marketplace is published
```

## Contributing

Pull requests are welcome. See [PUBLISHING.md](PUBLISHING.md) for notes on marketplace publication and the plugin development workflow.
