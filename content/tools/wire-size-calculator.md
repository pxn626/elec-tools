---
title: "Wire Size Calculator — NEC AWG & kcmil Sizing"
description: "Free NEC-aware wire size calculator. Enter amps, voltage, distance & material — get AWG/kcmil with ampacity + 75 °C correction in seconds. No signup."
slug: wire-size-calculator
categories:
  - "Electrical Tools"
  - "Wire Sizing"
  - "NEC 310"
tags:
  - "wire size calculator"
  - "AWG"
  - "NEC 310.16"
  - "electrical calculator"
  - "wire gauge"
  - "ampacity"
  - "copper aluminum"
  - "EV charger"
  - "subpanel"
  - "solar PV"
translationKey: "wire_size_calculator"
---

{{< wire-size-calculator >}}

## What size wire do I need?

**Wire Size Calculator — sized right, NEC right.** Pick the correct
copper or aluminum conductor for any residential, commercial, or
industrial branch circuit in seconds. This **NEC-aware wire size
calculator** uses the **75 °C ampacity column from NEC Table 310.16**
and applies temperature-correction and conduit-fill adjustment factors
per **NEC 310.15(B)** — the same numbers your inspector checks. Enter
load amps (or watts + volts), system voltage, one-way run length, and
wire material; the tool returns the smallest compliant AWG or kcmil,
the temperature-corrected ampacity, and a **NEC 240.4(B) round-up
flag** if the next-larger size is required for overcurrent
coordination. **Built for licensed electricians, EV-charger installers,
solar-PV designers, and DIY homeowners pulling a permit.** No signup,
no ads, no email gate.

### Why this wire size calculator?

- **NEC 310.16 compliant** — calculates copper & aluminum conductor sizes using the 75 °C ampacity column (the inspector-favored terminal rating per NEC 110.14(C)).
- **Covers 14 AWG to 750 kcmil** — from a single 15-amp lighting branch circuit to a 600-amp service entrance, in one calculator.
- **EV-charger, subpanel & solar presets** — one-click sizing for 30/40/50/60/100 amp services, 11 kW/22 kW Level-2 EV chargers, and 12V/24V/48V PV DC runs.
- **Temperature & conduit-fill correction** — applies NEC 310.15(B) ambient-temperature adjustment factors (30 °C / 35 °C / 40 °C / 45 °C) and conduit-fill derating (more than 3 current-carrying conductors).
- **Voltage-drop check built-in** — instantly shows the % drop at the recommended size and warns if you cross NEC 3 % branch / 5 % feeder limits; one-click link to our full voltage-drop calculator.

## How to use this wire size calculator

1. **Choose a preset or enter your load manually.** Start with the
   "Quick Presets" chips at the top for instant EV-charger, subpanel,
   service, dryer, or range sizing — or enter load amps directly. For
   three-phase motors, enter kW first then let the calculator convert
   to FLA via our [three-phase power calculator](/tools/three-phase-power-calculator/).

2. **Set the system conditions.** Pick system voltage (120 / 208 / 220 /
   240 / 277 / 347 / 480 / 600 V), phase (1Φ or 3Φ), and one-way run
   length in feet. The round-trip voltage drop is computed as 2× the
   one-way length.

3. **Pick the wire material and environment.** Toggle between copper
   and aluminum. Set ambient temperature (default 30 °C) and the
   number of current-carrying conductors in the conduit — both feed
   the NEC 310.15(B)(1) temperature correction and NEC 310.15(C)(1)
   conduit-fill adjustment.

4. **Flag continuous loads.** EV chargers, solar PV inverters, and
   some motor loads are continuous (NEC 210.20(A) / 215.3 / 625) and
   require the conductor + breaker to be sized to **125 % of the load**.
   Check the "Continuous load" box or pick an EV / solar preset to
   auto-enable it.

5. **Read the result card.** The 3-column card shows the recommended
   AWG / kcmil, the corrected ampacity, the recommended OCPD size,
   and the voltage-drop percentage. The compliance badge at the top
   goes 🟢 GREEN (fully compliant), 🟡 YELLOW (compliant but
   voltage drop marginal), or 🔴 RED (does not meet NEC — upsize).

