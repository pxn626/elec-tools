---
title: "Cable Current-Carrying Capacity Lookup — NEC 310.15 / Table 310.16 Online Reference Tool"
description: "Online cable ampacity lookup tool aligned with NEC 310.15 and Table 310.16 (formerly 310.16), the 75°C / 90°C ampacity columns for THHN / THWN-2 / XHHW-2 / USE-2 and other common conductor types. Covers 5 installation methods: free-air, conduit, cable tray, direct burial, and duct. Applies NEC 310.15(A)(2) ambient baseline (30°C), NEC 310.15(B)(2)(a) temperature correction, and NEC 310.15(C)(1) more-than-three-conductors adjustment. For NEC PE-stamped design, AHJ inspection, and licensed electrician field use."
categories:
  - "Electrical Tools"
  - "Cable & Installation"
  - "Engineering Quick Reference"


images:
  - "/images/tools/cable-current-carrying-capacity-lookup.svg"
tags:
  - "cable ampacity"
  - "current carrying capacity"
  - "NEC 310.15"
  - "Table 310.16"
  - "THHN ampacity"
  - "conduit installation"
  - "cable tray"
  - "derating factor"
keywords:
  - "cable ampacity lookup"
  - "cable sizing"
  - "NEC 310.15"
  - "Table 310.16"
  - "THHN ampacity"
  - "conduit installation"
  - "cable tray"
  - "ampacity derating"
layout: "page"
translationKey: "cable_current_carrying_capacity_lookup"
date: "2026-07-18T21:05:00+00:00"
draft: true
---

{{< cable-current-carrying-capacity-lookup >}}

# Cable Current-Carrying Capacity Lookup — NEC Table 310.16 Online Reference

## Introduction

**Cable current-carrying capacity lookup** (ampacity lookup) is a daily task for licensed electricians, PE-stamped designers, and AHJ (Authority Having Jurisdiction) inspectors. The traditional approach involves flipping through NEC 310.15 and Chapter 9 of NFPA 70 — cross-referencing wire size (AWG / kcmil), insulation temperature rating (60°C / 75°C / 90°C), installation method, ambient temperature, more than three current-carrying conductors, and altitude. This is inefficient and error-prone. This tool encapsulates the base ampacity from NEC Table 310.15(B)(16) (formerly 310.16) and the NEC correction framework (temperature adjustment per 310.15(B)(2)(a), more-than-three adjustment per 310.15(C)(1)) into a web form. Enter your parameters and get the corrected ampacity with factor breakdowns instantly. Suitable for stamped design calculations, on-site installation verification, and AHJ submittal review — say goodbye to manual table-flipping.

**Cross-reference for designers working on Chinese mainland projects:** the Chinese national standard GB 50217-2018 *Code for Design of Cables of Electric Engineering* covers a similar correction-factor framework using metric mm² and a 25°C ambient baseline. Where the two standards differ in temperature baseline (NEC 30°C vs GB 25°C) and conductor table sources, this tool follows the NEC convention.

---

## Tool Features — 5 Installation Methods

### Free-Air / Surface Mounted

**Applicable scenarios**: Exposed cable tray, wall mounting, outdoor架空支架 (overhead bracket). **Thermal conditions**: Natural air convection is good; **base factor K_s = 1.0**. **Typical users**: Factory workshop distribution mains, low-voltage cabinet feeders, ventilated cable trench sections.

```
Input: Conductor material / Cable type / Cross-section / Ambient temperature / Parallel circuits / Sun exposure / Altitude
Output: I_0 (base) / I_z (corrected) / K_θ / K_s / K_p / K_h / Compliance notes
```

### Conduit / Conduit-in-Structure

**Applicable scenarios**: Cables inside PVC conduit / galvanized steel conduit, utility shafts, slab concealed installation. **Thermal conditions**: No airflow between conduit wall and cables; **K_s typically 0.75–0.85** (varies significantly with number of conductors; 1-core vs 3-core differs notably). **Typical users**: Building electrical, indoor distribution, utility shafts, fire mains.

```
Input: Conductor material / Cable type / Cross-section / Ambient temperature / Conduit material / Conductors per conduit / Parallel circuits / Altitude
Output: I_0 / I_z / K_θ / K_s / K_p / K_h / Compliance notes
```

### Cable Tray

**Applicable scenarios**: Ladder tray, perforated tray, solid-bottom tray, cable trough tray. **Thermal conditions**: Tray is open, intermediate between free-air and conduit; perforated/solid-bottom slightly lower than ladder. **Typical users**: Factory distribution, server room vertical shafts, underground utility galleries, commercial complex mains.

