---
description: Configure project-setup for your offerings, drive layout, and companion-plugin integrations. Captures your service catalog so /project-setup can interview clients and produce templated outputs that match your firm. Re-run anytime to add or update offerings.
---

# /setup-projects

Short interview that captures the catalog `/project-setup` needs to be useful for your firm.

---

## Step 1 — Check for existing config

Read `references/user-context.md`. Populated → ask whether to update. Missing → start fresh.

---

## Step 2 — The interview

### Section 1 — Identity
- Your name
- Your company
- One-sentence description of what your firm does
- Your role (Principal / Partner / Founder / etc.)

### Section 2 — Drive layout
- Where do you store active client work? (e.g., Google Drive shared drive name + path: "Active Clients")
- Naming convention for client folders (e.g., "[Client Name] — [Offering Short Name]")
- Any standardized subfolder structure beyond the defaults? (Defaults: 00_Contract, 01_Kickoff, 02_Discovery, 03_Deliverables, 04_Client Assets, 05_Meeting Notes, 06_Internal Working Docs)

### Section 3 — Offerings catalog

For each offering, capture:
- **Full name** (e.g., "AI Operating Model & Governance")
- **Short name** for folder/project labels (e.g., "AI Op Model")
- **Typical duration** (e.g., "6–8 weeks")
- **Phases** — usually 2–4. For each: name, goal (one sentence), typical week range
- **Offering-specific interview questions** — what questions do you ask clients during initialization that are unique to this offering?
- **Standard deliverables** — what outputs does this offering produce (named, not generic)?

Repeat for each offering. (If the user has 1 offering, that's fine. If 3+, work through them one at a time.)

After capturing, edit `references/templates/project-plans.md` to add or update each offering's plan. Edit `references/templates/drive-structure.md` to update folder-02 layouts per offering.

### Section 4 — Communication defaults
- Default communication cadence (e.g., "weekly async update + biweekly sync")
- Default response time (e.g., "1 business day")
- Tools you typically use to communicate with clients (Email / Slack / Teams / etc.)

### Section 5 — Companion plugins
- Is `claude-cortex` installed? (Y/N — drives whether memory node init runs in Output 4)
- Is `core-ops` installed? (Y/N — provides pipeline-analyst for periodic engagement reviews)
- Is `weekly-outreach` installed? (Y/N — useful context if engagements often come from outreach pipeline)

---

## Step 3 — Write the config

Populate `references/user-context.md`:

```markdown
# project-setup user context

_Last updated: [date]_

## Identity
- **Name:** ...
- **Company:** ...
- **What we do:** ...
- **Role:** ...

## Drive layout
- **Active Clients location:** ...
- **Naming convention:** ...
- **Standard subfolder structure:** ...

## Offerings
[For each offering — pulled from interview, also reflected in templates/project-plans.md and templates/drive-structure.md]
- **[Offering Full Name]** ([short name]) — [duration]
  - Phases: ...
  - Offering-specific questions: ...
  - Standard deliverables: ...

## Communication defaults
- **Cadence:** ...
- **Response time:** ...
- **Communication tools:** ...

## Companion plugins
- **claude-cortex:** ...
- **core-ops:** ...
- **weekly-outreach:** ...
```

---

## Step 4 — Update templates

Walk the user through opening `references/templates/project-plans.md` and `references/templates/drive-structure.md`. Suggest specific edits based on the offerings they captured (e.g., "add Phase 1 / Phase 2 / Phase 3 for [Offering] using this structure as a starting point").

The starter templates ship with three example offerings (AI Operating Model, Custom Agent Systems, Learning Production System). The user can:
- Keep them if applicable
- Replace them with their own offerings
- Add additional offerings alongside

---

## Step 5 — Confirm and offer next step

Summarize. Offer:
> "Try `/project-setup` for your next client engagement."

---

## Behavior rules

- One section at a time.
- For Section 3 (offerings catalog), be patient — this is the most important section. The plugin is generic only if the offerings are well-captured.
- Idempotent — re-running adds new offerings or updates existing ones.