6. **Cross-check with the voltage-drop calculator.** If the V-drop
   card flags a yellow or red, click through to our full
   [voltage drop calculator](/tools/voltage-drop-calculator/) for
   length-by-gauge and ambient temperature sensitivity analysis.
   Then pair the conductor with the breaker using our
   [circuit breaker sizing calculator](/tools/circuit-breaker-sizing-calculator/).

### NEC wire sizing basics

NEC wire sizing rests on three pillars. **First, ampacity** — the
maximum current a conductor can carry continuously without exceeding
its insulation temperature rating — is defined per NEC Table 310.16
for each AWG / kcmil size, with separate columns for 60 °C, 75 °C,
and 90 °C insulation. The **75 °C column** is the inspector-favored
reference for circuits rated 100 A or less (NEC 110.14(C)).

**Second, derating.** Base ampacity assumes 30 °C ambient and at
most three current-carrying conductors in the conduit. Higher
ambient temperatures apply NEC 310.15(B)(1) correction factors;
more than three current-carrying conductors apply NEC 310.15(C)(1)
adjustment factors (0.80 for 4–6 conductors, 0.70 for 7–9, and so on).

**Third, overcurrent protection coordination.** The breaker must not
exceed the conductor's corrected ampacity — except where NEC 240.4(B)
permits the next-larger standard OCPD when no standard OCPD matches
the conductor ampacity.

## NEC ampacity reference (Table 310.16, 75 °C column)

This table is the **inspector-favored reference** for ampacity in
the US — every AWG / kcmil from 14 AWG through 750 kcmil, copper and
aluminum, 75 °C terminal-rating column per NEC 110.14(C). Cross-check
the recommended conductor against this table, or look up an existing
conductor's corrected ampacity with our
[cable ampacity lookup](/tools/cable-current-carrying-capacity-lookup/).

| AWG / kcmil | Copper (A) | Aluminum (A) | Ω/1000 ft @ 75 °C (Cu) |
|-------------|-----------:|-------------:|------------------------:|
| 14 AWG      | 20         | —            | 3.14                    |
| 12 AWG      | 25         | —            | 1.98                    |
| 10 AWG      | 35         | —            | 1.24                    |
| 8 AWG       | 50         | 40           | 0.778                   |
| 6 AWG       | 65         | 50           | 0.491                   |
| 4 AWG       | 85         | 65           | 0.308                   |
| 3 AWG       | 100        | 75           | 0.245                   |
| 2 AWG       | 115        | 90           | 0.194                   |
| 1 AWG       | 130        | 100          | 0.154                   |
| 1/0 AWG     | 150        | 120          | 0.122                   |
| 2/0 AWG     | 175        | 135          | 0.0967                  |
| 3/0 AWG     | 200        | 155          | 0.0766                  |
| 4/0 AWG     | 230        | 180          | 0.0608                  |
| 250 kcmil   | 255        | 205          | 0.0515                  |
| 300 kcmil   | 285        | 230          | 0.0429                  |
| 350 kcmil   | 310        | 250          | 0.0367                  |
| 400 kcmil   | 335        | 270          | 0.0321                  |
| 500 kcmil   | 380        | 310          | 0.0258                  |
| 600 kcmil   | 420        | 340          | 0.0214                  |
| 750 kcmil   | 475        | 385          | 0.0171                  |

Source: NFPA 70 — National Electrical Code 2023, Table 310.16 (75°C
column). Use this table to verify the calculator's output or look up
an existing conductor's corrected ampacity.

## Wire size for common services (presets)

The calculator ships with one-click presets for the most common
residential, commercial, and light-industrial circuits. Each preset
auto-fills the inputs and returns the smallest NEC-compliant
conductor. For service-entrance sizing (100 A / 200 A), pair the
recommended conductor with the breaker per NEC 240.4(B) using our
[circuit breaker sizing calculator](/tools/circuit-breaker-sizing-calculator/).