```
Input: Conductor material / Cable type / Cross-section / Ambient temperature / Tray type / Parallel circuits / Altitude
Output: I_0 / I_z / K_θ / K_s / K_p / K_h / Compliance notes
```

### Direct Burial

**Applicable scenarios**: Outdoor cable trench direct burial, soil burial, cable gallery. **Thermal conditions**: Heat dissipation depends on soil thermal resistivity; **moist soil vs dry soil varies widely** (ρ_soil from 1.0 to 4.0 K·m/W; K_s can differ by 25%). **Typical users**: Municipal distribution, residential area feed-in, campus external lines, new-energy booster stations.

```
Input: Conductor material / Cable type / Cross-section / Soil temperature / Soil thermal resistivity / Parallel circuits / Altitude
Output: I_0 / I_z / K_θ / K_s / K_p / K_h / Compliance notes
```

### Duct / Protective Duct

**Applicable scenarios**: Cable protection ducts (MPP / fiberglass / galvanized steel), cable duct banks, cable tunnel pull-through sections. **Thermal conditions**: Similar to conduit, but duct diameter, length, and water-filling status have more pronounced effects. **Typical users**: Urban power grid, highway duct crossing, cable tunnel egress, airport power supply.

```
Input: Conductor material / Cable type / Cross-section / Soil temperature / Duct material / Parallel circuits / Altitude
Output: I_0 / I_z / K_θ / K_s / K_p / K_h / Compliance notes
```

---

## Preset Values — 7 Input Parameter Categories

### Conductor Material (2 options)

| Option | Code | Notes |
|---|---|---|
| Copper | Cu | NEC 14 AWG minimum copper for branch circuits (NEC 240.4(D)); preferred for power distribution |
| Aluminum | Al | NEC 12 AWG minimum aluminum for branch circuits (NEC 240.4(D)); cost-reduction for large feeders |

### Cable Type (7 NEC presets + custom)

| Name | NEC Type | Insulation | Applicable Scenarios | Chinese cross-reference |
|---|---|---|---|---|
| XLPE insulated, 90°C rated | XHHW-2 | XLPE 90°C | Indoor / tunnel / duct; most common in commercial feeders | YJV (cross-ref) |
| XLPE insulated, aluminum 90°C rated | XHHW-2 (Al) | XLPE 90°C | Large-feeder aluminum; cost reduction | YJLV (cross-ref) |
| XLPE insulated, armored 90°C rated | MC (metal-clad) / armored XHHW-2 | XLPE 90°C | Direct burial / outdoor; withstands mechanical stress | YJV22 (cross-ref) |
| PVC/nylon insulated, 90°C rated (commonly used at 75°C) | THHN / THWN-2 | PVC + nylon 90°C | Most common branch-circuit conductor; legacy PVC construction | VV (cross-ref) |
| PVC/nylon insulated, aluminum | THHN (Al) | PVC + nylon 90°C | Same; aluminum core | VLV (cross-ref) |
| Copper PVC/nylon flexible stranded | THHN (stranded) | PVC + nylon 90°C | Distribution panel wiring, flexible connections | BVR (cross-ref) |
| Aluminum PVC/nylon flexible stranded | THHN (Al stranded) | PVC + nylon 90°C | Same; aluminum core | BLVR (cross-ref) |
| Custom | (free input) | — | Engineer-defined type | — |

### Conductor Size (AWG / kcmil tiers, 14 AWG ~ 500 kcmil)

Common NEC sizes for power circuits: 14, 12, 10, 8, 6, 4, 2 AWG; 1/0, 2/0, 3/0, 4/0 AWG; 250, 300, 350, 400, 500 kcmil.

(For metric mm² cross-reference commonly used in Chinese design: 1.5 ~ 300 mm² maps approximately to NEC 14 AWG ~ 500 kcmil — not exact equivalency; consult NEC Chapter 9 Table 9 for actual cross-sectional area.)

### Installation Method (5 types)

Free-air / Conduit / Cable tray / Direct burial / Duct (see Tool Features section for details)

### Ambient Temperature (°C; common presets + custom)

- **30°C** (NEC 310.15(A)(2) ambient air baseline; reference for Table 310.16 values)
- **25°C** (Cool basement / utility shaft; below baseline; ampacity can be increased per 310.15(B)(2)(a))
- **35°C** (High-temperature workshop, summer attic)
- **40°C** (Dense cable tray, boiler room, rooftop)
- **Custom** (-20 ~ 60°C range; tool issues a warning if out of range)

### Current-Carrying Conductor Count (5 tiers)

| Number of CCs n | 1 | 2 | 3 | 4 | 6 |
|---|---|---|---|---|---

