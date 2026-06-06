# Backyard Renovation Project — AI Agent Handoff Document

> **Purpose:** This document contains all project context, ground truth data, design decisions, and current status needed for an AI agent to continue optimizing this renovation project without loss of context.
>
> **Location:** Littleton, CO (Denver metro) — Douglas County
> **Plot Plan Source:** Aztec Consultants, Inc. — dated 5/18/2021, Scale 1" = 20'

---

## Table of Contents

1. [Ground Truth Data](#1-ground-truth-data)
2. [Spatial Orientation](#2-spatial-orientation)
3. [Existing Conditions](#3-existing-conditions)
4. [Design Decisions (Confirmed)](#4-design-decisions-confirmed)
5. [SVG Plan Version History](#5-svg-plan-version-history)
6. [Material Quantities & Budget](#6-material-quantities--budget)
7. [Construction Plan Summary](#7-construction-plan-summary)
8. [Open Questions & Next Steps](#8-open-questions--next-steps)
9. [Conversation Key Decisions Log](#9-conversation-key-decisions-log)
10. [File Index](#10-file-index)

---

## 1. Ground Truth Data

> **CRITICAL:** All design and construction calculations must use these values as the single source of truth. Do not estimate or approximate these figures — they come directly from the official plot plan.

### Lot Dimensions

| Parameter | Value | Source |
|-----------|-------|--------|
| Lot area | 6,448 sq ft | Plot plan legal description |
| Plot plan scale | 1" = 20' | Title block |
| Working scale used in SVG | 1 ft = 8 px | Derived |

### Backyard Boundary Dimensions

| Boundary | Direction | Length | Notes |
|----------|-----------|--------|-------|
| East fence | N–S | **66.19 ft** | Rear boundary, confirmed from plot plan |
| South boundary (lot edge) | E–W | **115.19 ft** | East side of lot |
| North boundary (lot edge) | E–W | ~115 ft | West side, partially obscured by engineer stamp |
| West boundary (street) | — | Curved arc | L=37.06/R=250 + L=45.06/R=250 |

### House & Backyard Key Measurements

| Item | Measurement | Notes |
|------|-------------|-------|
| Backyard width (N–S) | **66.19 ft** | Total east fence span |
| Backyard depth (E–W) | **~45 ft** | House rear wall to east fence |
| North side setback | **18.1 ft** | House north wall to north fence |
| South side setback | **9.96 ft** | House south wall = South Pathway width |
| Deck dimensions | **20 × 10 ft** | Within house footprint (see §3) |
| Staircase dimensions | **~20 ft × 4 ft** | Cantilevered on east wall exterior |
| Rear yard setback (regulatory) | **15 ft** | Douglas County requirement |
| Side setbacks | **5 ft** (corner: 7 ft) | Douglas County requirement |

### Elevation & Grade Data

| Location | Value | Notes |
|----------|-------|-------|
| Finished floor elevation (FF) | **5,721.3 ft** | Above sea level |
| Top of foundation (TOF) | **5,720.1 ft** | |
| Lawn slope (main) | **7.9%** | Slopes east (toward fence) |
| North patio extension slope | **10%** | Slopes east |
| South Pathway slope | **13%** | Steepest zone, slopes east |
| Deck area slope | **10%** | |

### Regulatory Setbacks Summary

```
East (rear) fence:  ←————— 15 ft setback ——————|  ← no permanent structures east of this line
North fence:        5 ft setback
South fence:        5 ft setback (corner: 7 ft)
```

---

## 2. Spatial Orientation

> **IMPORTANT for SVG/plan reading:** The plot plan is rotated from conventional north-up orientation.

```
Plot plan orientation:
  UP    = East (slightly south of true east)
  DOWN  = West
  LEFT  = North (slightly west of true north)
  RIGHT = South

Real-world house orientation:
  House faces west (street side)
  Backyard opens east
  Morning sun hits backyard; afternoon shade from house
```

### SVG Coordinate System (used in all plan files)

```
X-axis: West → East  (left to right)
Y-axis: North → South (top to bottom)
1 ft = 8 px

Key X coordinates:
  X=20   House west wall (edge of canvas)
  X=80   Existing Patio west edge / North Patio Extension west edge
  X=160  House east wall (rear wall)
  X=192  Staircase east edge / South Pathway east terminus
  X=224  East Corridor east edge / East South Strip east edge
  X=468  Lawn east edge (6.5 ft buffer from east fence)
  X=520  East fence

Key Y coordinates:
  Y=80   North fence
  Y=105  North Patio Extension north edge
  Y=160  Lawn north edge (~10 ft south of north fence)
  Y=225  House north wall / existing Patio north edge / staircase top
  Y=257  Arc cut terminus (east corridor starts full width here)
  Y=385  Existing Patio south edge / staircase base / east corridor south
  Y=530  House south wall / South Pathway north edge
  Y=610  South fence (South Pathway south edge)
```

---

## 3. Existing Conditions

### House Structure (Rear/East Face)

```
┌─────────────────────────────────┐  ← House north wall (Y=225)
│                                 │
│   DECK (20×10 ft)               │  Deck is INSIDE house footprint
│   Second floor, east side       │  X=80~160, Y=225~385
│   White railings                │
│                                 │
│   PATIO (20×10 ft)              │  Ground floor, directly below Deck
│   Concrete slab                 │  X=80~160, Y=225~385
│   Currently used for storage    │
│                                 │
└─────────────────────────────────┘  ← House south wall (Y=530)
         │
    STAIRCASE                         Cantilevered outside east wall
    X=160~192, Y=225~385              ~4 ft wide × 20 ft long
    Descends from Deck NE corner      Runs N→S, lands at Y=385
    Has step treads visible in plan
```

### Existing Water & Hardscape

| Element | Location | Condition | Plan |
|---------|----------|-----------|------|
| Concrete patio (walkout) | X=80~160, Y=225~385 | Functional, cluttered | Clear & reuse |
| South Pathway | X=20~192, Y=530~610 | 9.96 ft wide, 13% slope | Retain as-is |
| Staircase base strip | X=160~192, Y=385~530 | Rock-filled; below staircase, connects patio east edge to South Pathway | Pave — clear rocks, match North Patio material |
| L-turn at SE corner | X=160~192, Y≈530 | Connects staircase base strip to South Pathway | Retain / integrate into paving |
| Downspout (north side) | ~X=155, Y=145 | Surface exit in patio zone | Reroute underground |

### Existing Vegetation

| Plant | Location | Status |
|-------|----------|--------|
| Pear tree | NE corner, near X=498, Y=80 (north fence) | Retain |
| 3× Garden Boxes | Along north fence, west of pear tree | Retain all 3 |
| Pine tree | SE corner, near east fence, close to south pathway | Retain |
| Lawn | X=192~468, Y=160~385 (approx.) | Sparse, weedy — reduce & reseed |

### Existing Irrigation System

| Component | Description |
|-----------|-------------|
| West main pipe | N–S orientation, near X=192, 4 sprinkler heads |
| East main pipe | N–S orientation, near X=462, 4 sprinkler heads |
| Entry point | Both pipes enter from north extension zone (under proposed patio) |
| Coverage | Current 8 heads cover full existing lawn |
| Issue | Both pipes will be covered by new North Patio Extension |

### Lawn Issues

- Center section: bare/sparse — poor soil, insufficient water
- North section (near north fence): better quality due to shade
- South section: below average
- East boundary: weeds constantly invade from open rangeland outside east fence
- Overall: difficult to maintain due to slope, dry climate, weed pressure

---

## 4. Design Decisions (Confirmed)

> All items below have been explicitly confirmed by the homeowner during conversation. Do not change without re-confirmation.

### 4.1 Patio System (Phase 1)

> **Plan 3 update (May 2026)**: North Patio Extension and seat wall are still active. East Corridor and East South Strip (eastward extensions into grass) are cancelled. Existing east-wall concrete strip (X=160~192, Y=385~530) is **retained as-is**. See §9 [D29]–[D31].

**North Patio Extension** — ACTIVE
- Size: Trapezoid — east side 220", west side 195", south side (perpendicular) 171" = **246.4 sq ft**
- Location: North of existing patio, X=80~192, Y=105~225
- Material: **Home Depot grey stone pavers** — confirmed [D35]
- Purpose: Outdoor dining area + grill station
- Feature: Low seat wall (12–15" high, 16–18" wide) at Y=225 separating from existing patio level
- Grade handling: 10% slope → two-tier terrace; north extension sits ~12–15" lower than existing patio

**Curved Diagonal Cut (Arc)** — ACTIVE (north patio NE corner transition)
- Shape: Curved arc (NOT straight line)
- Start: Existing patio NE corner at (X=192, Y=225)
- End: East corridor at (X=224, Y=257)
- Direction: ~45° SE diagonal arc
- Note: Arc cut is still needed at the NE corner of the North Patio Extension even though the East Corridor is cancelled

**Seat wall** — ACTIVE (confirmed May 2026)
- Location: Y=225, along south edge of North Patio Extension
- Height: 12–15", Width: 16–18"
- Material: CMU blocks 8×8×16", mortar-set (3 courses)
- Length: 14 ft
- Purpose: Grade separation + seating

**Staircase Base Strip** — ACTIVE
- Size: 220" long × 46" wide = **70.3 sq ft**
- Location: X=160~192, Y=385~530 (directly below staircase, same footprint width)
- Current state: rock-filled (not concrete) — clear rocks, install paving
- Purpose: complete the patio edge connection from staircase base to South Pathway
- Material: Home Depot grey stone pavers (match North Patio Extension) — confirmed [D35]

~~**East Corridor** (~4 ft × 20 ft, X=192~224, Y=225~385, east of staircase into grass)~~ — **CANCELLED (Plan 3)**
- This was the extension *beyond* the staircase footprint into the grass/yard. Not needed.

~~**East South Strip** (~4 ft × 18 ft, X=192~224, Y=385~530, east of staircase footprint into grass/mulch)~~ — **CANCELLED (Plan 3)**
- This was the eastward extension from the staircase edge into the existing grass and black mulch area. Not needed.

---

### 4.2 Fire Pit

- Type: **Portable / movable** (not built-in)
- Location: At boundary of lawn and mulch bed, ~center-east area
- Zone: 10 ft diameter circle, ~79 sq ft
- Ground prep: Level pad, 4" compacted gravel base
- Clearances: ≥10 ft from structure, ≥10 ft from fence

### 4.3 Lawn

- **Retain**: ~870 sq ft (approx. 34 ft × 28 ft minus fire pit circle)
  - Concentrated in north zone (better shade, better turf)
  - X=224~468, Y=160~385
- **Remove**: ~612 sq ft south section (becomes mulch bed)
- **Reseeding**: Fine Fescue (shaded/north) or Tall Fescue (traffic areas)
- **Weed barrier strip**: 2 ft wide along east fence interior (entire 66 ft length) to block rangeland weed invasion

### 4.4 Mulch Planting Bed

- Area: ~970 sq ft (X=192~468, Y=305~530) — north edge extended +10 ft total from staircase base line
- Materials: Commercial-grade weed barrier + brown dyed mulch, 3" depth
- Features: Stepping stones (17× 24"×18" stones) winding through bed
- Drip irrigation branch from west main pipe

### 4.5 East Buffer Strip

- Existing black mulch arc already present — **retain as-is**
- No construction work needed
- Pine tree in SE corner — retain

### 4.6 Garden Boxes

- **3 existing boxes retained** — no new boxes
- Located along north fence, west of pear tree, evenly spaced
- Maintenance: Add 2" mulch to pathways around boxes (~96 sq ft)

### 4.7 Irrigation System

**Subplan 1 — contractor, before paving:**
- West pipe only: 4" PVC conduit sleeve (~15 ft) under north patio footprint — east pipe at X=462 is outside patio footprint, no sleeve needed
- Heads: reduce 8 → 6 (cap 2 in north zone, install 2× 180° half-circle nozzles, ~9 ft spacing)
- See [`task_details/irrigation_sleeve.md`](task_details/irrigation_sleeve.md) for full contractor brief

**Subplan 2 — contractor, before mulch installation:**
- New: drip irrigation for mulch bed (~970 sq ft, 12" line spacing, branch from west pipe)

### 4.8 Downspout

- **🟡 Partially done** — existing roll-out extender is in place and functional
- **Remaining:** Re-orient bottom elbow to point east (toward lawn at X=192+) after east-side pavers are laid
- See [`task_details/downspout_reroute.md`](task_details/downspout_reroute.md) for details

### 4.9 Items Explicitly REMOVED from Scope

| Item | Reason |
|------|--------|
| Plant installation in mulch bed | Homeowner will handle separately |
| North privacy planting (Serviceberry) | Removed from scope |
| Garden box expansion (new boxes) | Already have 3, no expansion needed |
| East buffer strip renovation | Black mulch already exists, retain as-is |
| **East Corridor** (78 sq ft new paving east of staircase) | **Plan 3 decision — cancelled May 2026** |
| **East South Strip** (72 sq ft new paving, staircase base to South Pathway) | **Plan 3 decision — cancelled May 2026** |

### 4.10 South Pathway

- **Fully retain** existing concrete
- Width: 9.96 ft, slope: 13%
- Terminus: Ends at X=192 (east wall of staircase strip), does NOT continue east
- Future: Plant drought-tolerant plants on both sides (low priority)

---

## 5. SVG Plan Version History

| Version | File | Key Changes |
|---------|------|-------------|
| v1 | backyard_plan.svg | Initial draft — incorrect deck position, wrong orientation |
| v2 | backyard_plan_v2.svg | Corrected deck inside house, staircase exterior |
| v3 | backyard_plan_v3.svg | Corrected patio fully inside house, L-shaped concrete strip |
| v4 | backyard_plan_v4.svg | Fixed staircase length = patio length (20 ft), north patio from X=80 |
| v5 | backyard_plan_v5.svg | Corrected lawn boundaries (N: 10 ft gap, E: 6.5 ft gap), garden box to N fence, pathway ends at X=192 |
| v6 | backyard_plan_v6.svg | Added east corridor + east south strip, diagonal cut, pathway extended to X=224 |
| v7 | backyard_plan_v7.svg | Diagonal cut moved to (192,225)→(224,257), 45° |
| v8 | backyard_plan_v8.svg | Lawn polygon extended to fill NE strip and diagonal triangle (error — wrong fill) |
| v9 | backyard_plan_v9.svg | Lawn polygon corrected to Y=225 stop |
| v10 | backyard_plan_v10.svg | Diagonal corrected: upper-right = lawn, lower-left = patio; straight line used |
| v11 | backyard_plan_v11.svg (archived) | Arc cut, black mulch strip, 3 garden boxes, stepping stones, pine tree SE, irrigation system — Plan 2 |
| **v12** | **backyard_plan_v12.svg** | **Plan 3: East Corridor + East South Strip removed; Staircase Base Strip added as new paving; lawn/mulch extended to X=192** |

### Current SVG (v11) Zone Color Key

| Zone | Fill Color | Hex |
|------|-----------|-----|
| House | Gray-beige | `#d0c8b8` |
| Existing Patio / Deck overlay | Medium gray | `#b8b0a8` |
| Staircase | Tan/wood | `#e8d0a0` |
| Existing concrete strip + Pathway | Gray | `#a8a090` |
| North Patio Extension (new) | Light gray dashed | `#c8c0b8` |
| East Corridor + East South Strip (new) | Light gray dashed | `#c8c0b8` |
| Lawn | Green | `#7ab648` |
| Mulch planting bed | Brown | `#a07850` |
| East buffer strip | Dark brown | `#8B6040` |
| Black mulch arc in buffer strip | Near-black strokes | `#1a1a1a` |
| Fire pit | Orange circle | `#d4956a` |
| North planting strip | Dark green | `#5a7a40` |
| Garden boxes | Tan/gold | `#c8a060` |
| Pear tree / Pine tree | Dark green circle | `#3a7a28` |
| Irrigation pipes | Blue | `#4090d0` |
| Sprinkler heads | Blue dot + fan | `#4090d0` |
| East fence | Brown dashed | `#8B6914` |
| Arc cut line | Red | `#e05050` |
| Slope arrows | Orange | `#d06010` |
| 15 ft setback line | Red dashed | `#e03030` |

---

## 6. Material Quantities & Budget

> **Updated for Plan 3 (May 2026)**: East Corridor + East South Strip cancelled. North Patio Extension + Staircase Base Strip remain active paving scope. Existing east-wall concrete strip retained.

### Area Summary

| Zone | Dimensions | Area | Notes |
|------|-----------|------|-------|
| **North Patio Extension** | Trapezoid: E=220", W=195", S=171" | **246.4 sq ft** | Active — Phase 1 DIY |
| **Staircase Base Strip** | 220" × 46" | **70.3 sq ft** | Active — below staircase, currently rocks |
| ~~East Corridor~~ | ~~4 ft × 20 ft, X=192~224~~ | ~~78 sq ft~~ | Cancelled (Plan 3) — was extension east into grass |
| ~~East South Strip~~ | ~~4 ft × 18 ft, X=192~224~~ | ~~72 sq ft~~ | Cancelled (Plan 3) — was extension east into grass/mulch |
| **Total new paving** | | **316.7 sq ft** | Updated with precise field measurements (June 2026) |
| Lawn (retained) | ~34 ft × 18 ft | ~625 sq ft | South edge moved 10 ft north for mulch extension |
| Mulch planting bed | ~34 ft × 28 ft | ~970 sq ft | North edge extended +10 ft (Y=305~530) |
| Fire pit circle | dia. 10 ft | ~79 sq ft | |

### Material Quantities (Plan 3)

| Material | Calculation | Quantity | Unit |
|----------|------------|----------|------|
| Class 6 aggregate base (4") | 282 sqft × 4/12 ft × 1.05 waste | **~3.9 cu yd** | (~105 cu ft) |
| Coarse sand bedding (1") | 282 sqft × 1/12 ft × 1.05 waste | **~1.1 cu yd** | (~29 cu ft) |
| Flagstone (option A) | 282 sqft × 1.10 waste | **~310 sqft / ~2.6–3.7 tons** | 15–20 lb/sqft |
| Concrete pavers 24"×24" — Home Depot grey stone | Grid count: 74 (patio) + 20 (strip) | **94 units / ~1,692 lb** | 18 lb/unit; grid-counted incl. cuts [D35] |
| CMU blocks 8×8×16" (seat wall) | 14 ft × 3 courses × ~11 blocks/course | **~33 blocks** | |
| Mortar mix | Seat wall | **~2 bags** | 60 lb/bag |
| Polymeric sand | ~1 bag/100 sqft | **~3 bags** | 50 lb/bag |
| Flexible metal edging | Patio perimeter + arc | **~55 ft** | |
| Polyurethane sealant | Expansion joints | **~1 tube** | 10 oz/tube |
| PVC conduit sleeve 4" | West pipe under north patio only | **~15 ft** | East pipe outside patio footprint — no sleeve needed |
| Commercial weed barrier | 970 bed × 1.10 | **~1,070 sqft** | |
| Garden staples / U-pins | 1,065 sqft × 0.15/sqft | **~160 units** | |
| Black dyed mulch (3") | 970 sqft × 3/12 × 1.10 | **~9.9 cu yd** | (~267 cu ft) |
| Mulch for box pathways (2") | 96 sqft × 2/12 | **~0.6 cu yd** | (~16 cu ft) |
| Stepping stones 24×18" | 10 units | **~10 units / ~33 sqft** | |
| Fine/Tall Fescue seed | 625 sqft / 1000 × 5.5 lb | **~3.5 lb** | |
| Premium topsoil | 625 sqft × 2.5/12 ft | **~3.2 cu yd** | (~87 cu ft) |
| Straw mulch | 625 sqft / 500 sqft per bale | **~2 bales** | |
### Budget Summary (Plan 3)

| Category | Low | High | Notes |
|----------|-----|------|-------|
| Contractor: irrigation sleeve + west pipe reroute | $500 | $800 | 4" PVC sleeve ~30 ft under north patio |
| Contractor: downspout reroute | $200 | $400 | PVC 12 ft underground, pop-up emitter |
| Contractor: drip irrigation for mulch bed | $300 | $600 | Branch from existing west pipe |
| Phase 1: aggregate + sand | $150 | $270 | ~2.9 + 0.8 cu yd |
| Phase 1: flagstone paving (option A) | $700 | $1,400 | ~231 sqft |
| Phase 1: (alt.) concrete pavers (option B) | $350 | $700 | ~58 units |
| Phase 1: seat wall + mortar | $100 | $190 | 33 blocks |
| Phase 1: polymeric sand + edging + sealant | $90 | $160 | |
| Phase 1: tool rentals | $150 | $250 | Compactor + grinder + sod cutter |
| Phase 2: topsoil + seed + straw | $170 | $340 | |
| Phase 2: weed barrier + mulch (895 sqft) | $330 | $560 | |
| Phase 2: stepping stones + staples | $90 | $180 | |
| Phase 2: mulch box pathways + grading fill | $50 | $110 | |
| Misc. | $50 | $100 | |
| **DIY Total (flagstone)** | **$1,810** | **$3,445** | |
| **DIY Total (paver)** | **$1,460** | **$2,745** | |
| **Grand Total incl. contractor (flagstone)** | **$2,810** | **$5,245** | |
| **Grand Total incl. contractor (paver)** | **$2,460** | **$4,545** | |

---

## 7. Construction Plan Summary

> Two independent subplans — either can proceed first or in parallel. No shared work zones or sequencing dependency between them.

---

### Subplan 1: Patio Extension

**Scope:** North Patio Extension (246.4 sqft) + Staircase Base Strip (70.3 sqft) + seat wall
**Best season:** May–September (paving)

#### DIY Steps

| Step | Task | Duration |
|------|------|----------|
| P1-A | Irrigation sleeve (~15 ft, west pipe only) + head adjustment (8→6) — see `task_details/irrigation_sleeve.md` | 0.5–1 day |
| P1-B | Site clearing — north patio zone, ~3.9 cu yd excavation | 1 day |
| P1-C | Base course — ~2.9 cu yd Class 6 + 0.8 cu yd sand, compact | 1 day |
| P1-D | North patio paving (246.4 sqft) + seat wall (14 ft, 3 courses) | 2–3 days |
| P1-E | Staircase base strip (70.3 sqft) — clear rocks, base course, pave to match | 1 day |
| P1-F | 🟡 Downspout elbow re-orient east (after east-side pavers laid) | 0.5 day |

**Subplan 1 DIY labor: ~6–7.5 days**

#### Key Rules

- **Call 811** before any digging (Colorado state law)
- **4" compacted Class 6 base** mandatory for all paved surfaces — freeze-thaw protection
- **2% drainage slope** on all paved surfaces, draining away from house
- All paved surfaces must respect **15 ft east setback** and **5 ft side setbacks**
- **Arc cut**: angle grinder in 3–4 shallow passes, flexible metal edging to retain edge
- **Expansion joint**: 0.5" gap at seat wall, filled with polyurethane sealant (NOT polymeric sand)
- Seat wall: **mortar-set** (not dry-stack) for stability in freeze-thaw
- **Drainage**: all paved surfaces slope away from house foundation (min. 2%)

---

### Subplan 2: Lawn Reduction + Mulch

**Scope:** Reduce lawn to ~625 sqft (north zone); convert ~970 sqft south zone to mulch bed; fire pit pad; garden box surrounds
**Best season:** August 15 – September 15 for seeding; mulch any time
**Work zone:** X=192~468, Y=305~530 — no overlap with patio footprint

#### Pre-req — Contractor (before mulch installation)

1. **Mulch bed drip line**: branch from west irrigation pipe, ~970 sqft at 12" line spacing

#### DIY Steps

| Step | Task | Duration |
|------|------|----------|
| M2-A | Lawn: remove sod from south zone, amend ~625 sqft retained area, reseed, straw | 1–2 days |
| M2-B | Mulch bed (~970 sqft, Y=305~530): weed barrier, stepping stones (17×), black mulch (3") | 1–2 days |
| M2-C | Fire pit zone: level pad, 4" compacted gravel base, edging | 0.5 day |
| M2-D | Garden box surrounds: 96 sqft mulch paths, tree rings | 0.5 day |

**Subplan 2 DIY labor: ~3–5 days**

#### Key Rules

- **Call 811** before any digging
- Weed barrier: commercial-grade, overlap seams 6", pin every 18"
- Mulch depth: 3" after settling (apply ~3.5" to account for compaction)
- Seeding window: August 15 – September 15 for best germination (Colorado Zone 5b–6a)
- **Weed barrier strip**: 2 ft wide along east fence interior (entire 66 ft) to block rangeland weed invasion

---

## 8. Open Questions & Next Steps

### Pending Homeowner Decisions

- [x] **Downspout reroute method**: Option B (roll-out extender, DIY) — re-orient elbow east after east-side pavers are laid
- [x] **Paving material choice**: ~~Natural flagstone vs. concrete pavers~~ → **Home Depot grey stone pavers** confirmed [D35]
- [ ] **Mulch bed planting**: Species selection for planting bed (not in current scope — homeowner to handle separately)
- [ ] **Contractor selection (Subplan 1)**: Get 2–3 quotes for irrigation sleeve (~30 ft) + head adjustment (8→6)
- [ ] **Contractor selection (Subplan 2)**: Get 2–3 quotes for mulch bed drip line (~970 sqft)
- [ ] **HOA approval**: Submit application before construction if required

### Potential Agent Tasks (Optimization Opportunities)

- [ ] Update **materials shopping list** (shopping_list.md) to reflect Plan 3 quantities
- [ ] Update **pioneer_quote_list.md** to reflect new mulch quantities (~7.6 cu yd vs. prior figure)
- [ ] Produce a **plant palette list** for the mulch bed (drought-tolerant, Zone 5b-6a, deer-resistant options for Colorado)
- [ ] Create a **contractor bid request template** for drip irrigation + downspout + irrigation sleeve
- [ ] Update the **SVG plan** (v12) to reflect Plan 3: remove East Corridor + East South Strip, retain east-wall concrete strip, expand mulch zone
- [ ] Produce a **seasonal maintenance calendar** for the new backyard
- [ ] Verify **HOA guidelines** and flag any permit requirements for staircase demolition

---

## 9. Conversation Key Decisions Log

This log records every confirmed design decision in chronological order, useful for resolving any future ambiguity.

```
[D01] Orientation: Plot plan UP = East (slightly south of true east). Confirmed.
[D02] Deck is INSIDE house footprint (not cantilevered). Size: 20×10 ft.
[D03] Staircase is cantilevered OUTSIDE east wall. It descends from deck NE corner southward.
      Staircase length = patio length = 20 ft. Width ≈ 4 ft.
[D04] No storage space under staircase.
[D05] Patio is DIRECTLY BELOW deck, same footprint (20×10 ft), fully within house rectangle.
[D06] South Pathway is existing concrete, retained as-is.
[D07] South Pathway runs only to X=192 (east wall staircase line) — does NOT continue east.
[D08] East wall concrete strip runs from staircase base (Y=385) to South Pathway (Y=530),
      same width as staircase (~4 ft), forms L-turn at SE corner.
[D09] Garden boxes (already 3 exist) are along NORTH fence, west of pear tree — not east fence.
[D10] Pear tree is at EAST side of garden boxes, in NE corner of backyard (near east + north fence).
[D11] Existing lawn has 2 irrigation pipes: W pipe near X=192, E pipe near X=462, both N–S.
      4 sprinkler heads each (8 total). Both enter from north patio extension zone.
[D12] Grass is maintained by irrigation system — design must preserve/adapt irrigation.
[D13] Lawn: ~10 ft gap from north fence (碎石带). ~6.5 ft gap from east fence (隔离带).
[D14] North patio extension: from existing patio north edge (Y=225) northward ~15 ft,
      width from existing patio west edge (X=80) to staircase east edge (X=192).
[D15] East corridor: east of staircase (X=192~224), connects north patio to south strip.
[D16] East south strip: same 4 ft width (X=192~224), connects from staircase base to South Pathway.
[D17] South Pathway extended east to X=224 to align with east south strip.
[D18] Arc cut (NOT straight line) from (192,225) to (224,257), ~45° angle.
      Upper-right triangle = lawn (green). Lower-left triangle = patio (gray).
[D19] Patio material: natural flagstone OR large concrete pavers — not yet decided.
[D20] Fire pit: PORTABLE/movable. Not built-in.
[D21] Lawn retention: 1/3 to 1/2 of original. ~870 sqft focused north.
[D22] East buffer strip (black mulch): EXISTING, retain as-is. No work needed.
[D23] Garden box expansion: CANCELLED. 3 existing boxes are sufficient.
[D24] North privacy planting: REMOVED from scope.
[D25] Mulch bed plant installation: REMOVED from scope (homeowner handles separately).
[D26] Pine tree: 1 tree, SE corner, near east fence close to south pathway.
[D27] Irrigation redesign: contractor. West pipe moves 4 ft east. 8→6 heads. Add drip line for mulch bed.
[D28] Downspout reroute: contractor. Underground PVC, 12 ft, pop-up emitter.
[D29] PLAN 3 CHANGE (May 2026): East Corridor (78 sqft, east of staircase) CANCELLED.
      East South Strip (72 sqft, staircase base to South Pathway) CANCELLED.
      North Patio Extension and seat wall RETAINED — still active.
[D30] Staircase is existing structure — retained as-is. Was never added as a new construction item.
[D31] PLAN 3 CHANGE (May 2026): East Corridor (X=192~224, Y=225~385) and East South Strip
      (X=192~224, Y=385~530) CANCELLED — these were eastward extensions beyond the staircase
      footprint into the existing grass and black mulch area.
      Staircase Base Strip (X=160~192, Y=385~530) is NOT cancelled — it stays in scope as
      paving to fill the rock-filled strip below the staircase (patio east edge to grass edge).
      §3 corrected: this strip is currently rock-filled, not concrete as originally documented.
[D32] Staircase Base Strip (X=160~192, Y=385~530, ~72 sqft) confirmed as active paving scope.
      Currently has decorative rocks — clear and pave to match North Patio Extension material.
[D33] Mulch bed north edge extended +5 ft (Y=385→345 in SVG). Mulch area grows from ~612 to ~800 sqft.
      Lawn south boundary moves correspondingly (lawn shrinks ~170 sqft to ~800 sqft).
[D34] Mulch bed north edge extended another +5 ft (Y=345→305 in SVG, +10 ft total from original).
      Mulch area now ~970 sqft. Lawn now ~625 sqft.
[D35] Paving material confirmed: Home Depot grey stone pavers (June 2026).
      Applies to both North Patio Extension (210 sqft) and Staircase Base Strip (72 sqft).
      Use concrete paver quantities and budget column (option B) for all future estimates.
```

---

## 10. File Index

| File | Description | Status |
|------|-------------|--------|
| `drawings/backyard_plan_v12.svg` | **Current SVG plan — Plan 3 layout** (North Patio + Staircase Base Strip, no East Corridor) | ✅ Current |
| `archive/backyard_plan_v11.svg` | Previous SVG — Plan 2 layout (superseded) | Archive |
| `drawings/plot plan current.jpg` | Hand-annotated plot plan: current state (green=grass, black=mulch, blue=concrete) | ✅ Reference |
| `drawings/plot plan plan2.jpg` | Hand-annotated plot plan: Plan 2 (red=proposed patio, orange=proposed mulch) | Archive |
| `drawings/plot plan plan3.jpg` | Hand-annotated plot plan: **Plan 3 — current active design** (red=delete zone) | ✅ Current |
| `backyard_construction_plan.docx` | Bilingual (ZH/EN) construction plan — needs update for Plan 3 | Needs update |
| `backyard_project.md` | This file — full project context for agent handoff | ✅ Current |
| `figures/picture2.jpg` | Overhead photo of backyard from deck | Reference |
| `backyard_plan.svg` through `backyard_plan_v10.svg` | Previous SVG versions — superseded | Archive |
| `backyard_interactive.jsx` | React interactive plan (v1, outdated layout) | Outdated |

---

## Appendix: Useful References

- **Douglas County setback codes**: https://www.douglas.co.us/planning/
- **HOA**: Contact developer for CC&Rs
- **Colorado 811 (utility locate)**: Call 811 or visit https://www.colorado811.org
- **USDA Plant Hardiness Zone**: Zone 5b-6a for Littleton, CO at 5,721 ft elevation
- **Denver Water conservation rebates**: https://www.denverwater.org/residential/rebates
- **Colorado State University Extension — Lawn care**: https://extension.colostate.edu/lawn-management/

---

*Document generated from conversation context. Last updated: May 2026.*
*For continuity: always load `backyard_plan_v11.svg` as the current visual reference and treat §1 Ground Truth Data as immutable unless new survey data is provided.*
