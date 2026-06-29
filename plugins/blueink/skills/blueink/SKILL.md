---
name: blueink
description: Use when the user wants to manage Blueink e-signature envelopes, templates, signers, bundle files, or discuss DocuSign-style Blueink plugin behavior through the Blueink MCP server.
---

# Blueink

Use the Blueink MCP tools exposed by this plugin for e-signature work.

## Current MCP actions

- Check API status.
- Search envelopes.
- Get envelope details.
- Get signer status.
- List document templates.
- Create an envelope from an envelope template.
- Create an envelope from documents and signers.
- Get completed bundle files.
- Download completed bundle PDF data.

## Operating rules

- For create/send actions, ask for missing signer names, emails, template IDs, document inputs, and whether the envelope is test or production.
- Prefer test envelopes unless the user explicitly confirms production sending.
- Do not guess template IDs. Use the template-listing tool or ask the user for the exact ID.
- The plugin connects to the production MCP endpoint configured in `.mcp.json`.