(Per NEC 310.15(C)(1), adjustment applies only when count **exceeds 3** current-carrying conductors; for > 6 CCs treat as 6 and prompt: "Recommend splitting to separate trays / raceways".)

### Sun Exposure / Shading (2 options)

- **Shaded**: Indoor / inside tray / conduit — no additional derating beyond NEC 310.15(C) rules
- **Exposed to sun on rooftop**: Outdoor direct sunlight — **important note**: rooftop ambient temperature may exceed 30°C baseline; verify with NEC 310.15(B)(2)(a) adjustment using ambient temperature measured at the conductor location, not the weather-station reading.

---

## Output Descriptions — I₀ / I_z / K Factors / Compliance Notes

### Base Ampacity I₀

Defined as: **Under standard NEC base conditions (copper or aluminum conductor, single circuit, 30°C ambient, not more than 3 current-carrying conductors in raceway/cable, free-air or per installation method), the maximum current the conductor is permitted to carry continuously** (unit: A).

**Data source**: NEC Table 310.15(B)(16) (formerly Table 310.16) for 75°C and 90°C rated conductors — the most commonly referenced column is 75°C because that matches most termination ratings (NEC 110.14(C)(1)). This tool's defaults to the 75°C column for branch-circuit sizing and switches to 90°C only when the terminations are explicitly 90°C rated. The tool does not expose the raw tables externally — I₀ is only presented as one output item.

### Corrected Ampacity I_z

Defined as: **The maximum current the conductor is permitted to carry continuously under actual engineering conditions, after applying the NEC correction framework** (unit: A).

**Engineering meaning**: During sizing verification, **the circuit's continuous load current I_L must satisfy I_L ≤ I_z** to meet NEC 310.15(B) requirements and Article 210 / 215 / 220 sizing rules. Otherwise, the conductor is subject to long-term overload — accelerated insulation aging, and in severe cases, fire.

### Temperature Correction Factor K_θ (NEC 310.15(B)(2)(a))

- **Source**: NEC Table 310.15(B)(2)(a) (formerly Table 310.15(B)(2)(a); 30°C ambient baseline)
- **Range**: **0.82 (40°C, 90°C-rated) ~ 1.12 (25°C, 90°C-rated)**; different values for 60°C / 75°C / 90°C rated conductors
- **Output**: Displays specific value + text note such as "THHN/XHHW 90°C insulation rated" / "TW 60°C insulation rated"
- **Formula**: `multiplier = √((θ_n - θ_a) / (θ_n - 30))` where θ_n is insulation rating and θ_a is ambient

### Installation Method Correction Factor K_s (NEC 310.15(C) / Annex B)

- **Source**: NEC 310.15(C)(1) — adjustment applies only when count of current-carrying conductors **exceeds 3**
- **Range**: **0.80 ~ 1.00** (for 4 ~ 9+ CCs)
  - 1.0 (≤ 3 CCs in raceway)
  - 0.80 (4 ~ 6 CCs)
  - 0.70 (7 ~ 9 CCs)
  - 0.70 (10 ~ 20 CCs; further derating may apply)
  - 0.60 (> 20 CCs; NEC Annex B reference)
- **Output**: Displays value + text description

### Current-Carrying Conductor Correction Factor K_p (same as K_s above)

- **Source**: NEC Table 310.15(C)(1) Adjustment Factors (more-than-three CCs adjustment)
- **Range**: **0.70 ~ 1.00**
  - 1.0 (≤ 3 CCs; no adjustment)
  - 0.88 (4 ~ 6 CCs)
  - 0.82 (7 ~ 9 CCs) — note: this is the NEC Table 310.15(C)(1) value, not the GB 50217 sequence
- **Output**: Displays value + CC count and raceway fill status

### Altitude Correction Factor K_h

- **Source**: NEC 310.15(D) and Annex B Table B.310.15(D)(2) (formerly referenced as Table 5.4.6 in older GB conventions)

| Altitude (ft) | ≤ 3300 | 5000 | 7000 | 9000 | 10000 |
|---|---|---|---|---|---|
| K_h | 1.00 | 0.96 | 0.91 | 0.87 | 0.85 |
| Altitude (m) | ≤ 1000 | 1500 | 2100 | 2700 | 3000 |

- **Output**: Displays value + altitude advisory
- **Engineering note**: Below 1000 m / 3300 ft, use 1.00; for higher altitudes, interpolate from the table; the tool also notes that NEC 310.14 explicitly requires multiplying the Table 310.16 ampacity by 0.96 once altitude exceeds 3300 ft (US) / 1000 m (metric).

### Compliance Notes

The tool does not issue binary pass/fail judgments, but provides descriptive guidance, for example:

