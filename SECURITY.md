# Security Policy

## What this plugin does with your data

Project Setup interviews you about a new client engagement and produces structured outputs (Drive folder structure to create manually, Claude Project system prompt, phased project plan, optional memory node). Reads almost nothing automatically; writes only locally.

**Reads:**
- **Information from the user during the interview** (no automated reads).
- **Plugin references** — `references/user-context.md` (your offerings catalog), `references/templates/*.md` (template files for the four outputs).
- **Working memory** (if `claude-cortex` installed) — `~/Documents/Claude/memory/DASHBOARD.md` to determine where the new memory node should go.
- **Shared user-level config** — `~/Documents/Claude/identity.md` (read-only).

**Writes:**
- **Plugin user-context** — `references/user-context.md` (after `/setup-projects`).
- **Memory node** (only if `claude-cortex` installed and user confirms) — `~/Documents/Claude/memory/client/[client-name].md` plus a small entry in `DASHBOARD.md` for the new node.
- **Outputs in the conversation** — Drive folder structure (text only; user creates manually), Claude Project system prompt (copy-paste ready), phased project plan, immediate next step.

**Does not:**
- **Create Drive folders.** Outputs the structure for the user to create manually in their Drive.
- **Modify the Claude Project.** Outputs the system prompt for the user to paste at claude.ai.
- **Read or modify the SOW or contract files.** The interview asks the user to summarize; the plugin doesn't access contract files directly.
- **Send any data outside your machine** beyond what the user pastes into Cowork's conversation.

## Where data lives

- Plugin reference files (config and templates) inside the installed plugin directory.
- Memory node at `~/Documents/Claude/memory/client/[client-name].md` (if cortex installed).
- Shared identity (read-only) at `~/Documents/Claude/identity.md`.

## What gets sent off your machine

- Nothing the plugin initiates. The user copy-pastes outputs (system prompt, folder structure) into other tools manually.

## Supported versions

| Version | Supported |
|---------|-----------|
| 0.1.x   | Yes       |

## Reporting a vulnerability

Report privately via GitHub Security Advisories:

https://github.com/BrightWayAI/project-setup/security/advisories/new

Do not open a public issue for security concerns. We aim to respond within 5 business days.
