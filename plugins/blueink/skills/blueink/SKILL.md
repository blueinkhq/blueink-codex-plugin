# Blueink eSignature Skill

Use this skill to send, track, and manage eSignature requests through the Blueink platform.

## Overview

Blueink lets you send documents to one or more recipients for electronic signature. Each signature request is called a **packet** (or bundle). A packet contains one or more **documents** and one or more **signers**.

## Example prompts

- "Send this contract to alice@example.com for signature using Blueink."
- "Check the signing status of my latest Blueink packet."
- "List all pending Blueink signature requests."
- "Cancel the Blueink packet I sent yesterday."
- "Download the signed copy of the NDA from Blueink."

## Available operations

| Operation | Description |
|-----------|-------------|
| `create_packet` | Create and send a new signature packet |
| `get_packet` | Retrieve the status and details of a packet |
| `list_packets` | List packets, optionally filtered by status or date |
| `cancel_packet` | Cancel (void) a packet that has not yet been completed |
| `get_document` | Download a document (signed or unsigned) from a packet |
| `list_templates` | List reusable document templates |
| `create_packet_from_template` | Create a packet using a saved template |

## Authentication

This skill uses the **Blueink API key** you provided when installing the plugin. Requests are sent to the Blueink MCP server at `https://mcp.blueink.com/mcp`, which forwards them to the Blueink API using your key.

## Notes

- Completed packets are stored in Blueink and accessible from the Blueink dashboard.
- Packet statuses include: `DRAFT`, `SENT`, `IN_PROGRESS`, `COMPLETE`, `FAILED`, `EXPIRED`, `CANCELLED`.
- Blueink supports email-based authentication for signers; additional authentication methods may be available on higher-tier plans.