- "Complies with NEC 310.15(B) ampacity selection rules"
- "Altitude > 1000 m (3300 ft) — apply NEC 310.15(D) correction"
- "Current-carrying conductors > 3 — NEC 310.15(C)(1) adjustment applies"
- "Ambient temperature close to insulation rating — verify 310.15(B)(2)(a) correction"
- "Cross-reference: in Chinese mainland projects, GB 50217-2018 applies; consult Chinese code separately"

## Chinese GB Standard Cross-Reference

The tool's NEC primary framework. For cross-reference:

- **GB 50217-2018** uses metric mm² (not AWG/kcmil) and a 25°C ambient baseline (vs NEC 30°C)
- **GB 50217 correction factor logic** matches NEC structurally: K_θ (temperature), K_s (installation), K_p (grouping), K_h (altitude)
- **GB 50217 Table C.0.1 ~ C.0.4** is functionally analogous to NEC Table 310.15(B)(16) but with metric mm² sizing
- For projects with Chinese-mainland applicability, consult GB 50217 directly — tables and clause numbers differ.

---

## Formula Details — I_z = I₀ × K_θ × K_s × K_p × K_h

### Core Formula

```
I_z = I_0 × K_θ × K_s × K_p × K_h
```

The four K factors multiply independently — **all coefficients ≤ 1** (all are 1.0 under base conditions). When the ambient temperature is below the base temperature (25°C), K_θ > 1.0, indicating that cooling conditions are better than base — a larger current is permitted. This is a physically meaningful interpretation recognized by both IEC and GB standards.

### Correction Factor Selection Key Points

| Factor | Meaning | Range | NEC Source |
|---|---|---|---|
| K_θ | Effect of ambient temperature deviation from NEC 30°C baseline | **0.82 ~ 1.12** (90°C-rated XLPE 25~40°C) | NEC Table 310.15(B)(2)(a) |
| K_s | Adjustment for > 3 current-carrying conductors (raceway/cable fill) | 0.70 ~ 1.00 | NEC Table 310.15(C)(1) |
| K_p | Same as K_s — NEC 310.15(C)(1) more-than-three CCs adjustment | 0.70 ~ 1.00 | NEC Table 310.15(C)(1) |
| K_h | Effect of high altitude / thin air on cooling | 0.85 ~ 1.00 (≤ 10000 ft) | NEC Table 310.15(D)(2) Annex B |

**Base temperature note:**

> This tool's K_θ strictly uses values from **NEC Table 310.15(B)(2)(a)** (30°C ambient baseline, 90°C-rated XLPE).
> GB 50217-2018 Table E.0.1 uses 25°C as base, resulting in 2–3% differences in values — **NEC takes precedence in this tool**.
> **Engineering significance**: Under the same conductor size and installation conditions, the I₀ given by GB 50217 is typically 2–3% more conservative than NEC at 30°C baseline — this tool follows NEC for North American AHJ-accepted design.

### Sizing Verification

```
I_L ≤ I_z             (For continuous load; NEC 210.20(A) / 215.2(A)(1) recommended)
or
I_L ≤ I_z / 0.80      (For continuous loads with NEC-defined 125% multiplier for combined loads)
```

Note: The 0.80 factor comes from NEC 210.20(A) continuous-load rule (breaker rating ≥ 125% of continuous load), which translates into checking I_L ≤ I_z / 0.80 ≈ 1.25 × I_L. **Not included in tool output**, only in the educational section.

---

## National Standard References

### NFPA 70 — National Electrical Code (NEC) 2023 / 2020

USA National Fire Protection Association standard, **NFPA 70 (NEC)**, current edition 2023 (with 2020 also commonly cited). Supervising body: NFPA. Contents relevant here: Chapter 3 (Wiring Methods), Article 310 (Conductors), Article 240 (Overcurrent Protection), Article 210 (Branch Circuits), Chapter 9 (Tables 1, 4, 5, 9). This tool's base ampacity follows NEC Table 310.15(B)(16) and the correction framework per NEC 310.15(B)(2)(a) / 310.15(C)(1) / 310.15(D).

