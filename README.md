# Blueink Codex Plugin Marketplace

This is the public Blueink plugin marketplace repository for [OpenAI Codex](https://openai.com/codex). It allows users to discover and install the Blueink eSignature plugin directly from the Codex Plugins tab.

## Installing the Blueink Plugin

### Step 1 – Add this marketplace to Codex

```bash
codex plugin marketplace add blueinkhq/blueink-codex-plugin
```

### Step 2 – Install the Blueink plugin

```bash
codex plugin add blueink@blueink
```

After adding this marketplace you can also search for **Blueink** in the **Codex Plugins** tab and install it from there.

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
      skills/
        blueink/
          SKILL.md            # Skill definition used by the agent
  README.md                   # This file
  PUBLISHING.md               # Notes on how this marketplace is published
```

## Contributing

Pull requests are welcome. See [PUBLISHING.md](PUBLISHING.md) for notes on marketplace publication and the plugin development workflow.
