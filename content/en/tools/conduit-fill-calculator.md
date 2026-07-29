---
title: "Conduit Fill Calculator — NEC Chapter 9 / Annex C Online Tool"
description: "Free NEC conduit fill calculator. Enter wire type, AWG, and count — get minimum conduit trade size and fill % per NEC Chapter 9 Table 4 and Annex C. EMT, PVC, RMC, IMC."
categories:
  - "Electrical Tools"
  - "NEC Chapter 9"
  - "Conduit Sizing"
  - "Raceway Fill"

images:
  - "/images/tools/conduit-fill-calculator.svg"
tags:
  - "conduit fill calculator"
  - "NEC conduit fill"
  - "EMT fill"
  - "PVC conduit fill"
  - "Chapter 9 Table 4"
  - "Annex C"
  - "raceway fill"
  - "THHN conduit"
  - "wire conduit size"
keywords:
  - "conduit fill calculator"
  - "NEC conduit fill"
  - "EMT fill calculator"
  - "PVC conduit fill"
  - "Chapter 9 Table 4"
  - "Annex C"
  - "raceway fill"
  - "conduit fill chart"
  - "THHN wire conduit size"
  - "how many wires in 3/4 emt"
  - "mixed wire sizes in conduit"
  - "conduit fill for EV charger"
  - "conduit fill for solar PV"
layout: "page"
translationKey: "conduit_fill_calculator"
date: "2026-07-28T04:00:00+00:00"
draft: false
---

# Conduit Fill Calculator — NEC Chapter 9 / Annex C Online Tool

{{< conduit-fill-calculator >}}

## TL;DR

**Conduit fill** is the percentage of a conduit's internal cross-sectional area occupied by the conductors (wires) running through it. NEC (NFPA 70, the U.S. National Electrical Code) limits this fill to **40% for 3 or more conductors**, **53% for 2 conductors**, and **60% for 1 conductor or any nipple (short conduit segment) ≤ 24 inches in length** (per NEC Chapter 9 Note 1 and NEC 310.15(C)(3)).

This tool implements **NEC Chapter 9 Table 4** (conduit internal area) and **Chapter 9 Table 5** (wire outside diameter including insulation) for **5 conduit types** (EMT, PVC-40, PVC-80, RMC, IMC) and **5 wire types** (THHN/THWN-2, XHHW/XHHW-2, USE-2/RHH, NM-B, UF-B). Three calculator modes are available:

- **Mode A — Verify:** Pick conduit + trade size + wire + AWG + count → see fill % and compliance.
- **Mode B — Recommend:** Pick conduit + wire + AWG + count → get the smallest compliant trade size.
- **Mode C — Mixed:** Mix different AWG wire types in one conduit → see total fill.

All calculations run **client-side in your browser** — no upload, no signup, no server processing.

---

## What Is Conduit Fill?

### NEC 40% / 53% / 60% Fill Rule

Per NEC Chapter 9 Table 4 Note 1, conduit fill is calculated as:

```
fill % = total conductor area / conduit internal area × 100%
```

The maximum fill percentage depends on the number of current-carrying conductors (CCCs) sharing the conduit:

| Conductor count | Fill limit (NEC reference) |
|---|---|
| 1 conductor | 60% |
| 2 conductors | 53% |
| 3 or more | 40% |
| Nipple (≤ 24") | 60% (regardless of count) |

**Why these specific numbers?** Annex C Tables C.1 through C.12 are pre-calculated lookup tables that round down to ensure the worst-case wire OD fits in the worst-case conduit OD with the mandated margin. The 40% rule for 3+ conductors leaves room for heat dissipation (joule heating from I²R losses), pulling-room for the wire (especially on long runs with bends), and future cable replacement.

### Why It Matters

- **Heat dissipation:** Conductors generate heat proportional to I²R (current squared times resistance). Cramming them too tightly prevents heat from escaping, raising insulation temperature and accelerating aging.
- **Pulling friction:** The NEC-mandated 40% margin gives enough clearance for the wire to be pulled through long conduit runs and bends without damaging insulation.
- **Damage to insulation:** Overfilled conduits can chafe insulation against the conduit wall during thermal expansion/contraction cycles.

### Which Conductors Count

Per NEC 300.17 and 310.15(C) informational note, **the following count toward fill**:
- Phase / hot conductors
- Neutral conductor (unless it's the only neutral on the run and is derated per NEC 310.15(B)(5) — rare in practice)
- **Equipment grounding conductors (EGC)** — **always count** (this is a common mistake)

The following do **not** count:
- NM-B / UF-B cable sheath (the cable assembly is treated as a single entity in the tool — see Wire Types below)
- Conduit fittings, locknuts, and bushings

---

## Conduit Types (supported by tool)

### EMT (Electrical Metallic Tubing)

**Use:** Indoor dry environment, exposed runs, light commercial. Most common in US residential and light commercial work. Sizes 1/2" through 4"; NEC permits 1/2" trade size for branch circuits.

**Internal area** (NEC Chapter 9 Table 4 for 1/2" through 4"):
- 1/2": 0.304 in² (196 mm²)
- 3/4": 0.533 in² (344 mm²)
- 1": 0.864 in² (557 mm²)
- 1-1/4": 1.496 in² (965 mm²)
- 1-1/2": 2.036 in² (1314 mm²)
- 2": 3.356 in² (2165 mm²)
- 2-1/2": 5.858 in² (3780 mm²)
- 3": 8.846 in² (5707 mm²)
- 4": 14.754 in² (9520 mm²)

### PVC Schedule 40 / 80

**Use:** Outdoor, underground, corrosive environments. PVC-80 (heavier wall) is used in areas subject to physical damage. Internal area is 5-7% smaller than EMT at the same trade size.

### RMC (Rigid Metal Conduit) / IMC (Intermediate Metal Conduit)

**Use:** Heavy-duty indoor/outdoor, exposed runs, hazardous locations. RMC is the heaviest; IMC is the lighter "middle-ground" alternative. Both have slightly smaller internal area than EMT due to thicker walls.

### Flex / LFMC

Currently not implemented in the tool. Use Mode A with custom OD if you have specific manufacturer data.

---

## Wire Types (with insulation OD)

The calculator includes NEC Chapter 9 Table 5 values for:

### THHN / THWN-2

**Most common building wire in North America.** Thermoplastic insulation rated 90°C in dry locations (THHN) and 75°C in wet (THWN-2). Typical OD ranges from 0.111 in (14 AWG) to 0.995 in (500 kcmil).

### XHHW / XHHW-2

**Cross-linked polyethylene insulation**, rated 90°C wet and dry. Slightly larger OD than THHN at the same gauge due to thicker insulation wall, but better thermal performance. Common in feeder runs.

### USE-2 / RHH / RHW

**Underground Service Entrance** cable. Designed for direct burial and outdoor exposure. OD typically larger than building wires of the same gauge. Used for solar PV DC circuits, service entrance, and outdoor feeders.

### NM-B / UF-B (cable form)

**Non-metallic sheathed cable** (Romex® is a brand name). NM-B for indoor dry; UF-B for direct burial or outdoor. **Note:** For these cable types, the calculator treats the entire cable as a single entity (cable overall OD including the sheath), not individual conductors inside the cable. So "Number of Conductors" actually means "Number of Cables" for NM-B / UF-B.

### Custom OD (free input)

Use this if your wire type isn't listed (mineral insulated MI, Teflon, etc.). Enter the manufacturer-specified OD in inches.

---

## How to Use the Calculator

### Mode A — Verify

You already know the conduit and wire spec; you want to confirm fill stays within limits.

1. Select **Conduit Type** (EMT, PVC-40, etc.) and **Trade Size** (1/2", 3/4", etc.).
2. Select **Wire Type** and **AWG / kcmil**.
3. Enter **Number of Conductors** — include all current-carrying conductors **plus the equipment grounding conductor**.
4. Tick **Nipple (≤ 24")** if the run is a short connecting segment (≤ 24 inches between boxes) — the limit becomes 60%.
5. Click **Calculate**.

The result card shows: conduit internal area, per-conductor area, total wire area, fill %, applicable NEC limit, and compliance badge.

### Mode B — Recommend

You have a wire spec and conductor count; you want the smallest compliant conduit.

1. Select **Conduit Type**, **Wire Type**, **AWG**, and **Number of Conductors**.
2. Tick **Nipple (≤ 24")** if applicable.
3. Click **Recommend**.

The tool iterates trade sizes from smallest to largest and shows the smallest one that stays under the limit, plus the fill % at that size.

### Mode C — Mixed

Different gauges or types in the same conduit (typical for branch circuits mixing lighting and signal).

1. Select **Conduit Type** and tick the nipple checkbox if applicable.
2. The form starts with one wire row — click **+ Add Wire Group** to add more.
3. For each row, select **Wire Type**, **AWG**, and **Count**.
4. Click **Calculate Mixed Fill**.

The tool computes the sum of (π/4 × OD² × count) across all rows, divides by the conduit's smallest trade size that fits, and reports the result.

### Presets: EV Charger / Solar PV / Garage 240V

Click a preset chip to automatically fill the Mode C form with a real-world configuration:

- **EV Charger (NEMA 14-50):** 2 × 6 AWG + 2 × 10 AWG THHN/THWN-2 in EMT (2 hot + ground + neutral).
- **Solar PV Combiner:** 4 × 10 AWG USE-2 in EMT (PV string conductors in a rooftop combiner run).
- **Garage 240V Outlet:** 2 × 6 AWG + 1 × 10 AWG + 1 × 12 AWG THHN/THWN-2 in PVC-40 (sub-panel feeder in residential garage).

---

## Worked Examples (5 verified + 1 Solar PV)

> Quality gate: every example below passes **two independent calculations** — (1) the tool's algorithm, and (2) a manual formula using NEC Chapter 9 Tables 4 and 5. If the numbers ever disagree, **the tool is wrong**, not the manual.

### Example 1 — 3 × 12 AWG THHN in 1/2" EMT (typical residential branch)

**Inputs:** Conduit = EMT 1/2"; Wire = THHN 12 AWG; Count = 3 (hot + neutral + EGC).

**Calculation (per NEC Chapter 9 Tables 4 & 5):**
- 12 AWG THHN OD = 0.130 in → area per conductor = π/4 × 0.130² = 0.01327 in²
- 1/2" EMT internal area = 0.304 in²
- Total wire area = 3 × 0.01327 = 0.03982 in²
- Fill % = 0.03982 / 0.304 = **13.10%**
- Limit (3+ conductors) = 40%
- Compliance: ✓ **Well under 40% — this is the most common 120 V receptacle circuit in North America.**

### Example 2 — Common Configuration: 9 × 12 AWG THHN in 3/4" EMT

**Inputs:** Conduit = EMT 3/4"; Wire = THHN 12 AWG; Count = 9 (multiple branch circuits bundled).

**Calculation:**
- 12 AWG THHN area = 0.01327 in² per conductor (same as Example 1)
- 3/4" EMT internal area = 0.533 in²
- Total wire area = 9 × 0.01327 = 0.11943 in²
- Fill % = 0.11943 / 0.533 = **22.40%**
- Limit (9 conductors) = 40%
- Compliance: ✓ **Well within limits, typical multi-circuit run.** Annex C Table C.1 maximum for 12 AWG THHN in 3/4" EMT = **16 wires** (the 3/4" EMT can accept up to 16 wires of this size before bumping to 1" EMT). This configuration uses 9 wires at 22.4% — comfortable margin for future circuit additions.

### Example 2b — Critical Annex C Sanity Check: 16 × 12 AWG THHN in 3/4" EMT

**Inputs:** Conduit = EMT 3/4"; Wire = THHN 12 AWG; Count = 16 (NEC Annex C Table C.1 maximum for this combination).

**Calculation:**
- 12 AWG THHN area = 0.01327 in² per conductor (same as Example 1 & 2)
- 3/4" EMT internal area = 0.533 in²
- Total wire area = 16 × 0.01327 = 0.21232 in²
- Fill % = 0.21232 / 0.533 = **39.83%**
- Limit (16 conductors) = 40%
- Compliance: ✓ **Just under the 40% limit — this is the Annex C Table C.1 boundary case (AV-2 directive: 3/4" EMT × 12 AWG THHN = 16 wires).** Pushing to 17 wires in the same 3/4" EMT would exceed 40% (17 × 0.01327 / 0.533 = **42.32%**, ✗ over limit) — at that point size up to 1" EMT.

This pairs with Example 2 (9 wires in 3/4" EMT, 22.40% — comfortable margin) to bracket the Annex C Table C.1 boundary for 12 AWG THHN: Example 2 sits comfortably inside the limit; Example 2b sits exactly at the boundary.

### Example 3 — 4 × 6 AWG XHHW in 3/4" PVC-40 → upgrade to 1" PVC-40

**Inputs:** Conduit = PVC-40 3/4"; Wire = XHHW 6 AWG; Count = 4 (sub-panel feeder or 50 A circuit).

**Calculation:**
- 6 AWG XHHW OD = 0.289 in → area per conductor = π/4 × 0.289² = 0.06560 in²
- 3/4" PVC-40 internal area = 0.508 in²
- Total wire area = 4 × 0.06560 = 0.26239 in²
- Fill % = 0.26239 / 0.508 = **51.65%**
- Limit (4 conductors) = 40%
- Compliance: ✗ **Exceeds 40% limit by 11.65 percentage points.**

**Upgrade path — retry with 1" PVC-40:**
- 1" PVC-40 internal area = 0.832 in²
- Fill % = 0.26239 / 0.832 = **31.54%**
- Compliance: ✓ Compliant, with 8.46 percentage points of margin.

**Recommendation:** Use 1" PVC-40 (smallest compliant upgrade). Skip 1-1/4" unless future expansion is planned.

### Example 4 — Mixed Sizes: 4 × 12 AWG + 2 × 14 AWG THHN in 1" EMT

**Inputs:** Conduit = EMT 1"; Group 1 = THHN 12 AWG × 4; Group 2 = THHN 14 AWG × 2 (signal wires bundled with branch circuits).

**Calculation:**
- 12 AWG THHN area = 0.01327 in² (per Example 1)
- 14 AWG THHN OD = 0.111 in → area per conductor = π/4 × 0.111² = 0.00968 in²
- Total wire area = 4 × 0.01327 + 2 × 0.00968 = 0.05309 + 0.01935 = 0.07244 in²
- 1" EMT internal area = 0.864 in²
- Fill % = 0.07244 / 0.864 = **8.38%**
- Limit (6 conductors) = 40%
- Compliance: ✓ **Massive margin; 3/4" EMT also works (fill = 13.62%) — choose by economics.**

Annex C cannot directly look up mixed sizes — the calculator sums per-conductor areas first (per NEC Chapter 9 Table 4).

### Example 5 — EV Charger (NEMA 14-50): 4 wires in 3/4" EMT

**Inputs:** Conduit = EMT 3/4"; Wire = THHN/THWN-2 (wet-rated for outdoor EV install); Group 1 = 6 AWG × 2 (L1 + L2); Group 2 = 10 AWG × 1 (EGC); Group 3 = 10 AWG × 1 (neutral).

**Calculation (with neutral):**
- 6 AWG THHN/THWN-2 OD = 0.268 in → area = π/4 × 0.268² = 0.05641 in²
- 10 AWG THHN OD = 0.164 in → area = π/4 × 0.164² = 0.02112 in²
- Total area = 2 × 0.05641 + 2 × 0.02112 = 0.11282 + 0.04224 = 0.15506 in²
- 3/4" EMT area = 0.533 in²
- Fill % = 0.15506 / 0.533 = **29.09%**
- Limit (4 conductors) = 40%
- Compliance: ✓ Well under 40%. (Without neutral: 25.13% fill, also compliant; common 240 V EVSE without neutral omits the neutral wire — this calculator's EV preset defaults to 4 wires.)

**Common mistake:** Forgetting to count the equipment grounding conductor in fill (NEC 300.17).

### Example 6 — Solar PV Combiner: 4 × 10 AWG USE-2 in 1" EMT

**Inputs:** Conduit = EMT 1"; Wire = USE-2 10 AWG; Count = 4 (four PV string conductors run from combiner to inverter on a rooftop installation).

**Calculation:**
- 10 AWG USE-2 OD = 0.193 in → area per conductor = π/4 × 0.193² = 0.02926 in²
- Total wire area = 4 × 0.02926 = 0.11704 in²
- 1" EMT internal area = 0.864 in²
- Fill % = 0.11704 / 0.864 = **13.55%** (precise: 13.547%)
- Limit (4 conductors) = 40%
- Compliance: ✓ **Comfortable margin, allows for 1-2 future strings without re-pulling.** USE-2 is the typical insulation for PV DC circuits in exposed outdoor conduit (NEC 690.31).

The tool's Solar PV preset auto-fills these four conductors in Mode C.

---

## NEC Reference — Chapter 9 & Annex C

### Chapter 9 Table 4 — Conduit Internal Area

This table gives the internal cross-sectional area (in²) of each conduit type at each trade size. The tool embeds the full NFPA 70-2023 table for EMT, PVC-40, PVC-80, RMC, and IMC (9 trade sizes each).

### Chapter 9 Table 5 — Wire OD Including Insulation

This table gives the overall OD (in) of each wire type / AWG combination **including insulation**. NEC requires that the *insulated* OD be used for fill calculations (not the bare copper OD).

### Annex C Tables C.1 through C.12

These tables are pre-calculated number-of-conductors lookups derived from the formula `⌊limit × A_conduit / A_wire⌋`. For single wire types, Annex C gives a quick answer without calculation. For mixed wire types or custom ODs, the formula is required (Mode C).

### Notes on NEC 2020 vs 2023

NEC Chapter 9 Table 4 and Table 5 wire OD values have remained stable across recent editions (2020, 2023). The Annex C tables round down to whole-conductor counts. Where the formula gives e.g. 16.06 wires maximum, Annex C lists 16 (not 17). The calculator's Mode A / Mode B / Mode C use the raw formula for true fill %, then compare against the rule — this is more accurate than Annex C rounding at the boundary.

---

## Frequently Asked Questions (FAQ)

### What is the 40% conduit fill rule?

Per NEC Chapter 9 Table 4 and Note 1, conduit fill is limited by conductor count: **60% for 1 conductor, 53% for 2 conductors, 40% for 3 or more**. Fill % is the total cross-sectional area of all conductors (including equipment grounding conductors) divided by the conduit's internal cross-sectional area (NEC Chapter 9 Table 4). For nipples 24 inches or less in length, **NEC 310.15(C)(3)** allows 60% fill regardless of conductor count.

### How many 12 AWG THHN wires can fit in 3/4" EMT?

Per the formula `⌊0.40 × 0.533 / 0.01327⌋ = 16`, the **Annex C Table C.1 maximum is 16 wires of 12 AWG THHN in 3/4" EMT**. Example with 9 wires: 9 × π/4 × 0.130² = 0.1194 in² total wire area. Conduit internal area for 3/4" EMT = 0.533 in². Fill % = 0.1194 / 0.533 = **22.40%** — well below the 40% limit for 3+ conductors. To push to the maximum (16 wires), fill becomes 16 × 0.01327 / 0.533 = **39.83%** (just under the limit). Once you exceed 16 wires, switch to 1" EMT (internal area 0.864 in², fill drops to 24.55% at 17 wires).

### Do I count the ground wire in conduit fill?

**Yes.** Per NEC 300.17 and the informational note to 310.15(C), equipment grounding conductors (EGC) and bonding conductors count toward fill. The only exception is an EGC that runs unbroken through the conduit (and is correctly sized per NEC 250.122) — but even those occupy physical space and must be counted. Typical sizes: 10 AWG bare copper for 60 A circuits, 8 AWG for 100 A, 6 AWG for 200 A.

### What is the difference between NEC Chapter 9 Table 4 and Annex C?

**Chapter 9 Table 4** gives the internal cross-sectional area (in²) of each conduit type by trade size. **Annex C** (Tables C.1 through C.12) provides pre-calculated number-of-conductors lookups by wire type and AWG. Annex C values are derived from Chapter 9 Tables 4 and 5 via the formula `⌊limit × A_conduit / A_wire⌋` (rounded down). Use Table 4 for mixed wire sizes or custom ODs (Mode C); use Annex C for single-wire-type quick lookup.

### Can I mix wire sizes in one conduit?

**Yes**, as long as total fill does not exceed 40% (or 53% for 2 conductors, 60% for 1 or nipple). Calculate the sum of (π/4 × OD²) for each conductor × count, divided by conduit internal area (Chapter 9 Table 4). Example: 4 × 12 AWG THHN (area 0.01327 in² each) + 2 × 14 AWG THHN (area 0.00968 in² each) in 1" EMT (area 0.864 in²): fill = (4 × 0.01327 + 2 × 0.00968) / 0.864 = 0.07244 / 0.864 = **8.38%** — compliant with a 31.6 percentage-point margin.

### What about nipples 24 inches or shorter — different fill rule?

**Yes.** Per NEC 310.15(C)(3), conduit nipples (short raceway segments) **24 inches or less in length** between enclosures are permitted to have fill up to **60% regardless of conductor count**. This recognizes that pulling heat buildup is less of a concern in short segments (heat conducts to both end enclosures). Common application: a 6-inch nipple between two adjacent junction boxes or between a panelboard and a metering trough. Count the equipment grounding conductor; the 60% rule is universal for nipples.

### Is conduit body (LB, Condulet) fill calculated the same way?

**Yes,** but with volumes instead of areas. NEC 314.16 and Chapter 9 Table 4 apply to conduit bodies (also called condulets, LBs, LLs, pull boxes). Calculate volume: (π/4 × OD²) for each conductor, summed, divided by conduit body internal volume (from manufacturer specs). The 40% / 53% / 60% fill rules are the same as for the conduit itself. The tool currently focuses on straight conduit runs; for conduit bodies, verify against the specific manufacturer's volume table (e.g. Crouse-Hinds, O-Z/Gedney, Hubbell).

### Is PVC-40 fill calculation different from EMT?

Calculation method is **identical** — same NEC Chapter 9 Table 4 fill limits (40% / 53% / 60%), same Table 5 wire OD values. The only difference: PVC-40 has slightly **smaller internal area** than EMT at the same trade size (e.g. 3/4" PVC-40 = 0.508 in² vs 3/4" EMT = 0.533 in² — 4.7% smaller wall thickness difference). So PVC-40 accommodates 1-2 fewer conductors than EMT at the same trade size. PVC-80 is even tighter (0.456 in² for 3/4"). Always verify the conduit type on the print before sizing.

---

## Related Tools

- **[Wire Size Calculator](/tools/wire-size-calculator/)** — start here: amps → wire gauge, then come back for conduit sizing.
- **[Cable Current-Carrying Capacity Lookup](/tools/cable-current-carrying-capacity-lookup/)** — verify ampacity after temperature / grouping derating before picking conduit.
- **[Circuit Breaker Sizing Calculator](/tools/circuit-breaker-sizing-calculator/)** — pair the OCPD with the conductor per NEC 240 / 110.14(C).
- **[Transformer Capacity Selection](/tools/transformer-capacity-selection/)** — kVA → secondary FLA for large feeders.
- **[Voltage Drop Calculator](/tools/voltage-drop-calculator/)** — long-distance run? Verify V_drop ≤ 3% (NEC 210.19(A) Informational Note 4) before finalizing conduit.
- **[Ground Resistance & Short-Circuit Calculator](/tools/ground-resistance-short-circuit-calculator/)** — ground electrode resistance + available fault current for EGC sizing.

---

## Disclaimer

**Reference only** — always verify with the current adopted **NEC** edition and your local **Authority Having Jurisdiction (AHJ)**. This tool does not replace professional engineering judgment or licensed electrician review. Final design must be reviewed and stamped by a registered professional engineer or performed by a licensed electrician where required by local regulations.

**Data sources:** NEC Chapter 9 Tables 4 and 5 are from NFPA 70-2023 (the latest published edition at the time of writing; values have remained stable across NEC 2020 and NEC 2023 for the conduit types and wire types listed). Annex C Table C.1 maximum conductor counts are derived from the formula (⌊limit × A_conduit / A_wire⌋) — verify against the printed NEC edition you are working with for borderline sizing decisions.

---

<!-- JSON-LD: WebApplication -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "Conduit Fill Calculator",
  "alternateName": "NEC Conduit Fill Calculator",
  "description": "Free NEC-aware conduit fill calculator. Enter wire type, AWG, and count — get minimum conduit trade size and fill % per NEC Chapter 9 Table 4 and Annex C. Supports EMT, PVC-40, PVC-80, RMC, IMC. Client-side only — no signup, no upload.",
  "url": "https://elec.webpenson.com/tools/conduit-fill-calculator/",
  "applicationCategory": "EngineeringApplication",
  "applicationSubCategory": "ElectricalDesignTool",
  "operatingSystem": "Any (Web Browser)",
  "inLanguage": "en-US",
  "browserRequirements": "Requires JavaScript. Requires HTML5.",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  },
  "author": {
    "@type": "Organization",
    "name": "elec.webpenson.com",
    "url": "https://elec.webpenson.com/"
  },
  "keywords": "conduit fill calculator,NEC conduit fill,EMT fill,PVC conduit fill,Chapter 9 Table 4,Annex C,raceway fill,wire conduit size,THHN conduit"
}
</script>

<!-- JSON-LD: FAQPage -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is the 40% conduit fill rule?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Per NEC Chapter 9 Table 4 and Note 1, conduit fill is limited by conductor count: 60% for 1 conductor, 53% for 2 conductors, 40% for 3 or more. Fill % is the total cross-sectional area of all conductors (including equipment grounding conductors) divided by the conduit's internal cross-sectional area (NEC Chapter 9 Table 4). For nipples 24 inches or less in length, NEC 310.15(C)(3) allows 60% fill regardless of conductor count."
      }
    },
    {
      "@type": "Question",
      "name": "How many 12 AWG THHN wires can fit in 3/4 inch EMT?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Per the formula floor(0.40 × 0.533 / 0.01327) = 16, the Annex C Table C.1 maximum is 16 wires of 12 AWG THHN in 3/4 inch EMT. Example with 9 wires: 9 × π/4 × 0.130² = 0.1194 in² total wire area. Conduit internal area for 3/4 inch EMT = 0.533 in². Fill % = 0.1194 / 0.533 = 22.40% — well below the 40% limit for 3+ conductors. To push to the maximum (16 wires), fill becomes 16 × 0.01327 / 0.533 = 39.83%. Once you exceed 16 wires, switch to 1 inch EMT (internal area 0.864 in², fill drops to 24.55% at 17 wires)."
      }
    },
    {
      "@type": "Question",
      "name": "Do I count the ground wire in conduit fill?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Per NEC 300.17 and 310.15(C) informational note, equipment grounding conductors (EGC) and bonding conductors count as conductors for fill calculation. Typical sizes: 10 AWG bare copper for 60 A circuits, 8 AWG for 100 A, 6 AWG for 200 A. The only exception is an EGC that runs unbroken through the conduit (NEC 250.122 sizing) — but even those occupy physical space and must be counted."
      }
    },
    {
      "@type": "Question",
      "name": "What is the difference between NEC Chapter 9 Table 4 and Annex C?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Chapter 9 Table 4 gives the internal cross-sectional area of each conduit type (EMT, PVC-40, PVC-80, RMC, IMC) by trade size. Annex C (Tables C.1 through C.12) provides pre-calculated number-of-conductors lookups by wire type and size. Annex C values are derived from Table 4 divided by Table 5 wire areas via the formula floor(limit × A_conduit / A_wire), rounded down. Use Table 4 for mixed wire sizes (custom calculation), Annex C for quick lookup of single wire types."
      }
    },
    {
      "@type": "Question",
      "name": "Can I mix wire sizes in one conduit?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, as long as total fill does not exceed 40% (or 53% for 2 conductors, 60% for 1 or nipple). Calculate: sum of (π/4 × OD²) for each conductor × count, divided by conduit internal area (Chapter 9 Table 4). Example: 4 × 12 AWG THHN (OD 0.130 in, area 0.01327 in² each) + 2 × 14 AWG THHN (OD 0.111 in, area 0.00968 in² each) in 1 inch EMT (area 0.864 in²): fill = (4 × 0.01327 + 2 × 0.00968) / 0.864 = 8.38% — compliant with large margin."
      }
    },
    {
      "@type": "Question",
      "name": "What about nipples 24 inches or shorter — different fill rule?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes. Per NEC 310.15(C)(3), conduit nipples (short raceway segments) 24 inches or less in length between enclosures are permitted to have fill up to 60% regardless of conductor count. This recognizes that pulling heat buildup is less of a concern in short segments. Common application: a 6-inch nipple between two adjacent junction boxes or panelboards. Always count the equipment grounding conductor; the 60% rule is universal for nipples."
      }
    },
    {
      "@type": "Question",
      "name": "Is conduit body (LB, Condulet) fill calculated the same way?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, but with volumes instead of areas. NEC 314.16 and Chapter 9 Table 4 apply to conduit bodies (also called condulets, LBs, pull boxes). Calculate volume: (π/4 × OD²) for each conductor, summed, divided by conduit body internal volume (from manufacturer specs). The 40% / 53% / 60% fill rules are the same as for the conduit itself. The tool currently focuses on straight conduit runs; for conduit bodies, verify against the specific manufacturer's volume table (e.g. Crouse-Hinds, O-Z/Gedney)."
      }
    },
    {
      "@type": "Question",
      "name": "Is PVC-40 fill calculation different from EMT?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Calculation method is identical — same Chapter 9 Table 4 fill limits (40% / 53% / 60%), same Table 5 wire OD values. The only difference: PVC-40 has slightly smaller internal area than EMT at the same trade size (e.g. 3/4 inch PVC-40 = 0.508 in² vs 3/4 inch EMT = 0.533 in² — 4.7% smaller). So PVC-40 accommodates 1-2 fewer conductors than EMT at the same trade size. PVC-80 is even tighter (0.456 in² for 3/4 inch). Always verify PVC type on the print before sizing."
      }
    }
  ]
}
</script>