Note: This tool is for engineering estimation only. Actual engineering design shall prevail with the locally-adopted NEC edition (AHJ determines which edition applies). Access: [NFPA Free Read-Only](https://www.nfpa.org/codes-and-standards/nfpa-70-standard-development/70){target="_blank" rel="nofollow noopener"}.

### IEC 60364-5-52 (cross-reference)

International Electrotechnical Commission **IEC 60364-5-52** *Low-voltage Electrical Installations — Part 5-52: Selection and Erection of Electrical Equipment — Wiring Systems*. Equivalent national standard in China: **GB/T 16895.15-2005**. The IEC framework is structurally similar to NEC 310.15 (temperature correction, grouping adjustment) but uses metric mm² and a 30°C ambient baseline that is conceptually identical to NEC 30°C baseline — values may differ by ±5% in some installation methods. For projects with cross-border applicability, cross-reference IEC 60364-5-52 / GB/T 16895.15.

### GB 50217-2018 (Chinese cross-reference)

**People's Republic of China National Standard, GB 50217-2018** *Code for Design of Cables of Electric Engineering*, published 2018-09-11, effective 2019-04-01. Supervising body: China Electricity Council. Used here only as cross-reference for projects where Chinese GB 50217 applies (e.g., export or dual-jurisdiction projects). Note: GB 50217 uses metric mm² and 25°C ambient baseline, while NEC uses AWG/kcmil and 30°C baseline — direct numerical equivalence is not 1:1.

Access: [National Standards Full-Text Public Query System](http://openstd.samr.gov.cn/){target="_blank" rel="nofollow noopener"} — Standardization Administration official portal.

### Other References

- **NEC Chapter 9 Table 5** — Conductor dimensions (OD) for THHN / THWN-2 / XHHW-2 / USE-2 / NM-B / UF-B
- **NEC Chapter 9 Table 4** — Conduit cross-sectional area (EMT / PVC-40 / PVC-80 / RMC / IMC / Flex)
- **NEC Chapter 9 Table 9** — DC resistance and AC resistance (75°C) for AWG / kcmil conductor sizing
- **NEC Annex C** — Number of conductors lookup tables (Annex C Tables C.1 ~ C.12)
- **NFPA 70 Article 210** — Branch Circuits (related sizing rules)
- **NFPA 70 Article 240** — Overcurrent Protection (cross-reference with NEC 310 sizing)

---

## Frequently Asked Questions (FAQ)

### What is cable current-carrying capacity?

Cable current-carrying capacity (ampacity) is the **maximum current a cable can carry continuously under specified conditions** (temperature, installation, grouping, altitude), in amperes (A). It is not a fixed value — it varies with installation conditions as a corrected result. During design, you must satisfy: **continuous load current I_L ≤ corrected ampacity I_z**; otherwise the cable will overheat, insulation will age prematurely, or in severe cases, cause fire. Different installation methods, ambient conditions, and cross-sections can result in ampacity differences exceeding 30% — therefore, engineering applications must calculate each correction factor per the formula, not guess.

### What is the difference between XHHW-2 and THHN cable ampacity?

For the same AWG/kcmil size, XHHW-2 (cross-linked polyethylene, 90°C rated) ampacity is **15% ~ 25% higher than THHN (PVC/nylon, 90°C rated but commonly limited to 75°C column for terminations)**. Reason: XLPE insulation is rated at 90°C, PVC/nylon THHN at 90°C rated but most equipment terminations are 75°C rated per NEC 110.14(C)(1)(a); the effective operating temperature limit is the lower of conductor and termination. **Selection recommendation**: NEC 110.14(C)(1) requires using the 75°C column of NEC Table 310.15(B)(16) when termination ratings are 75°C — most branch circuits and feeders use the 75°C column even when the conductor is 90°C rated. For higher rated applications (e.g., 90°C terminations on industrial feeders), the 90°C column may be used for ampacity calculation then adjusted to the termination rating. For the same 4/0 AWG copper conductor, XHHW-2 at 75°C column yields approximately 230 A free air, while THHN at 75°C yields approximately 230 A as well — both columns converge in larger sizes where termination is the limiting factor.

### Why does conduit fill / derating affect ampacity so much?

Conduit installation has reduced heat dissipation — air inside the conduit has limited circulation, and heat is conducted away through the conduit wall and adjacent conductors. **Per NEC 310.15(C)(1)**, when the count of current-carrying conductors (CCs) **exceeds 3**, an adjustment factor from NEC Table 310.15(C)(1) applies — typically 0.80 for 4–6 CCs, 0.70 for 7–9 CCs, dropping further for >9 CCs. The K_s value is NOT 1.0 in a typical conduit run with multiple conductors. **Actual difference**: For the same 6 AWG copper THHN conductor in free-air (per NEC Table 310.15(B)(16) 75°C column), ampacity is approximately **65 A**, while in a conduit with 4 current-carrying conductors, the adjusted ampacity is **65 × 0.80 = 52 A** — a **20% gap**. Larger CC counts produce larger derating; this is why NEC Chapter 9 Table 1 (Annex C) is consulted to verify conduit fill ≤ 40% before sizing ampacity.

### Why do multiple parallel cables need derating?

When multiple cables are installed touching each other, their heat mutually reinforces, raising the ambient temperature collectively — derating is required. Parallel 2 cables ≈ 0.88, 3 cables 0.82, 4 cables 0.77, 6 cables 0.73 (typical values, varies by installation method). **Engineering对策**: When there are many circuits, **splitting to separate trays, layers, or busbars** is more economical than cramming them into one tray — it retains heat dissipation space while facilitating future maintenance and expansion.

### How does altitude affect ampacity?

Higher altitude means thinner air, poorer heat dissipation. **NEC 310.15(D)** requires multiplying the Table 310.15(B)(16) ampacity by 0.96 once altitude exceeds 3300 ft (~1000 m). For higher altitudes, use **NEC Table 310.15(D)(2) Annex B** (non-linear table). Example: 5000 ft (~1500 m), K_h ≈ **0.96**; 7000 ft (~2100 m), K_h ≈ **0.91**; 10000 ft (~3000 m), K_h ≈ **0.85**. **Mountain-west US projects (Rocky Mountain states / Pacific Northwest) must check altitude**; plains projects may default to K_h = 1.00. Note that NEC Table 310.15(D)(2) is equivalent to IEC Table B.52.16 and GB 50217 Table 5.4.6 but is presented in ft — convert to metric when working internationally.

### How do cable ampacity and circuit breaker setting current match?

Strictly per **NEC 240.4(B)** (and 240.4(D) for small conductors), the circuit breaker's rated current must satisfy **I_n ≤ I_z** (equal or smaller — this is the hard constraint in NEC 240.4(B) for conductors rated 800 A or less). For continuous-load applications, NEC 210.20(A) and 215.3 require **breaker rating ≥ 125% of continuous load**, which translates into verifying **I_n ≥ 1.25 × I_L** or equivalently **I_L ≤ I_z / 0.80**. Example: Corrected ampacity 100 A with continuous load 80 A — set circuit breaker at 100 A (100 ≥ 1.25 × 80 = 100 ✓). For overcurrent protection coordination, short-circuit protection is a separate calculation: the breaker's **instantaneous trip setting** must clear cable short-circuit thermal stability — this is covered by the circuit breaker sizing tool.

### Which standard should I use — NEC, GB 50217, or IEC 60364?

**For US / North American projects, NEC (NFPA 70) is required** — most AHJ inspections reference the locally-adopted NEC edition. **For Chinese mainland projects, GB 50217 is preferred** for cable selection, GB 50054 for breaker coordination. **For international / export projects** (or where neither NEC nor GB is mandated), **IEC 60364-5-52** is more universally recognized — some Africa, Middle East, and Southeast Asia project bid documents directly cite IEC. The I₀ tables of NEC / GB / IEC differ minimally (±5%) when normalized to the same ambient baseline, but terminations and metric vs AWG units differ. **Key principle**: use one standard **consistently throughout** the project — do not mix GB for cable selection with NEC for breaker sizing in the same project. Mixing standards' correction formulas in one project creates audit / AHJ disputes.

### How is the temperature correction factor calculated?

Based on the conductor allowable operating temperature θ_n and the actual ambient temperature θ_a, values come from **NEC Table 310.15(B)(2)(a)** (30°C ambient baseline). Simplified formula (for understanding, not direct table lookup): `K_θ = √((θ_n - θ_a) / (θ_n - 30))`. Example: XHHW-2 (θ_n = 90), ambient 40°C → K_θ ≈ **0.91**; ambient 25°C → K_θ ≈ **1.08** (values per NEC Table 310.15(B)(2)(a)). PVC/nylon THHN (θ_n = 90) uses the same correction as XLPE; lower-temperature insulation like THW (θ_n = 75) uses the same formula but with faster derating. **The tool directly provides table values** — no manual calculation needed. Note: Chinese GB 50217 Table E.0.1 uses 25°C baseline instead of NEC 30°C baseline — when working with GB 50217 directly, recalculate K_θ using 25°C as the baseline (`K_θ = √((θ_n - θ_a) / (θ_n - 25))`).

---

## Disclaimer

**Important**: Ampacity data provided by this tool is based on **simplified calculations from NEC Table 310.15(B)(16) and the correction framework of NEC 310.15(B)(2)(a) / 310.15(C)(1) / 310.15(D)**, for **engineering estimation only**.

Actual engineering design must:

1. Use the latest published NEC edition adopted by the AHJ having jurisdiction as the authoritative source
2. Obtain a formal calculation sheet from a PE-stamped design professional or licensed electrical engineer
3. Special scenarios (hazardous areas, offshore wind power, marine, subway, hospital operating rooms) require additional NEC Chapter 5 / 6 references and possibly other NFPA standards

This tool **does not provide** automatic cable sizing recommendations and **does not replace** professional engineering judgment. This tool assumes no liability for any engineering incidents resulting from the use of this tool's data.

**For Chinese mainland projects**: GB 50217-2018 / GB 50054-2011 applies — consult these standards directly. The NEC framework is structurally equivalent but uses AWG/kcmil units and 30°C ambient baseline instead of metric mm² and 25°C baseline.

---

## Internal / External Links

**Related elec webpenson.com tools**:

- [EV Charger Power Calculator](/tools/charging-power-calculator/) — EV charger power (same electrical context)
- [Charging Time Calculator](/tools/charging-time-calculator/) — Charging time (same EV charger context)
- [Electricity Cost Calculator](/tools/electricity-cost-calculator/) — Electricity cost estimation
- [Three-Phase Power Calculator](/tools/three-phase-power-calculator/) — Three-phase power (current → sizing context)

**External links (national standards)**:

- [National Standards Full-Text Public Query System](http://openstd.samr.gov.cn/){target="_blank" rel="nofollow noopener"} — Standardization Administration official portal

---

## Meta & OG

```html
<!-- Basic Meta -->
<title>Cable Current-Carrying Capacity Lookup | NEC 310.15 / Table 310.16 Online Reference — elec.webpenson.com</title>
<meta name="description" content="Online cable ampacity lookup tool aligned with NEC 310.15 and Table 310.15(B)(16) (formerly 310.16), the 75°C / 90°C ampacity columns for THHN / XHHW-2 / USE-2 and other common conductors. Covers 5 installation methods: free-air, conduit, cable tray, direct burial, and duct. Applies NEC 310.15(A)(2) ambient baseline (30°C), 310.15(B)(2)(a) temperature correction, and 310.15(C)(1) more-than-three CCs adjustment." />
<meta name="keywords" content="cable ampacity lookup,NEC 310.15,Table 310.16,NEC cable ampacity,THHN ampacity,XHHW-2 ampacity,conduit cable ampacity,cable ampacity correction factors" />
<meta name="robots" content="index,follow" />
<meta name="author" content="elec.webpenson.com" />
<meta name="viewport" content="width=device-width, initial-scale=1" />

<!-- Open Graph -->
<meta property="og:type" content="website" />
<meta property="og:title" content="Cable Current-Carrying Capacity Lookup | NEC 310.15 / Table 310.16 Online Reference" />
<meta property="og:description" content="Online cable ampacity lookup tool aligned with NEC 310.15. 5 installation methods + NEC 310.15(B)(2)(a) temperature correction + 310.15(C)(1) more-than-three adjustment." />
<meta property="og:url" content="https://elec.webpenson.com/tools/cable-current-carrying-capacity-lookup/" />
<meta property="og:site_name" content="elec.webpenson.com" />
<meta property="og:locale" content="en_US" />
<meta property="og:image" content="https://elec.webpenson.com/og/cable-current-carrying-capacity-lookup.png" />

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Cable Current-Carrying Capacity Lookup | NEC 310.15 / Table 310.16 Online Reference" />
<meta name="twitter:description" content="Online cable ampacity lookup tool aligned with NEC 310.15. 5 installation methods + NEC correction framework." />
```

---

## JSON-LD Structured Data

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "Cable Current-Carrying Capacity Lookup",
  "alternateName": "Cable Ampacity Lookup",
  "description": "Online cable ampacity lookup tool supporting YJV / YJLV / VV / VLV / BVR / BLVR and other cable types. Covers 5 installation methods: free-air, conduit, tray, direct burial, and duct. Automatically applies GB 50217 temperature, grouping, and altitude correction factors.",
  "url": "https://elec.webpenson.com/tools/cable-current-carrying-capacity-lookup/",
  "applicationCategory": "EngineeringApplication",
  "applicationSubCategory": "ElectricalDesignTool",
  "operatingSystem": "Any (Web Browser)",
  "inLanguage": "en-US",
  "browserRequirements": "Requires JavaScript. Requires HTML5.",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "CNY"
  },
  "author": {
    "@type": "Organization",
    "name": "elec.webpenson.com",
    "url": "https://elec.webpenson.com/",
    "logo": "https://elec.webpenson.com/logo.png"
  },
  "keywords": "cable ampacity lookup,YJV cable ampacity,YJV22 ampacity table,cable ampacity reference,GB 50217 cable ampacity,conduit cable ampacity,cable ampacity correction factors,10kV cable ampacity,low-voltage cable ampacity"
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://elec.webpenson.com/" },
    { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://elec.webpenson.com/tools/" },
    { "@type": "ListItem", "position": 3, "name": "Cable Ampacity Lookup", "item": "https://elec.webpenson.com/tools/cable-current-carrying-capacity-lookup/" }
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is cable current-carrying capacity?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Cable ampacity is the maximum current a cable can carry continuously under specified conditions (temperature, installation, grouping, altitude), in amperes (A). It is not a fixed value — it varies with installation conditions as a corrected result. During design, you must satisfy: continuous load current I_L ≤ corrected ampacity I_z; otherwise the cable will overheat, insulation will age prematurely, or in severe cases, cause fire."
      }
    },
    {
      "@type": "Question",
      "name": "What is the difference between YJV and VV cable ampacity?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "For the same cross-section, YJV (cross-linked polyethylene) ampacity is 15–25% higher than VV (polyvinyl chloride). Reason: XLPE insulation is rated at 90°C, PVC at 70°C — higher allowable operating temperature means greater ampacity. Recommendation: Prioritize YJV for high-load, densely installed, and outdoor high-temperature scenarios; VV may be suitable for low-cost, temporary, or indoor dry environments. For the same 50 mm² copper conductor, YJV carries approximately 192 A in free air, VV only approximately 148 A."
      }
    },
    {
      "@type": "Question",
      "name": "Why is there such a large difference between conduit and free-air ampacity?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Conduit installation has poor heat dissipation — K_s is typically 0.75–0.85; free-air installation has good natural convection, K_s = 1.0. Actual difference: For 4 mm² copper, free-air is approximately 42 A (XLPE) or 35 A (PVC), while conduit is approximately 30 A — a 20–40% gap. More conductors in a conduit means greater derating; 3-core is 5–10% lower than 1-core."
      }
    },
    {
      "@type": "Question",
      "name": "Why do multiple parallel cables need derating?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "When multiple cables are installed touching each other, their mutual heating raises the ambient temperature — derating is required. 2 parallel ≈ 0.88, 3 cables 0.82, 4 cables 0.77, 6 cables 0.73 (typical values, varies by installation). Engineering approach: splitting to separate trays, layers, or busbars is more economical than cramming into one tray — better heat dissipation and easier maintenance and expansion."
      }
    },
    {
      "@type": "Question",
      "name": "How does altitude affect ampacity?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Higher altitude means thinner air, poorer heat dissipation. GB 50217 Section 5.0.7 requires correction per Table 5.4.6. Example: 2000 m, K_h ≈ 0.94; 3000 m, K_h ≈ 0.88 (non-linear table values). Yunnan-Guizhou / Qinghai-Tibet projects must check altitude; plains may default to K_h = 1.0. GB Table 5.4.6 is equivalent to IEC Table B.52.16 but differs from the simple linear derivation — use the standard table directly for engineering audits."
      }
    },
    {
      "@type": "Question",
      "name": "How do cable ampacity and circuit breaker setting current match?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Per GB 50054-2011, circuit breaker rated current I_n ≤ I_z (equal or smaller — hard constraint per Section 6.3.1). For 1.3× overload coordination (e.g., motor starting), also verify 1.45 × I_z trip current (Section 6.3.4). Example: Corrected ampacity 100 A, set breaker at 100 A or 80 A — do not select 125 A for long-term operation. Short-circuit protection is a separate calculation covered by the circuit breaker sizing tool."
      }
    },
    {
      "@type": "Question",
      "name": "GB 50217 or IEC 60364 — which should I use?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "For domestic power engineering, prefer GB 50217; for building electrical, GB 50054 is a useful reference. For overseas/export projects, IEC 60364-5-52 is more universally recognized — some Africa and Southeast Asia bid documents directly cite IEC. The I₀ tables differ minimally (±5%), and correction factor logic is consistent — either standard is acceptable, but use one consistently throughout. Do not mix GB for cables with IEC for breakers in the same project."
      }
    },
    {
      "@type": "Question",
      "name": "How is the temperature correction factor calculated?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Based on conductor allowable operating temperature θ_n and actual ambient temperature θ_a, from GB 50217 Table E.0.1 (25°C base). Simplified formula: K_θ = √((θ_n - θ_a) / (θ_n - 25)). Example: XLPE (θ_n = 90), ambient 40°C → K_θ ≈ 0.87; ambient 35°C → K_θ ≈ 0.91 (table-lookup values per GB 50217 Table E.0.1). PVC insulation (θ_n = 70) uses the same formula but with faster derating due to lower temperature rating."
      }
    }
  ]
}
</script>


## References

- NFPA 70 — National Electrical Code (NEC) 2023 / 2020, Article 310 (Ampacities of Conductors)
- IEC 60364-5-52 Low-voltage Electrical Installations (cross-reference)
- Chinese GB 50217-2018 (cross-reference for Chinese-mainland projects)