### 30 A dryer circuit
NEC 220.54 — standard 30 A dryer receptacle (10-30R) on a 30 A
breaker. Typical run 35 ft at 120/240 V → **10 AWG copper** + 30 A
breaker. Larger gauge is rarely needed; verify with your local AHJ.

### 40 A electric range circuit
NEC 220.55 demand Table — 40 A range receptacle (14-50R). Typical
run 35 ft at 120/240 V → **8 AWG copper** + 40 A breaker.

### 50 A RV / subpanel feeder
NEC 215.2 / 551.71 — 50 A subpanel feeder (detached garage,
workshop) or RV pedestal. Typical run 75 ft at 120/240 V → **6 AWG
copper** + 50 A breaker (or **4 AWG aluminum**).

### 60 A EV charger (Level 2, 11 kW)
NEC 625.41 + 210.20(A) — 48 A continuous-load Level-2 EV charger.
125 % rule → conductor rated 60 A minimum → **4 AWG copper** + 60 A
breaker. Verify the charger's actual demand with the
[EV charging power calculator](/tools/charging-power-calculator/).

### 100 A subpanel feeder
NEC 215.2(A)(1) — detached-building subpanel fed at 100 A. Typical
run 100 ft at 120/240 V → **3 AWG copper** + 100 A breaker.

### 200 A service entrance
NEC 230.42 — modern residential service entrance. Typical run 75 ft
at 120/240 V → **3/0 AWG copper** + 200 A breaker (or **4/0 AWG
aluminum**).

### Solar / PV (12V / 24V / 48V DC)
NEC 690.8 + 210.20(A) — off-grid PV battery circuit, 30 A continuous
load → **8 AWG copper** with 40 A OCPD. For grid-tied PV inverters
with step-up transformers, size the upstream transformer with our
[transformer capacity selection calculator](/tools/transformer-capacity-selection/).

## Copper vs aluminum wire sizing

Aluminum has approximately **61 % the conductivity of copper** by
cross-sectional area, so to carry the same ampacity you must step up
roughly **two AWG sizes**. A 6 AWG copper conductor (65 A) is roughly
equivalent to a 4 AWG aluminum conductor (65 A). NEC 310.6 permits
aluminum building wire only at 8 AWG and larger; 12 AWG and 10 AWG
aluminum are restricted to specific applications like transformer
secondaries.

Aluminum is widely used for service entrance and large feeders
because it costs 30–50 % less per amp than copper, but it requires
antioxidant joint compound (per NEC 110.14) and CU/AL-rated terminals
to prevent galvanic corrosion at the termination. For EV-charger and
subpanel branch circuits, copper is the de-facto standard — see our
[EV charging time calculator](/tools/charging-time-calculator/) for
EV-specific scenarios, or estimate the operating cost of the load
with our [electricity cost calculator](/tools/electricity-cost-calculator/).

## Frequently asked questions

### What size wire do I need for a 100 amp service?
For a 100 A residential service entrance (NEC 230), the typical
minimum is **3 AWG copper** or **1 AWG aluminum** for a 120/240 V
single-phase run under 100 ft, after NEC 310.15(B) temperature-
correction. For runs over 150 ft, bump up one AWG to stay under 3 %
voltage drop. Always verify with your local AHJ.

### What size wire for a 50 amp subpanel?
A 50 A subpanel feeder (NEC 215) typically requires **6 AWG copper**
or **4 AWG aluminum**, with an **8 AWG copper equipment grounding
conductor**. Use the calculator above to confirm for your exact run
length and conduit-fill conditions.

### What wire size for a Level-2 (40-50 A) EV charger?
A 40 A continuous-load EV charger (NEC 625) requires a conductor
rated **125 % of the load** → 50 A minimum → typically **6 AWG
copper** with a **50 A breaker**. For a 48 A / 11 kW charger:
**4 AWG copper** with a **60 A breaker**. For a 50 A / 12 kW charger:
**4 AWG copper** with a **50 A breaker** — verify the terminal rating
(75 °C).