<!-- JSON-LD: HowTo -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to Calculate Conduit Fill per NEC Chapter 9",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "Pick the conduit type and trade size (or wire spec)",
      "text": "Select conduit type (EMT, PVC-40, PVC-80, RMC, IMC) and trade size (1/2 inch to 4 inch), OR start from Mode B by picking wire type (THHN, XHHW, USE-2, NM-B, UF-B, or Custom OD) and AWG/kcmil plus conductor count."
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "Enter conductor count and check nipple flag if applicable",
      "text": "Enter the number of current-carrying conductors plus any equipment grounding conductors (ground counts toward fill per NEC 300.17). If the conduit run is a nipple 24 inches or shorter, tick the nipple checkbox to switch fill limit from 40% to 60% (NEC 310.15(C)(3))."
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "Read the result card",
      "text": "The result card shows: (a) conduit internal area (in²) from Chapter 9 Table 4, (b) per-conductor cross-section from Table 5, (c) total wire area, (d) fill percentage, (e) compliance badge (compliant or exceeds limit). For Mode B (recommend), the smallest compliant trade size is highlighted. For Mode C (mixed), the total area sum is compared against each trade size."
    }
  ]
}
</script>

<!-- JSON-LD: BreadcrumbList -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://elec.webpenson.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Tools",
      "item": "https://elec.webpenson.com/tools/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Conduit Fill Calculator",
      "item": "https://elec.webpenson.com/tools/conduit-fill-calculator/"
    }
  ]
}
</script>
