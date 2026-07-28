---
title: "Cable Current-Carrying Capacity Lookup — YJV / YJV22 / VV Online Reference Tool"
description: "Online cable ampacity lookup tool supporting YJV / YJLV / VV / VLV / BVR / BLVR and other cable types. Covers 5 installation methods: free-air, conduit, tray, direct burial, and duct. Automatically applies GB 50217 temperature, grouping, and altitude correction factors. For electrical engineering design, on-site construction, and factory maintenance."
categories:
  - "Electrical Tools"
  - "Cable & Installation"
  - "Engineering Quick Reference"


images:
  - "/images/tools/cable-current-carrying-capacity-lookup.svg"
tags:
  - "cable ampacity"
  - "current carrying capacity"
  - "YJV cable"
  - "conduit installation"
  - "cable tray"
  - "direct burial"
  - "GB 50217"
  - "derating factor"
keywords:
  - "cable ampacity lookup"
  - "cable sizing"
  - "YJV cable"
  - "conduit installation"
  - "cable tray"
  - "direct burial"
  - "ampacity derating"
layout: "page"
translationKey: "cable_current_carrying_capacity_lookup"
date: "2026-07-18T21:05:00+00:00"
draft: false
---

{{< cable-current-carrying-capacity-lookup >}}

# Cable Current-Carrying Capacity Lookup — YJV / YJV22 Online Reference

## Introduction

**Cable current-carrying capacity lookup** is a daily task for electrical designers, construction teams, and maintenance engineers. The traditional approach involves flipping through GB 50217-2018 *Code for Design of Cables of Electric Engineering* or the IEC 60364-5-52 handbook — cross-referencing cross-sectional area, installation method, temperature, parallel circuits, and altitude on table after table. This is inefficient and error-prone. This tool encapsulates the base ampacity I₀ and four correction factors (K_θ temperature, K_s installation, K_p grouping, K_h altitude) into a web form. Enter your parameters and get the corrected ampacity I_z with factor breakdowns instantly. Suitable for design institute calculation sheets, factory inspections, and on-site temporary sizing — say goodbye to manual table-flipping.

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
| Copper | Cu | GB 50054 minimum copper cross-section 1.5 mm²; preferred for factory distribution |
| Aluminum | Al | GB 50054 minimum aluminum cross-section 10 mm²; cost-reduction scenarios |

### Cable Type (7 presets + custom)

| Name | Type | Insulation | Applicable Scenarios |
|---|---|---|---|
| XLPE insulated, PVC sheathed | YJV | XLPE 90°C | Indoor / tunnel / duct; most common |
| XLPE insulated, PVC sheathed (Al) | YJLV | XLPE 90°C | Large-section mains; cost reduction |
| XLPE insulated, steel tape armored, PVC sheathed | YJV22 | XLPE 90°C | Direct burial / outdoor; withstands mechanical stress |
| PVC insulated, PVC sheathed | VV | PVC 70°C | Legacy standard / low-cost scenarios |
| PVC insulated, PVC sheathed (Al) | VLV | PVC 70°C | Same; aluminum core |
| Copper PVC insulated flexible cable | BVR | PVC 70°C | Distribution panel wiring, flexible connections |
| Aluminum PVC insulated flexible cable | BLVR | PVC 70°C | Same; aluminum core |
| Custom | (free input) | — | Engineer-defined type |

### Cross-Section (16 tiers, 1.5 ~ 300 mm²)

| Tier (mm²) | 1.5 | 2.5 | 4 | 6 | 10 | 16 | 25 | 35 | 50 | 70 | 95 | 120 | 150 | 185 | 240 | 300 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|

(Unit mm²; tool presents as preset buttons + custom input; custom range 1.5 ~ 1000 mm²)

### Installation Method (5 types)

Free-air / Conduit / Cable tray / Direct burial / Duct (see Tool Features section for details)

### Ambient Temperature (°C; common presets + custom)

