---
title: "Transformer Capacity Selection Calculator — kVA Sizing & GB/T 17468 R10 Standard Ratings"
description: "Online transformer capacity selection calculator. Enter power kW, power factor cosφ, efficiency η, and load factor β to quickly estimate required transformer kVA capacity. Recommends GB/T 17468 R10 standard ratings. Supports single-equipment / multi-equipment diversity factor / motor starting current correction. For engineering design, factory distribution, and design institute calculation sheets."
categories:
  - "Electrical Tools"
  - "Transformers & Distribution"
  - "Engineering Quick Reference"


images:
  - "/images/tools/transformer-capacity-selection.svg"
tags:
  - "transformer"
  - "kVA"
  - "transformer sizing"
  - "GB/T 17468"
  - "R10 preferred numbers"
  - "motor inrush"
  - "short-circuit impedance"
keywords:
  - "transformer capacity selection"
  - "kVA sizing"
  - "transformer rating"
  - "R10 preferred numbers"
  - "motor starting current"
  - "transformer loading"
layout: "page"
translationKey: "transformer_capacity_selection"
date: "2026-07-19T00:00:00+00:00"
draft: false
---

{{< transformer-capacity-selection >}}


# Transformer Capacity Selection Calculator — kVA Sizing & GB/T 17468 R10 Standard Ratings

## Introduction

**Transformer capacity selection** is a mandatory step in factory distribution, building electrical systems, and design institute calculation sheets. The traditional approach involves flipping through GB/T 17468 *Guide for Selection of Power Transformers* or GB 1094 *Power Transformers*, manually calculating **S = P / (cosφ × η)**, then looking up the nearest standard rating from the R10 preferred number series — with multi-equipment scenarios requiring a diversity factor KΣ and motor loads requiring starting current calculations. This is cumbersome and error-prone. This tool encapsulates the core formulas and national standard rating series into a web form. Enter your parameters and get recommended capacity and sizing rationale instantly — suitable for designers, constructors, and maintenance engineers alike.

---

## Tool Features — Implemented Sizing Modes

### Tab ① Demand Factor Method (Recommended, GB 50054)

**Applicable scenarios**: Multiple pieces of equipment sharing one transformer, with loads not all running at full load simultaneously. Core formula: **S = ΣP_i × K_xi × KΣ / (cosφ_avg × η)**, where cosφ_avg is calculated-load-weighted (GB 50054-2011 §3.4.5). **Typical users**: Factory workshop distribution, residential area substations, commercial complexes, hospital ICUs, design institute electrical discipline.

```
Input: Multi-equipment power P_i / Demand factor K_xi / Various cosφ_i / Diversity factor KΣ / Transformer efficiency η / Margin K_m
Output: Calculated load P_c / Apparent calculated load S_c / Required minimum capacity S_N_min / Recommended standard rating S_N_std / Actual load factor β_actual
```

### Tab ② Total Power Method (Quick Estimate)

**Applicable scenarios**: Single motor / heater bank / rectifier supply / total load known. Core formula: **S = P / (cosφ × η) × K_m**. **Typical users**: Design institute electrical discipline, factory single large equipment supply, construction drawing design phase quick estimate.

```
Input: Total active power P / Equipment type / Total power factor cosφ / Transformer efficiency η / Margin K_m
Output: Apparent power S / Required minimum capacity S_N_min / Recommended standard rating S_N_std / Actual load factor β_actual
```

### Tab ③ Motor Starting Check (GB 50055 §3.3.4)

**Applicable scenarios**: Transformers primarily supplying motors, with DOL / soft-start / VFD starting. Core formula: **S_st = K_st × P_motor / (cosφ × η)**; transformer impedance voltage drop **U_drop% ≈ S_st / S_n × U_k%**; verify **U_terminal ≥ 85% × U_n** (frequent starting ≥ 90%). **Typical users**: Motor-intensive workshops, water supply and drainage pump stations, fan and pump rooms, compressor distribution.

