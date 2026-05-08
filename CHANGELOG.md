# Changelog

All notable changes to project-setup are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/). Versions match `plugin.json`.

## [0.1.0] — Initial release

### Added
- End-to-end client engagement initialization slash command (`/project-setup`) producing four outputs in a single response:
  - Drive folder structure (text — user creates manually in their shared drive)
  - Claude Project system prompt (copy-paste ready)
  - Phased project plan with single Immediate Next Step (offers to execute it)
  - Memory node initialization at `~/Documents/Claude/memory/client/[client-name].md` (only if `claude-cortex` is installed)
- User-customizable templates in `references/templates/`:
  - `drive-structure.md` — folder layouts per offering
  - `claude-project-prompt.md` — system-prompt template
  - `project-plans.md` — phased delivery plans per offering
- Starter templates ship with three example offerings (AI Operating Model, Custom Agent Systems, Learning Production System) — replace, remove, or extend per your firm.
- Setup interview captures offerings catalog, drive layout, communication defaults, companion plugin presence.
- Setup reads `~/Documents/Claude/identity.md` (shared identity from cortex) when available.
- Memory node init is conditional on cortex being installed — skipped gracefully otherwise.