- **25°C** (GB 50217 reference temperature; base)
- **30°C** (Standard indoor)
- **35°C** (High-temperature workshop, summer outdoor)
- **40°C** (Dense cable tray, utility shafts)
- **Custom** (-20 ~ 60°C range; tool issues a warning if out of range)

### Parallel Circuit Count (5 tiers)

| Number of circuits n | 1 | 2 | 3 | 4 | 6 |
|---|---|---|---|---|---

(For > 6 circuits, treat as 6 and prompt: "Recommend splitting to separate trays / busbars")

### Sun Exposure / Shading (2 options)

- **Shaded**: Indoor / inside tray / conduit — no additional derating
- **Exposed to sun**: Outdoor direct sunlight — **additional correction K_s = 0.9 required** (GB 50217-2018 §5.4.5)

---

## Output Descriptions — I₀ / I_z / K Factors / Compliance Notes

### Base Ampacity I₀

Defined as: **Under standard base conditions (copper/aluminum conductor, single circuit, 25°C, free-air, no sun exposure, altitude ≤ 1000 m), the maximum current the conductor is permitted to carry continuously** (unit: A).

**Data source**: GB 50217-2018 Annex Tables C.0.1 ~ C.0.4 (0.6/1 kV XLPE / PVC insulated cables) and IEC 60364-5-52 Annex B (adopted equivalently). This tool does not expose the raw tables externally — I₀ is only presented as one output item. Engineers can expand and view it in the results section.

### Corrected Ampacity I_z

Defined as: **The maximum current the conductor is permitted to carry continuously under actual engineering conditions, after applying four correction factors** (unit: A).

**Engineering meaning**: During sizing verification, **the circuit's continuous load current I_L must satisfy I_L ≤ I_z** to meet GB 50217 requirements. Otherwise, the conductor is subject to long-term overload — accelerated insulation aging, and in severe cases, fire.

### Temperature Correction Factor K_θ

- **Source**: GB 50217-2018 Table E.0.1 (base temperature 25°C)
- **Range**: **0.87 (40°C) ~ 1.15 (10°C, XLPE)**; different values for XLPE vs PVC
- **Output**: Displays specific value + text note such as "XLPE insulation, θ_n = 90°C" / "PVC insulation, θ_n = 70°C"
- **Formula**: `K_θ = √((θ_n - θ_a) / (θ_n - 25))`

### Installation Method Correction Factor K_s

- **Source**: GB 50217-2018 Table D.0.1 / Table 5.4.5
- **Range**: **0.70 ~ 1.00**
  - 1.0 (free-air base)
  - 0.8 ~ 0.9 (conduit / duct)
  - 0.9 ~ 1.0 (cable tray)
  - 0.7 ~ 0.9 (direct burial, depending on soil thermal resistivity)
- **Output**: Displays value + text description

### Parallel Circuit Correction Factor K_p

- **Source**: GB 50217-2018 Table D.0.1 (equivalent to IEC 60364-5-52 Table B.52.17)
- **Range**: **0.73 ~ 1.00**
  - 1.0 (single circuit)
  - 0.88 (2 circuits touching)
  - 0.82 (3 circuits touching)
  - 0.77 (4 circuits touching)
  - 0.73 (6 circuits touching)
- **Output**: Displays value + circuit count and installation method (touching / spaced)

### Altitude Correction Factor K_h

- **Source**: **GB 50217-2018 Table 5.4.6** (altitude correction factor; non-linear table)

| Altitude (m) | ≤ 1000 | 1500 | 2000 | 2500 | 3000 | 3500 | 4000 |
|---|---|---|---|---|---|---|---|
| K_h | 1.00 | 0.97 | 0.94 | 0.91 | 0.88 | 0.85 | 0.82 |