```
Input: Worst-case single motor capacity P_motor / Starting method (DOL/Y-Δ/soft-start) / Starting multiple K_st / cosφ / η / Bus voltage U_n / Transformer short-circuit impedance U_k%
Output: Starting apparent power S_st / Starting current I_st / Transformer impedance voltage drop U_drop% / Terminal voltage U_terminal/U_n / Recommended standard capacity S_n (R10 iterative)
```

### Tab ④ Harmonic Derating K_h Correction (IEEE 519 / GB/T 14549)

**Applicable scenarios**: Transformer supplying harmonic sources (6-pulse / 12-pulse rectifier, UPS, VFD clusters, large-scale LED). Core formula: **S_corrected = S_demand × K_h**; **6-pulse rectifier K_h ≈ 1.10–1.20** (THDi ≈ 33%); **12-pulse rectifier K_h ≈ 1.05–1.10** (THDi ≈ 10%). **Typical users**: Data centers (UPS), VFD-intensive workshops, electrolytic rectifier stations, large-scale LED lighting.

```
Input: Fundamental required capacity S_demand / Rectifier pulse count (6/12) / Current THDi
Output: Harmonic derating factor K_h / Harmonic-corrected capacity S_corrected / Recommended standard rating S_N (R10 round-up)
```

**Not Yet Implemented** (planned for future versions):

- Load Factor Optimization (Economic Operation): Multi-transformer parallel / data-center 24h continuous supply
- Standalone R10 Rating Recommendation: Currently R10 is integrated into Tab ①/②/③/④ as the capacity output
- Full UPS / Generator Coordination: Currently Tab ④ harmonic derating covers partial UPS scenarios

---

## Preset Values — 6 Input Parameter Categories

### Equipment Type (5 presets + custom)

| Type | Typical cosφ | Typical η | Notes |
|---|---|---|---|
| Induction motor (full load) | 0.85 | 0.92 | Most common load; starting multiple 5–7 (DOL) |
| Synchronous motor | 0.90 (leading) | 0.95 | Can provide reactive compensation; improves power factor |
| Rectifier / VFD load | 0.95–0.98 | 0.97 | Harmonic source; requires K_h derating correction |
| Resistive heating / lighting | 1.00 | 1.00 | Purely resistive; no starting surge |
| Custom | User input | User input | Engineer-defined scenario |

### Input Voltage Class (4 presets)

- **0.4 kV** (380/220 V, low-voltage distribution, most common; factory workshop / building distribution)
- **6 kV** (Medium-voltage distribution; legacy factory substations; coal mining / chemical)
- **10 kV** (Medium-voltage distribution; national standard mainstream; new factories / substations)
- **35 kV** (High-voltage distribution; regional substations; large industrial bases)

### GB/T 17468 R10 Standard Rating Series (19 ratings, including 63 kVA common tier)

| Rating Group | Standard Ratings (kVA) |
|---|---|
| Small capacity | 30 / 50 / **63** / 80 / 100 |
| Medium capacity | 160 / 200 / 250 / 315 / 400 / 500 / 630 |
| Large capacity | 800 / 1000 / 1250 / 1600 / 2000 / 2500 |

(19 ratings total; source GB/T 17468-2019 *Guide for Selection of Power Transformers* + GB/T 321 *Preferred Numbers*; **63 kVA** is the common mid-range rating for commercial/industrial distribution.)

### Starting Method (3 options)

- **Direct-on-line (DOL)** — K_st = 5–7 (most common; small-capacity motors; GB 50055 default value)
- **Star-delta (Y-Δ)** — K_st = 2–3 (reduced-voltage starting; applicable to cage motors with light-load starting)
- **Soft-starter / VFD** — K_st = 1.0–1.5 (smooth starting; reduces grid impact; preferred for large-capacity motors)

### Diversity Factor KΣ (4 presets + custom)

- **0.9** — 2–3 pieces of equipment; nearly simultaneous operation
- **0.8** — 4–6 pieces; most operate simultaneously
- **0.7** — 7–10 pieces; partial load staggering
- **0.6** — >10 pieces; significant load staggering
- **Custom** — 0.5 ~ 1.0 range; engineer adjusts per process requirements

