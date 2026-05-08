# project-setup

End-to-end client engagement initialization for Claude (Cowork + Claude Code).

A new client signs. You run `/project-setup`. Five minutes later: Drive folder structure to create, Claude Project system prompt to paste, a phased project plan with an immediate next step, and (if claude-cortex is installed) a memory node so every future session has context from day one.

## What it does

1. **Interviews you** about the new engagement (basics, scope, context, communication)
2. **Generates outputs:**
   - Drive folder structure (you create manually in your shared drive)
   - Claude Project system prompt (copy-paste ready)
   - Phased project plan + immediate next step (offers to execute)
   - Memory node (if `claude-cortex` is installed)

## Install

Recommended: via the [BrightWayAI marketplace](https://github.com/BrightWayAI/claude-plugins).

```
/plugin marketplace add BrightWayAI/project-setup
/plugin install project-setup@project-setup
```

## First-time setup

Run `/setup-projects`. Captures:

- **Identity** — you, your company, what you do
- **Offerings** — your service offerings, with names, durations, and which template applies to each
- **Drive layout** — where Active Clients lives, naming conventions, folder structure preferences
- **Memory** — whether claude-cortex is installed (drives whether memory init runs)
- **Communication defaults** — your default cadence for client comms

Saved to `references/user-context.md` (gitignored).

## Customizing templates

The plugin ships with **starter templates** in `references/templates/`:

- `drive-structure.md` — folder layouts per offering
- `claude-project-prompt.md` — the system-prompt template
- `project-plans.md` — phased delivery plans per offering

Edit these to match your firm. They're committed to your fork (or to your local clone). Setup interview pulls offering names + durations from your user-context, but the structural templates are yours to customize.

## Companion plugins

- **claude-cortex** — for memory node initialization. If not installed, project-setup skips Output 4.
- **core-ops** — for pipeline-analyst integration when reviewing recently-signed deals.

Works without them.

## What's inside

```
.claude-plugin/plugin.json
commands/
  project-setup.md           Main interview + generation workflow
  setup-projects.md          Plugin configuration interview
skills/
  project-setup/SKILL.md     Auto-fires on new-engagement phrases
  setup/SKILL.md             Auto-fires on setup phrases
references/
  user-context.template.md   Structure (committed)
  user-context.md            Your config (gitignored)
  templates/
    drive-structure.md       Folder layouts (committed; user-editable)
    claude-project-prompt.md System prompt template
    project-plans.md         Phased plans per offering
```

## License

MIT.
