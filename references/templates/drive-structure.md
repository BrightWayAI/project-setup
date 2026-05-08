# Drive Folder Structure Templates

_Edit this file to match your firm's offerings. Setup ships with three example offerings; replace, remove, or add as needed._

Use the base structure for all engagements. Swap offering-specific subfolder 02 based on the active offering(s).

---

## Base structure (all engagements)

```
📁 [Client Name] — [Offering Short Name]
├── 📁 00_Contract & SOW
├── 📁 01_Kickoff
│   ├── 📄 Kickoff Agenda
│   └── 📄 Kickoff Recap
├── 📁 [02 — offering-specific, see below]
├── 📁 03_Deliverables
├── 📁 04_Client Assets
├── 📁 05_Meeting Notes
└── 📁 06_Internal Working Docs
```

**Naming convention:** `[Client Name] — [Offering Short Name]`

Multiple offerings → combine in title (e.g., "AI Op Model + Custom Agents")

---

## Offering-specific Folder 02

### AI Operating Model & Governance

```
├── 📁 02_Discovery & Research
│   ├── 📄 Stakeholder Interview Notes — [Name]
│   ├── 📄 AI Tool & Workflow Inventory
│   └── 📄 Research Synthesis
```

### Custom Agent Systems

```
├── 📁 02_Discovery & Design
│   ├── 📄 Workflow Map — Current State
│   ├── 📄 Agent Design Document
│   └── 📄 Technical Spec
```

### Learning Production System

```
├── 📁 02_Content Audit
│   ├── 📄 Content Inventory
│   ├── 📄 Current Production Workflow Map
│   └── 📄 AI Workflow Design
```

### Multiple offerings (combined)

Use the primary offering's folder 02 structure. Add a second research folder if needed:

```
├── 📁 02_Discovery & Research
├── 📁 02b_Design & Spec          ← add if Custom Agents is included
```

---

## Deliverables subfolders (inside 03_Deliverables)

### AI Operating Model

```
├── 📁 03_Deliverables
│   ├── 📁 Phase 1 — AI Readiness Report
│   ├── 📁 Phase 2 — AI Operating Model
│   └── 📁 Phase 3 — Executive Presentation
```

### Custom Agent Systems

```
├── 📁 03_Deliverables
│   ├── 📁 Phase 1 — Agent Design Document
│   ├── 📁 Phase 2 — Builds (Alpha, Beta)
│   └── 📁 Phase 3 — User Guide & Docs
```

### Learning Production System

```
├── 📁 03_Deliverables
│   ├── 📁 Phase 1 — Content Audit & Workflow Map
│   ├── 📁 Phase 2 — Pilot Assets
│   └── 📁 Phase 3 — Production Run & Playbook
```

---

## Adding your own offerings

1. Add a new section under "Offering-specific Folder 02" with the folder structure for that offering.
2. Add a corresponding section under "Deliverables subfolders" with phase names.
3. Update `references/user-context.md` with the offering name, short name, and duration.
4. Update `references/templates/project-plans.md` with the phased plan.