- **Output**: Displays value + altitude advisory
- **Engineering note**: Below 1000 m, use 1.00; for 1000 ~ 4000 m, interpolate from the table; above 4000 m, the tool prompts: "Beyond the range of GB 50217 Table 5.4.6 — recommend referring to industry standards or conducting special design"

### Compliance Notes

The tool does not issue binary pass/fail judgments, but provides descriptive guidance, for example:

- "Complies with GB 50217-2018 Section 5.4"
- "Altitude > 1000 m — recommend reviewing cabinet thermal management"
- "Parallel circuits ≥ 4 — recommend splitting to separate trays / layers"
- "Ambient temperature close to insulation rating — recommend reviewing cable selection"

---

## Formula Details — I_z = I₀ × K_θ × K_s × K_p × K_h

### Core Formula

```
I_z = I_0 × K_θ × K_s × K_p × K_h
```

The four K factors multiply independently — **all coefficients ≤ 1** (all are 1.0 under base conditions). When the ambient temperature is below the base temperature (25°C), K_θ > 1.0, indicating that cooling conditions are better than base — a larger current is permitted. This is a physically meaningful interpretation recognized by both IEC and GB standards.

### Correction Factor Selection Key Points

| Factor | Meaning | Range | Source |
|---|---|---|---|
| K_θ | Effect of temperature deviation from base (25°C) | **0.87 ~ 1.15** (XLPE 10~40°C) | GB 50217 Table E.0.1 |
| K_s | Installation method thermal dissipation difference | 0.70 ~ 1.00 | GB 50217 Table D.0.1 |
| K_p | Multiple parallel circuit derating | 0.73 ~ 1.00 | GB 50217 Table D.0.1 |
| K_h | Effect of high altitude / thin air on cooling | 0.82 ~ 1.00 (≤ 4000 m) | GB 50217 Table 5.4.6 |

**Base temperature note:**

> This tool's K_θ strictly uses values from **GB 50217-2018 Table E.0.1** (**base temperature 25°C**).
> IEC 60364-5-52 Table B.52.14 uses 30°C as base, resulting in 2–3% differences in values — **China's national standard takes precedence**.
> **Engineering significance**: Under the same cross-section and installation conditions, the I₀ given by GB 50217 is typically 2–3% more conservative than IEC — **higher safety margin in sizing**.

### Sizing Verification

```
I_L ≤ I_z / 1.45      (Permits short-term overload at 1.45×, complying with IEC 60364-4-43)
or
I_L ≤ I_z             (For continuous load; recommended)
```

Note: The 1.45× short-term overload allowance is a typical IEC-standard value — **not included in tool output**, only in the educational section to prevent engineer misuse.

---

## National Standard References

### GB 50217-2018 *Code for Design of Cables of Electric Engineering*

People's Republic of China National Standard, **GB 50217-2018**, published 2018-09-11, effective 2019-04-01. Supervising body: China Electricity Council. Contents: cable selection, installation methods, ampacity corrections, protection coordination. This tool's I₀ and four correction factors (K_θ / K_s / K_p / K_h) are all based on the annex tables of this standard.