### How do I size aluminum wire vs copper?
Aluminum has about **61 %** the conductivity of copper, so for the
same ampacity you typically go **two AWG sizes larger** (e.g.
**6 AWG copper ≈ 4 AWG aluminum**). Aluminum is common for service
entrance and large feeders (above 6 AWG equivalent) but is restricted
for branch circuits in many jurisdictions (NEC 310.6).

### What is the NEC 240.4(B) round-up rule?
NEC 240.4(B) says the next-larger standard overcurrent device (OCPD)
is permitted **only** if the ampacity of the conductor does not
correspond to a standard OCPD size AND the next-larger OCPD is no
more than **800 A**. In practice this means: if your load calculation
lands on a non-standard ampacity, the conductor must be sized to the
next standard OCPD — the calculator flags this automatically.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Wire Size Calculator",
  "applicationCategory": "UtilitiesApplication",
  "operatingSystem": "Web",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  },
  "description": "NEC 310.16-compliant wire size calculator for copper and aluminum circuits, 14 AWG through 750 kcmil."
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to use the wire size calculator",
  "step": [
    {
      "@type": "HowToStep",
      "name": "Enter the load",
      "text": "Enter load amps directly, or use the kW + voltage fields for a quick conversion."
    },
    {
      "@type": "HowToStep",
      "name": "Set the run conditions",
      "text": "Set system voltage, phase, wire material, run length, ambient temperature, and the number of current-carrying conductors in the conduit."
    },
    {
      "@type": "HowToStep",
      "name": "Read the result",
      "text": "The calculator returns the smallest NEC-compliant AWG or kcmil, the temperature-corrected and conduit-fill-adjusted ampacity, and a recommended breaker (OCPD) size. The voltage-drop card flags whether the run meets the NEC 3% branch / 5% combined limit."
    }
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
      "name": "What size wire do I need for a 100 amp service?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "For a 100 A residential service entrance (NEC 230), the typical minimum is 3 AWG copper or 1 AWG aluminum for a 120/240 V single-phase run under 100 ft, after NEC 310.15(B) temperature-correction. For runs over 150 ft, bump up one AWG to stay under 3 % voltage drop. Always verify with your local AHJ."
      }
    },
    {
      "@type": "Question",
      "name": "What size wire for a 50 amp subpanel?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A 50 A subpanel feeder (NEC 215) typically requires 6 AWG copper or 4 AWG aluminum, with an 8 AWG copper equipment grounding conductor. Use the calculator above to confirm for your exact run length and conduit-fill conditions."
      }
    },
    {
      "@type": "Question",
      "name": "What wire size for a Level-2 (40-50 A) EV charger?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A 40 A continuous-load EV charger (NEC 625) requires a conductor rated 125 % of the load → 50 A minimum → typically 6 AWG copper with a 50 A breaker. For a 48 A / 11 kW charger: 4 AWG copper with a 60 A breaker. For a 50 A / 12 kW charger: 4 AWG copper with a 50 A breaker — verify the terminal rating (75 °C)."
      }
    },
    {
      "@type": "Question",
      "name": "How do I size aluminum wire vs copper?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Aluminum has about 61 % the conductivity of copper, so for the same ampacity you typically go two AWG sizes larger (e.g. 6 AWG copper ≈ 4 AWG aluminum). Aluminum is common for service entrance and large feeders (above 6 AWG equivalent) but is restricted for branch circuits in many jurisdictions (NEC 310.6)."
      }
    },
    {
      "@type": "Question",
      "name": "What is the NEC 240.4(B) round-up rule?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NEC 240.4(B) says the next-larger standard overcurrent device (OCPD) is permitted only if the ampacity of the conductor does not correspond to a standard OCPD size AND the next-larger OCPD is no more than 800 A. In practice this means: if your load calculation lands on a non-standard ampacity, the conductor must be sized to the next standard OCPD — the calculator flags this automatically."
      }
    }
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://elec.webpenson.com/" },
    { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://elec.webpenson.com/tools/" },
    { "@type": "ListItem", "position": 3, "name": "Wire Size Calculator", "item": "https://elec.webpenson.com/tools/wire-size-calculator/" }
  ]
}
</script>