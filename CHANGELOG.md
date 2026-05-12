# Changelog

All notable changes to project-setup are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/). Versions match `plugin.json`.

## [0.2.3] — Platform-agnostic Step 0 (2026-05-12)

### Changed
- **Setup command Step 0 now platform-agnostic.** Every `request_cowork_directory(...)` call is conditional: "In Cowork, call `request_cowork_directory(...)`. In Claude Code (or any environment with direct filesystem access), no mount is needed." Same plugin source works in both runtimes.

### Why this matters
Phase 0 of SECOND-BRAIN-V2-SPEC. Removes the implicit Cowork-only assumption so Claude Code users do not hit unsupported tool calls during setup.

## [0.2.0] — Config-root refactor

### Changed
- **Plugin config moved to a user-chosen folder.** Reads and writes now go to `<config-root>/plugins/project-setup.user-context.md`, where `<config-root>` is the folder the user chooses on first plugin setup (recorded at `~/Documents/.claude-plugin-config-root`). The old plugin-relative `references/user-context.md` path failed silently under Cowork's read-only mount.
- **`/setup-projects` gets Step 0** — resolves the config root via the pointer; prompts for it on first run; offers to migrate legacy `~/Documents/Claude/identity.md` / `voice.md` and any pre-staged `~/Documents/Claude/plugin-configs/*.user-context.md` files.
- **Operating skills/commands updated** — `/project-setup` reads from the new path.
- **User-facing prompts and skill descriptions debranded** for fork-friendliness.

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