### Load Factor β (3 presets + custom)

- **0.7** — Lower limit of economic operation zone (near transformer efficiency curve peak)
- **0.85** — Recommended value (balance of economy and margin; withstands 3-year load growth)
- **1.0** — Full load; no expansion margin (not recommended for long-term operation)
- **Custom** — 0.5 ~ 1.2 range

---

## Output Descriptions

### Required Capacity S_demand

Defined as: The minimum transformer capacity calculated from the input equipment power, power factor, efficiency, diversity factor, starting multiple, and other parameters. Calculation formula: **S_demand(kVA) = P(kW) × KΣ × K_st / (cosφ × η)**. **Engineering meaning**: During sizing, **standard rating S_n ≥ S_demand** is the hard constraint.

### Recommended Standard Rating S_n

Defined as: The nearest standard rating not less than S_demand, selected from the **GB/T 17468 R10 preferred number series**. The tool does not expose the raw table externally — only the recommended rating as an output item.

**Recommendation principles**:

- **S_n ≥ 1.15 × S_demand** — 15% expansion margin; **default recommendation** (withstands 3-year load growth)
- **S_n = 1.0 × S_demand** — Just meets requirements; no expansion (acceptable short-term; not recommended long-term)
- **S_n < S_demand** — ⚠️ **Warning: Capacity insufficient — select the next larger rating or parallel transformers**

### Actual Load Factor β_actual

Defined as: **S_demand / S_n**, reflecting the transformer's actual load level after sizing. **Engineering meaning**:

- **0.6 ~ 0.85** — ✅ **Economic operation zone** (highest transformer efficiency; optimal balance of no-load and load loss)
- **0.85 ~ 0.95** — Full-load zone; acceptable short-term; copper loss rises sharply with long-term operation
- **> 0.95** — ⚠️ Overload risk; accelerated insulation aging; shortened service life
- **< 0.5** — ⚠️ Long-term low load; "large horse pulling small cart"; high no-load loss ratio; poor efficiency

### Sizing Rationale

The tool does not issue binary pass/fail judgments, but provides descriptive guidance, for example:

- ✅ "Complies with GB/T 17468 R10 rating recommendation; actual load factor 78% (economic operation zone)"
- ⚠️ "Capacity is low — recommend 100 kVA instead of 80 kVA; retain expansion margin"
- ⚠️ "Actual load factor 92%; approaching overload — not economical for long-term operation"
- 💡 "Note: Synchronous motors can provide reactive compensation — actual cosφ can be adjusted up to 0.95"

### Starting Current Verification (Motor Scenarios)

When the equipment type is a motor, the tool additionally calculates:

- **Starting apparent power**: S_st = √3 × U × I_st
- **Transformer impedance voltage drop**: U_drop% ≈ S_st / S_n × U_k% (U_k% typical 4%–6%; GB 1094)
- **Terminal voltage verification**: U_terminal ≥ 0.85 × U_n (GB 50055 motor starting terminal voltage requirement)
- **Example output**: "Starting bus voltage drop 12%; complies with GB 50055 motor starting terminal voltage ≥ 85% of rated requirement"

---

## Formula Details

### Core Formula (Single Equipment)

```
S(kVA) = P(kW) / (cosφ × η)
```

- **P** — Equipment active power (kW)
- **cosφ** — Power factor (between 0 and 1; typical 0.7–0.98)
- **η** — Transformer efficiency (typical 0.95–0.98; higher for larger units)

**Example**: 100 kW motor load, cosφ = 0.85, η = 0.97 → S ≈ 100 / (0.85 × 0.97) ≈ **121 kVA** → round up to nearest R10 → **125 kVA**.

### Margin K_m and Target Load Factor β_opt (Naming Fix 2026-07-29)

In this tool:

- **Margin K_m** (engineering experience 1.10–1.25, GB 50052 recommended) → directly multiplied with required capacity, retaining safety margin
- **Target load factor β_opt** (0.70–0.85) → reference for "engineer's expected actual load factor"; **not participating in division calculation**
- **Actual load factor β_actual** = S_c / S_N_std (real load factor after selecting R10 standard rating)

```
S_N_min = (S_c / η) × K_m            # Required minimum capacity
S_N_std = selectStandardCapacity(S_N_min)  # Round up to nearest R10 rating
β_actual = S_c / S_N_std              # Actual load factor (verify 0.7–0.85)
```

**Correction Note**: The old version used `S_N_min = (S_c / η) × (K_m / β_opt)`, which caused β_actual to deviate from the expected value (e.g., with β_opt=0.85, β_actual became 71%). The new version uses K_m only as a margin multiplier and β_opt only as a target reference — this way β_actual truly reflects the actual load factor after sizing.

### Multi-Equipment Diversity Factor

```
S(kVA) = KΣ × ΣP_i / (cosφ_avg × η)
```

- **KΣ** — Diversity factor (0.6–0.9; see preset table)
- **ΣP_i** — Sum of active power of equipment type i (kW)
- **cosφ_avg** — **Load-weighted average power factor**

**Weighted formula** (per GB 50054-2011 §3.4.5):

```
cosφ_avg = Σ(P_i × K_xi × cosφ_i) / Σ(P_i × K_xi)
```

Where P_i = total active power of equipment type i (kW), K_xi = demand factor (0.4–1.0), cosφ_i = power factor of equipment type i. **Note**: Both numerator and denominator are multiplied by K_xi — i.e., **"weighted by calculated load"** rather than "weighted by total rated equipment power" — this accurately reflects the real operating condition where equipment does not all run at full load simultaneously.

### Motor Starting Correction

```
S(kVA) ≥ K_st × ΣP_motor / (cosφ × η)
```

- **K_st** — Starting current multiple
  - **DOL**: 5–7 (GB 50055 default; small-capacity motors)
  - **Y-Δ**: 2–3 (reduced-voltage starting; applicable to cage motors)
  - **Soft-start**: 1.0–1.5 (smooth starting; preferred for large-capacity motors)
- The formula takes the **most adverse starting combination's peak value**, not a simple sum
- The transformer's short-circuit impedance U_k% also affects starting voltage drop and requires separate verification

### Economic Load Factor

```
β_opt = 0.7 ~ 0.85   (Economic operation zone)
S_optimal = P_avg / (β_opt × cosφ × η)
```

**Basis**: Transformer efficiency curve peaks near β = 0.5–0.7; long-term full-load operation (β ≈ 1.0) causes copper loss to increase sharply. Engineering convention: calculate at β = 0.85 during sizing, retaining 15% expansion margin.

### Harmonic Derating K_h Correction

```
S_corrected(kVA) = S_demand(kVA) × K_h
```

- **S_demand** — Fundamental required capacity (kVA, excluding harmonic correction)
- **K_h** — Harmonic derating factor (engineering range)
  - **6-pulse rectifier** (THDi ≈ 33%): K_h ≈ 1.10–1.20 (10%–20% derating)
  - **12-pulse rectifier** (THDi ≈ 10%): K_h ≈ 1.05–1.10 (5%–10% derating)

**This tool's approximation**: K_h ≈ 1 + 0.50 × (THDi / 100), clamped to engineering range. Example: 6-pulse THDi=33% → K_h ≈ 1.165; S_demand=100 kVA → S_corrected = 116.5 kVA → R10 = 125 kVA.

**Reference**: IEEE 519-2022 / GB/T 14549-1993 *Power Quality — Harmonics in Public Supply Networks* for harmonic current limits and transformer derating recommendations for different pulse rectifiers.

### Sizing Verification

```
S_demand ≤ S_n ≤ S_demand × 1.3   (15%~30% expansion margin; recommended)
or
S_demand ≤ S_n                     (Just meets requirements; no expansion; not recommended)
```

