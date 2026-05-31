# Backyard Reconstruction — Project Repository

**Location:** Littleton, CO (Denver metro) — USDA Zone 5b–6a  
**Jurisdiction:** Douglas County

---

## Purpose

This repository is the single source of truth for planning, tracking, and managing the backyard reconstruction project. It stores all active plans, drawings, reference photos, and design decisions needed to continue the project across sessions.

---

## Ground Truth

All measurements, dimensions, and spatial data come from the official plot plan surveyed by **Aztec Consultants, Inc., dated 5/18/2021, Scale 1" = 20'**. No estimation or approximation of these values is permitted.

| Parameter | Value |
|-----------|-------|
| Lot area | 6,448 sq ft |
| Backyard width (N–S) | 66.19 ft |
| Backyard depth (E–W) | ~45 ft |
| Rear yard setback (regulatory) | 15 ft |
| Side setbacks | 5 ft (corner: 7 ft) |
| SVG working scale | 1 ft = 8 px |

See [backyard_project.md § 1 Ground Truth Data](backyard_project.md#1-ground-truth-data) for the full table of authoritative measurements. **Do not override these values without new survey data.**

---

## Repository Structure

```
/
├── README.md                         ← This file. Start here.
├── backyard_project.md               ← Primary living doc: ground truth, design decisions, status
├── backyard_construction_plan.docx   ← Bilingual (ZH/EN) construction plan with material quantities
├── drawings/                         ← All spatial drawings and plan files
│   ├── backyard_plan_v12.svg         ← Current SVG plan (Plan 3 layout)
│   ├── plot plan current.jpg         ← Annotated: current state (green=grass, black=mulch, blue=concrete)
│   ├── plot plan plan2.jpg           ← Annotated: Plan 2 (red=proposed patio, orange=mulch) — superseded
│   ├── plot plan plan3.jpg           ← Annotated: Plan 3 — CURRENT ACTIVE DESIGN (red=delete zone)
│   └── plot plan.jpg                 ← Official plot plan scan (ground truth source)
├── figures/                          ← Photos and pictures taken of the backyard
│   ├── picture.jpg
│   └── picture2.jpg
└── archive/                          ← Superseded and early-scope documents
    ├── initial plans.png
    ├── mark on picture.jpg
    └── concept render.png
```

---

## Authoritative Documents

| Document | Role |
|----------|------|
| [backyard_project.md](backyard_project.md) | Primary reference. Contains ground truth data, all confirmed design decisions, SVG version history, material quantities, budget, construction phases, and the decision log. **Update this file as decisions are made or changed.** |
| [backyard_construction_plan.docx](backyard_construction_plan.docx) | Bilingual construction plan with step-by-step phases and material quantities. Update in sync with `backyard_project.md`. |
| [shopping_list.md](shopping_list.md) | Full materials shopping list with quantities, checklist, and Denver-area sourcing suggestions. Update as items are purchased. |
| [pioneer_quote_list.md](pioneer_quote_list.md) | Print-and-bring quote list for Pioneer Landscape Centers #1176 in Littleton, with exact Pioneer product names, quantities, and questions to ask. |
| [drawings/backyard_plan_v11.svg](drawings/backyard_plan_v11.svg) | Current visual plan. All zones, dimensions, and colors reflect confirmed design as of v11. This is the reference for any visual or spatial work. |
| [drawings/plot plan.jpg](drawings/plot%20plan.jpg) | Official plot plan scan. The primary source for all lot measurements. Do not modify. |

Documents in [archive/](archive/) are for historical context only and do not reflect current scope or decisions.

---

## Design Status

**Current plan:** Plan 3 (May 2026) — no new paving; demolish staircase + east-wall concrete; keep and expand mulch areas.

**Current phase:** Pre-construction planning. Contractor quotes for Phase 0 (demolition + drip irrigation) not yet obtained.

**Construction phases:**

| Phase | Description | Status |
|-------|-------------|--------|
| Phase 0 | Contractor: demolish staircase + east-wall concrete strip; add drip irrigation to mulch bed | Not started |
| Phase 1 | DIY: grade former concrete zone, fire pit zone prep | Not started |
| Phase 2 | DIY: lawn reseeding, mulch bed, former concrete zone, garden box surrounds | Not started |

Open decisions and next steps are tracked in [backyard_project.md § 8](backyard_project.md#8-open-questions--next-steps).

---

## Working Disciplines

These rules apply to all work done in this repository — by a person or an AI agent.

### Reading the plan

- The SVG coordinate system has **X increasing east, Y increasing south**, scale 1 ft = 8 px.
- The physical plot plan is **rotated**: UP = East, DOWN = West, LEFT = North, RIGHT = South. See [§ 2 Spatial Orientation](backyard_project.md#2-spatial-orientation).
- Always load `drawings/backyard_plan_v11.svg` as the current visual reference.

### Making changes

- **Design decisions** must be confirmed by the homeowner before being recorded.
- When a decision is confirmed, append it to the **Decision Log** in [backyard_project.md § 9](backyard_project.md#9-conversation-key-decisions-log) with a `[Dxx]` entry.
- Update **§ 4 Design Decisions** and **§ 6 Material Quantities** in `backyard_project.md` to reflect the change.
- When the SVG is updated, increment the version number, add a row to the **SVG Version History** table in [§ 5](backyard_project.md#5-svg-plan-version-history), and move the previous SVG to `archive/`.
- Update `backyard_construction_plan.docx` if quantities or phases change.

### What not to change without authorization

- Ground truth measurements in § 1 — immutable unless new survey data is provided.
- Confirmed design decisions in § 4 — only update after explicit homeowner re-confirmation.
- Regulatory setbacks (15 ft rear, 5 ft sides) — these are Douglas County requirements.

### Drawings folder

- `drawings/` holds only the **current** plot plan and **current** SVG version.
- Superseded SVG versions go to `archive/`.
- Do not add concept sketches or work-in-progress files to `drawings/`; use `archive/` or a temporary location.

### Figures folder

- `figures/` contains photos and visual references of the actual backyard.
- Add new photos here as they are taken. Do not delete existing photos.

---

## Key References

| Resource | URL |
|----------|-----|
| Douglas County setback codes | https://www.douglas.co.us/planning/ |
| Colorado 811 (call before digging — required by law) | https://www.colorado811.org |
| HOA | Contact developer for CC&Rs |
| USDA Plant Hardiness Zone | Zone 5b–6a (Littleton, CO, 5,721 ft) |
| Denver Water conservation rebates | https://www.denverwater.org/residential/rebates |
| CSU Extension — Lawn care | https://extension.colostate.edu/lawn-management/ |