Note: This tool is for engineering estimation only. Actual engineering design shall prevail with the version published by the Standardization Administration of China. Access: [National Standards Full-Text Public Query System](http://openstd.samr.gov.cn/){target="_blank" rel="nofollow noopener"}.

### IEC 60364-5-52 / GB/T 16895.15-2005

International Electrotechnical Commission IEC 60364-5-52 *Low-voltage Electrical Installations — Part 5-52: Selection and Erection of Electrical Equipment — Wiring Systems*. Corresponding national standard: **GB/T 16895.15-2005** (equivalent adoption). Difference from GB 50217: GB 50217 leans toward Chinese power engineering conventions (high proportion of direct burial and conduit), while IEC 60364 leans toward building electrical conventions. For cross-border / export projects, cross-reference both standards.

### Other References

- GB/T 12706.1-2020 *Extruded Power Cables with Rated Voltages from 1 kV(Um=1.2 kV) up to and Including 35 kV(Um=40.5 kV) — Part 1: Cables for Rated Voltages of 1 kV and 3 kV*
- GB 50054-2011 *Code for Design of Low Voltage Electrical Installations* (circuit breaker setting reference)

---

## Frequently Asked Questions (FAQ)

### What is cable current-carrying capacity?

Cable current-carrying capacity (ampacity) is the **maximum current a cable can carry continuously under specified conditions** (temperature, installation, grouping, altitude), in amperes (A). It is not a fixed value — it varies with installation conditions as a corrected result. During design, you must satisfy: **continuous load current I_L ≤ corrected ampacity I_z**; otherwise the cable will overheat, insulation will age prematurely, or in severe cases, cause fire. Different installation methods, ambient conditions, and cross-sections can result in ampacity differences exceeding 30% — therefore, engineering applications must calculate each correction factor per the formula, not guess.

### What is the difference between YJV and VV cable ampacity?

For the same cross-section, YJV (cross-linked polyethylene) ampacity is **15% ~ 25% higher than VV (polyvinyl chloride)**. Reason: XLPE insulation is rated at 90°C, PVC insulation at 70°C — the higher the conductor allowable operating temperature, the greater the ampacity. **Selection recommendation**: Prioritize YJV for high-load, densely installed, and outdoor high-temperature scenarios; VV may be considered for low-cost, temporary, or indoor dry-environment installations. For the same 50 mm² copper conductor, YJV can carry approximately 192 A in free air, while VV carries only approximately 148 A.

### Why is there such a large difference between conduit-installed and free-air ampacity?

Conduit installation has poor heat dissipation — air inside the conduit does not flow, and heat is conducted away through the conduit wall, resulting in a typical **K_s of 0.75 ~ 0.85**; free-air installation has good heat dissipation with natural air convection, **K_s = 1.0**. **Actual difference**: For the same 4 mm² copper conductor, free-air ampacity is approximately **42 A (XLPE) or 35 A (PVC)**, while conduit-installed is approximately **30 A** — a **20% ~ 40% gap**. More conductors inside a conduit means greater derating; 3-core is 5% ~ 10% lower than 1-core. This is why GB 50054 recommends verifying calculations when conduit run exceeds 15 m or has more than 3 bends.

### Why do multiple parallel cables need derating?

When multiple cables are installed touching each other, their heat mutually reinforces, raising the ambient temperature collectively — derating is required. Parallel 2 cables ≈ 0.88, 3 cables 0.82, 4 cables 0.77, 6 cables 0.73 (typical values, varies by installation method). **Engineering对策**: When there are many circuits, **splitting to separate trays, layers, or busbars** is more economical than cramming them into one tray — it retains heat dissipation space while facilitating future maintenance and expansion.

### How does altitude affect ampacity?

Higher altitude means thinner air, poorer heat dissipation. GB 50217 Section 5.0.7 requires correction per Table 5.4.6. Example: 2000 m, K_h ≈ **0.94**; 3000 m, K_h ≈ **0.88** (GB 50217 Table 5.4.6, table-lookup values, non-linear). **Projects in Yunnan-Guizhou / Qinghai-Tibet must check altitude**; plain projects may default to K_h = 1.0. Note that GB Table 5.4.6 is equivalent to IEC Table B.52.16, but differs from the simple "every 100 m derate 0.4%" linear derivation — for engineering audits, directly reference the standard table.

### How do cable ampacity and circuit breaker setting current match?

Strictly per GB 50054-2011, the circuit breaker's rated current must satisfy **I_n ≤ I_z** (equal or smaller — this is the hard constraint in GB 50054-2011 Section 6.3.1). For engineering experience with 1.3× overload coordination (e.g., motor starting special scenarios), also verify **1.45 × I_z trip current** (GB 50054 Section 6.3.4). Example: Corrected ampacity 100 A — set circuit breaker at 100 A or 80 A; **do not select 125 A for long-term operation**. Short-circuit protection is a separate calculation: the breaker's instantaneous setting must clear cable short-circuit thermal stability — this is covered by the circuit breaker sizing tool.

### Which standard should I use — GB 50217 or IEC 60364?

**For domestic power engineering, GB 50217 is preferred**; for building electrical, GB 50054 is a useful reference. **For overseas/export projects**, IEC 60364-5-52 is more universally recognized — some Africa and Southeast Asia project bid documents directly cite IEC. The I₀ tables of both standards differ minimally (±5%), and the correction factor logic is consistent — either standard is acceptable in actual engineering, but the key is **using one standard consistently throughout** — do not mix GB for cable selection with IEC for breaker sizing. Mixing the two standards' correction formulas in one project creates audit disputes.

### How is the temperature correction factor calculated?

Based on the conductor allowable operating temperature θ_n and the actual ambient temperature θ_a, values come from GB 50217 Table E.0.1 (25°C base). Simplified formula (for understanding, not direct table lookup): `K_θ = √((θ_n - θ_a) / (θ_n - 25))`. Example: XLPE (θ_n = 90), ambient 40°C → K_θ ≈ **0.87**; ambient 35°C → K_θ ≈ **0.91** (table-lookup values per GB 50217 Table E.0.1). PVC insulation (θ_n = 70) uses the same formula, just with a lower temperature rating and faster derating. **The tool directly provides table values** — no manual calculation needed.

---

## Disclaimer

**Important**: Ampacity data provided by this tool is based on **simplified calculations from the annex tables of GB 50217-2018**, for **engineering estimation only**.

Actual engineering design must:

1. Use the latest published GB 50217 national standard as the authoritative source
2. Obtain a formal calculation sheet from a design institute / registered electrical engineer
3. Special scenarios (chemical corrosion, hazardous areas, offshore wind power, subway) require additional industry standard references

This tool **does not provide** automatic cable sizing recommendations and **does not replace** professional engineering judgment. This tool assumes no liability for any engineering incidents resulting from the use of this tool's data.

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
<title>Cable Current-Carrying Capacity Lookup | YJV/YJV22 Online Reference — elec.webpenson.com</title>
<meta name="description" content="Online cable ampacity lookup tool supporting YJV/YJLV/VV/BVR and other cable types. Covers 5 installation methods: free-air, conduit, tray, direct burial, and duct. Automatically applies GB 50217 temperature, grouping, and altitude correction factors." />
<meta name="keywords" content="cable ampacity lookup,YJV cable ampacity,YJV22 ampacity table,cable ampacity reference,GB 50217 cable ampacity,conduit cable ampacity,cable ampacity correction factors" />
<meta name="robots" content="index,follow" />
<meta name="author" content="elec.webpenson.com" />
<meta name="viewport" content="width=device-width, initial-scale=1" />

<!-- Open Graph -->
<meta property="og:type" content="website" />
<meta property="og:title" content="Cable Current-Carrying Capacity Lookup | YJV/YJV22 Online Reference" />
<meta property="og:description" content="Online cable ampacity lookup tool supporting YJV/YJLV/VV/BVR and other cable types. 5 installation methods + GB 50217 four correction factors." />
<meta property="og:url" content="https://elec.webpenson.com/tools/cable-current-carrying-capacity-lookup/" />
<meta property="og:site_name" content="elec.webpenson.com" />
<meta property="og:locale" content="en_US" />
<meta property="og:image" content="https://elec.webpenson.com/og/cable-current-carrying-capacity-lookup.png" />

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Cable Current-Carrying Capacity Lookup | YJV/YJV22 Online Reference" />
<meta name="twitter:description" content="Online cable ampacity lookup tool, 5 installation methods + GB 50217 four correction factors." />
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

- IEC 60364-5-52 Low-voltage Electrical Installations - Selection of Cables
- NEC 310.15 Ampacities of Conductors