Note: The **1.3× upper limit is an engineering convention** — not included in tool output, only in the educational section to prevent engineer misuse.

---

## National Standard References

### GB/T 17468-2019 *Guide for Selection of Power Transformers*

People's Republic of China National Standard, **GB/T 17468-2019**, published 2019 (superseding GB/T 17468-1998). Supervising body: State Administration for Market Regulation / Standardization Administration of China. Contents: transformer selection principles, load factors, capacity determination, R10 preferred number series. This tool's national standard rating recommendations (**19 ratings from 30 to 2500 kVA**, including the common 63 kVA tier) are based on this standard.

**Rating breakdown (19 tiers)**:

- **Small capacity (30–100 kVA)**: 30 / 50 / **63** / 80 / 100 kVA — small-capacity workshops, construction site temporary power, **63 kVA is the common mid-range for commercial/industrial distribution**
- **Medium capacity (160–630 kVA)**: 160 / 200 / 250 / 315 / 400 / 500 / 630 kVA — factory distribution, residential area substations; primary rating tier
- **Large capacity (800–2500 kVA)**: 800 / 1000 / 1250 / 1600 / 2000 / 2500 kVA — regional substations, large factories, commercial complexes

This tool is for engineering estimation only. Actual engineering design shall prevail with the version published by the Standardization Administration of China. Access: [National Standards Full-Text Public Query System](http://openstd.samr.gov.cn/){target="_blank" rel="nofollow noopener"}.

### GB 1094 *Power Transformers* Series

People's Republic of China National Standard, **GB 1094.1~.11 series**. Contents: general provisions, temperature rise, insulation levels, winding connections, short-circuit withstand capability. Relevant to this tool: **temperature rise limits** (affecting actual overload capability) and **short-circuit impedance U_k%** (affecting starting voltage drop calculation; typical 4%–6%).

### Other Reference Standards

- **GB 50052-2009 *Code for Design of Electric Power Supply Systems*** — Transformer minimum efficiency values (no-load loss P₀, load loss P_k)
- **GB 20052-2020 *Minimum Allowable Values of Energy Efficiency and the Energy Efficiency Grades of Power Transformers*** — Grade 1 / 2 / 3 energy efficiency transformer loss limits; for procurement, energy efficiency grade is more important than the η value itself
- **GB/T 321-2005 *Preferred Numbers*** — R10 series (1, 1.25, 1.6, 2.0, 2.5, 3.15, 4.0, 5.0, 6.3, 8.0…) national standard basis
- **GB 50054-2011 *Code for Design of Low Voltage Electrical Installations* §3.4.5** — cosφ_avg weighted formula national standard source
- **GB 50055-2011 *Code for Design of Distribution of General-Purpose Electric Equipment*** — DOL / Y-Δ starting current multiples and terminal voltage verification requirements

---

## Frequently Asked Questions (FAQ)

### How do I calculate transformer capacity most accurately?

Core formula: **S(kVA) = P(kW) / (cosφ × η)**, where P is active power, cosφ is power factor, and η is transformer efficiency. For multi-equipment: **S = KΣ × ΣP / (cosφ_avg × η)**, where KΣ is the diversity factor (0.6–0.9). For motor loads, apply the starting multiple: calculate **K_st × P_motor** first, then divide by (cosφ × η) — **do not simply sum**. **Most accurate approach**: After calculating S, look up the GB/T 17468 R10 rating table, select the nearest rating not less than S, and retain 15%–30% expansion margin.

### How does power factor cosφ affect transformer capacity?

Lower cosφ means a larger required kVA — the transformer is more expensive and line losses are higher. Example: 100 kW load, cosφ = 0.95 → S ≈ 110 kVA; cosφ = 0.7 → S ≈ 149 kVA (**35% more expensive**). **Countermeasure**: Install capacitor compensation to raise cosφ above 0.9; China's Power Factor Adjustment Electricity Fee Method also incentivizes compensation (penalties apply below 0.9). Transformer nameplates are in kVA, not kW, because cosφ is uncontrollable — the transformer can only guarantee the maximum apparent capacity S.

### What is the optimal transformer load factor?

The economic operation zone is **0.7–0.85** — higher is not better. Load factor below 0.5 ("large horse pulling small cart"): High no-load loss proportion, low efficiency, uneconomical. Load factor 0.85–0.95: Near full-load; acceptable short-term; copper loss rises sharply with long-term operation. Load factor > 0.95: Overload risk, accelerated insulation aging, shortened service life. **Engineering convention**: Calculate at β = 0.85 during sizing, retaining 15% expansion margin (withstands 3-year load growth).

### What is the typical transformer efficiency η?

Distribution transformers (10/0.4 kV, 100–2500 kVA) typically have efficiency of **0.95–0.98**. Small transformers (30–80 kVA): η ≈ 0.93–0.95. Medium transformers (100–800 kVA): η ≈ 0.95–0.97. Large transformers (1000–2500 kVA): η ≈ 0.97–0.98. **New standard GB 20052-2020** sets stricter loss limits for Grade 1 / 2 energy efficiency transformers — for actual procurement, the energy efficiency grade is more important than the η value itself. **Note**: η is the transformer's own efficiency, not the load's power factor — these are two different concepts.

### Which national standard governs transformer capacity selection?

Primary reference: **GB/T 17468-2019 *Guide for Selection of Power Transformers*** (superseding GB/T 17468-1998). The R10 rating series (30 / 50 / **63** / 80 / 100 / 125 / 160 / 200 / 250 / 315 / 400 / 500 / 630 / 800 / 1000 / 1250 / 1600 / 2000 / 2500 kVA, **19 ratings**) comes from this standard. Supporting standards: GB 1094 *Power Transformers* series (temperature rise, insulation, short-circuit impedance), GB 50052 *Code for Design of Electric Power Supply Systems* (transformer minimum efficiency), GB 20052 *Power Transformer Energy Efficiency Grades*. **For international projects**, refer to IEC 60076 series — the rating series is consistent with GB R10.

### What are the common transformer standard ratings?

GB/T 17468 R10 preferred number series **19 ratings** (in kVA):

- **Small capacity (≤100)**: 30 / 50 / **63** / 80 / 100 — suitable for small-capacity workshops, construction site temporary power (**63 kVA is the common mid-range for commercial/industrial distribution**)
- **Medium capacity (160–630)**: 160 / 200 / 250 / 315 / 400 / 500 / 630 — factory distribution, residential area substations; primary rating tier
- **Large capacity (800–2500)**: 800 / 1000 / 1250 / 1600 / 2000 / 2500 — regional substations, large factories, commercial complexes

**Sizing principle**: After calculating S, **round up one tier**, retaining 15%–30% expansion margin. If the result is 180 kVA, select 200, not 160 (full-load operation shortens service life).

### How do I match transformer and UPS capacities?

Rule-of-thumb formula: **S_transformer ≥ S_UPS / 0.8**. Example: 100 kVA UPS requires a front-end transformer of at least 125 kVA (125 × 0.8 = 100, just covers UPS full load). Considering UPS input harmonics (6-pulse rectifier THDi ≈ 33%), the transformer also requires 10%–20% derating — **actually select ≥ 160 kVA**. **Generator coordination**: **S_generator ≈ S_transformer × 1.1–1.25** (accounting for generator nonlinear load derating and step-load capability). **Key point**: UPS capacity (kVA) ≠ actual load (kW); UPS cosφ is typically 0.9–1.0 (modern UPS); older UPS may be 0.8.

---

## Internal Links (Companion Tools)

- [Three-Phase Power Calculator](/tools/three-phase-power-calculator/) — Same cosφ topic; transformer sizing requires first calculating S = P/cosφ
- [Electricity Cost Calculator](/tools/electricity-cost-calculator/) — cosφ 0.9 threshold affects reactive power fees; before/after compensation comparison
- [EV Charger Power Calculator](/tools/charging-power-calculator/) — EV charging station transformer sizing scenario; 7kW / 11kW / 22kW charger quantities → transformer capacity
- [Cable Current-Carrying Capacity Lookup](/tools/cable-current-carrying-capacity-lookup/) — Transformer low-voltage side outgoing cable sizing

---

## Disclaimer

> **Important**: Capacity recommendations provided by this tool are based on **simplified calculations from GB/T 17468-2019 *Guide for Selection of Power Transformers*** and **GB 20052-2020 *Power Transformer Energy Efficiency Grades***, for **engineering estimation only**.
>
> Actual engineering design must:
> 1. Use the latest published GB/T 17468 national standard as the authoritative source
> 2. Obtain a formal calculation sheet from a design institute / registered electrical engineer
> 3. Special scenarios (chemical corrosion, hazardous areas, offshore wind power, subway, hospital) require additional industry standard references
> 4. Verify manufacturer data sheets and energy efficiency grades before transformer procurement
>
> This tool **does not provide** automatic transformer model selection and **does not replace** professional engineering judgment. This tool assumes no liability for any engineering incidents resulting from the use of this tool's data.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://elec.webpenson.com/" },
    { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://elec.webpenson.com/tools/" },
    { "@type": "ListItem", "position": 3, "name": "Transformer Capacity Selection Calculator", "item": "https://elec.webpenson.com/tools/transformer-capacity-selection/" }
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to size a transformer per GB/T 17468 R10 / GB 50054 / GB 50055",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "Choose mode & enter load parameters",
      "text": "Pick Tab ① Demand Factor Method (multi-equipment, diversity factor KΣ), Tab ② Total Power Method (single equipment / total load), Tab ③ Motor Starting Check (GB 50055 §3.3.4), or Tab ④ Harmonic Derating (K_h correction). Enter power kW, power factor cosφ, efficiency η, and other relevant parameters."
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "Read the transformer result card",
      "text": "The result card shows required capacity S_demand, required minimum capacity S_N_min, recommended standard rating S_N_std (GB/T 17468 R10 preferred numbers, round-up), and actual load factor β_actual. Tab ③ additionally outputs starting voltage drop U_drop% and terminal voltage U_terminal/U_n (required ≥ 85%); Tab ④ additionally outputs harmonic derating factor K_h and corrected capacity."
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "Validate selection & finalize",
      "text": "Verify β_actual falls within the 70%–85% economic operation zone (GB 50052 §6.0.7), confirm U_terminal meets the ≥ 85% terminal voltage requirement (motor scenarios), and confirm K_h-corrected harmonic losses are acceptable (UPS / VFD scenarios). When issuing calculation sheets and procurement lists, record the cited clauses from GB/T 17468-2019, GB 50054-2011, GB 50055-2011, and GB 1094.5-2024."
    }
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "Transformer Capacity Selection",
  "alternateName": "Transformer kVA Sizing",
  "description": "Online transformer capacity selection calculator. Enter power, power factor, efficiency, and load factor to quickly estimate required kVA capacity. Recommends GB/T 17468 R10 standard ratings. Supports multi-equipment diversity factor and motor starting current correction.",
  "url": "https://elec.webpenson.com/tools/transformer-capacity-selection/",
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
  "keywords": "transformer capacity selection,transformer sizing calculation,transformer kVA calculation,transformer capacity formula,distribution transformer sizing,transformer load factor,R10 rating series,transformer power factor correction"
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "How do I calculate transformer capacity most accurately?", "acceptedAnswer": {"@type": "Answer", "text": "Core formula S(kVA) = P(kW) / (cosφ × η), where P is active power, cosφ is power factor, and η is transformer efficiency. For multi-equipment: S = KΣ × ΣP / (cosφ_avg × η), KΣ is diversity factor (0.6–0.9). For motor loads, apply starting multiple: K_st × P_motor first, then divide by (cosφ × η) — do not simply sum. Most accurate: calculate S, look up GB/T 17468 R10 table, select nearest rating ≥ S, retain 15%–30% expansion margin."}},
    {"@type": "Question", "name": "How does power factor cosφ affect transformer capacity?", "acceptedAnswer": {"@type": "Answer", "text": "Lower cosφ means larger required kVA — transformer is more expensive and line losses are higher. Example: 100 kW load, cosφ = 0.95 → S ≈ 110 kVA; cosφ = 0.7 → S ≈ 149 kVA (35% more expensive). Countermeasure: Install capacitor compensation to raise cosφ above 0.9; China's Power Factor Adjustment Electricity Fee Method penalizes below 0.9. Transformer nameplates are in kVA, not kW, because cosφ is uncontrollable — the transformer can only guarantee maximum apparent capacity S."}},
    {"@type": "Question", "name": "What is the optimal transformer load factor?", "acceptedAnswer": {"@type": "Answer", "text": "Economic operation zone is 0.7–0.85 — higher is not better. Below 0.5: high no-load loss ratio, low efficiency. 0.85–0.95: near full-load, acceptable short-term, copper loss rises sharply long-term. Above 0.95: overload risk, accelerated aging. Engineering convention: calculate at β = 0.85, retain 15% expansion margin."}},
    {"@type": "Question", "name": "What is the typical transformer efficiency η?", "acceptedAnswer": {"@type": "Answer", "text": "Distribution transformers (10/0.4 kV, 100–2500 kVA) typically 0.95–0.98. Small (30–80 kVA): η ≈ 0.93–0.95; medium (100–800 kVA): η ≈ 0.95–0.97; large (1000–2500 kVA): η ≈ 0.97–0.98. GB 20052-2020 sets stricter loss limits for Grade 1/2 energy efficiency transformers — energy efficiency grade is more important than the η value for procurement. Note: η is the transformer's own efficiency, not the load's power factor — these are different concepts."}},
    {"@type": "Question", "name": "Which national standard governs transformer capacity selection?", "acceptedAnswer": {"@type": "Answer", "text": "Primary: GB/T 17468-2019 Guide for Selection of Power Transformers (superseding 1998 version). R10 rating series (30/50/63/80/100/125/160/200/250/315/400/500/630/800/1000/1250/1600/2000/2500 kVA, 19 ratings) comes from this standard. Supporting: GB 1094 series (temperature rise, insulation, short-circuit impedance), GB 50052 (transformer minimum efficiency), GB 20052 (energy efficiency grades). For international projects, refer to IEC 60076 series — rating series is consistent with GB R10."}},
    {"@type": "Question", "name": "What are the common transformer standard ratings?", "acceptedAnswer": {"@type": "Answer", "text": "GB/T 17468 R10 preferred number series 19 ratings (kVA). Small (≤100): 30/50/63/80/100 — small workshops, construction temporary power (63 kVA common mid-range). Medium (160–630): 160/200/250/315/400/500/630 — factory distribution, residential substations, primary tier. Large (800–2500): 800/1000/1250/1600/2000/2500 — regional substations, large factories, commercial complexes. Sizing: after calculating S, round up one tier, retain 15%–30% margin. 180 kVA → select 200, not 160."}},
    {"@type": "Question", "name": "How do I match transformer and UPS capacities?", "acceptedAnswer": {"@type": "Answer", "text": "Rule of thumb: S_transformer ≥ S_UPS / 0.8. Example: 100 kVA UPS requires ≥125 kVA front-end transformer (125 × 0.8 = 100). Considering UPS input harmonics (6-pulse rectifier THDi ≈ 33%), transformer also requires 10%–20% derating — actually select ≥160 kVA. Generator coordination: S_generator ≈ S_transformer × 1.1–1.25 (accounting for nonlinear load derating and step-load capability). UPS capacity (kVA) ≠ actual load (kW); modern UPS cosφ typically 0.9–1.0; older UPS may be 0.8."}}
  ]
}
</script>


## References

- GB/T 17468-2019 Guide for Selection of Power Transformers
- IEEE C57.91 Guide for Loading Mineral-Oil-Immersed Transformers
