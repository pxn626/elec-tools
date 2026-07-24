---
title: "Circuit Breaker Size Calculator — NEC 240 / 430 OCPD Sizing"
description: "Free NEC-aware circuit breaker calculator. Enter amps or kW, get the OCPD per NEC 240.6(A) + 240.4(B) + 125% rule. EV, subpanel, motor presets. No signup."
slug: circuit-breaker-sizing-calculator
categories:
  - "Electrical Tools"
  - "NEC 240"
  - "OCPD Sizing"
  - "Breaker Selection"
tags:
  - "circuit breaker calculator"
  - "breaker sizing"
  - "NEC 240.6"
  - "NEC 240.4(B)"
  - "NEC 430.52"
  - "NEC 210.20(A)"
  - "OCPD"
  - "motor breaker"
  - "EV charger breaker"
  - "subpanel feeder"
translationKey: "circuit_breaker_sizing_calculator"
---

{{< circuit-breaker-sizing-calculator >}}

> **TL;DR — What this calculator returns.** Enter load amps or kW (resistive / general), or motor HP (NEC 430 branch circuit) — the tool returns the recommended overcurrent protective device (OCPD / breaker) sized per **NEC 240.6(A)** standard ratings, with **NEC 240.4(B) next-larger OCPD logic** when no standard OCPD matches the conductor ampacity, and the **NEC 210.20(A) / 215.3 / 625 125 % continuous-load rule** applied automatically when the load runs more than 3 hours. For motor branch circuits, the tool follows **NEC 430.52** (inverse-time breaker = 250 % of FLA for NEMA Design A/B, 150 % for Design C/E). 100 % client-side, no signup, no upload.

## What size breaker do I need?

A circuit breaker size calculator solves one specific problem: **given a load, find the smallest NEC-compliant standard breaker that will protect the conductor without nuisance tripping**. The answer depends on three pieces of information — running amps, whether the load is *continuous* (NEC Article 100: expected to run 3 hours or more), and which NEC Article applies to your circuit type.

For most residential and small-commercial branch circuits, the chain is **NEC 240.4 → 240.6(A) → 210.20(A)** — conductor ampacity is matched to one of the 27 standard OCPD sizes listed in NEC 240.6(A), and a 125 % multiplier is layered on when the load is continuous (EV chargers, commercial lighting, storage heaters). For motor branch circuits the chain is fundamentally different: **NEC 430.52 → Table 430.250 (3Φ) / Table 430.6 (1Φ) → 250 % or 150 % multiplier** depending on NEMA/IEC design letter. For service-entrance and feeder conductors the chain is **NEC 215.3 → 220** (demand factors optional). And for hot tubs, spas, and pool equipment, **NEC 680** layers GFCI protection onto the sizing chain.

**The most common inspector question on a permit drawing is: "What NEC Article sized this breaker?"** This calculator answers that question in line with the result card — every recommended OCPD is tagged with the Article (240.6(A), 240.4(B), 210.20(A), 430.52, etc.) that produced it. Once you have the breaker size, pair the breaker with the conductor using our [Wire Size Calculator](/tools/wire-size-calculator/) — that's the second half of the NEC 110.14(C) + 240.4(B) pairing flow.

## Why this circuit breaker calculator?

Most online breaker-sizing tools return "round to the nearest 5 A," which is **not NEC-compliant** — inspectors reject non-standard OCPD sizes during plan review. This calculator is built around the actual NEC 2023 NFPA-70 logic, not around a smoothing function. Six things make it different:

### Standard OCPD ladder (NEC 240.6(A))

NEC 240.6(A) lists exactly **27 standard ratings** in amperes: 15, 20, 25, 30, 35, 40, 45, 50, 60, 70, 80, 90, 100, 110, 125, 150, 175, 200, 225, 250, 300, 350, 400, 450, 500, 600, 700, 800. Anything else — including "55 A breaker" — is non-standard and will be rejected on a permit drawing. The calculator always returns a value from this list, with no rounding exceptions.

### Round-up logic (NEC 240.4(B))

NEC 240.4(B) permits the **next-larger standard OCPD** *only* when no standard OCPD corresponds to the conductor ampacity (the next-larger OCPD is also capped at 800 A). For example, 6 AWG copper at 75 °C terminal rating has an ampacity of 65 A — the next standard OCPD larger than 55 A is 60 A, which is permitted. But 50 A conductor + 50 A OCPD is already a direct match — bumping that to 60 A is an *over-size*, not a 240.4(B) round-up. The calculator surfaces this distinction with a 🟢 / 🟡 / 🔴 compliance badge.

### Continuous-load 125 % rule (NEC 210.20(A) / 215.3 / 625)

A continuous load (NEC 100 definition: expected to run ≥ 3 hours) requires **OCPD ≥ 1.25 × load**. EV chargers, solar PV inverters, battery storage PCS units, and most commercial lighting all trigger this rule. The calculator applies it by default for EV-charger presets and exposes a checkbox for manual entries. *(Note: NEC 215.3 governs feeder OCPD sizing; the 125 % multiplier is identical on both sides of the service.)*

### Motor branch-circuit path (NEC 430.52)

NEC 430.52 sizes OCPD for motors using **FLA × multiplier**, where **FLA** comes from NEC Table 430.250 (3-phase) or Table 430.6 (single-phase) and the multiplier depends on NEMA design letter: **Design A or B = 250 % of FLA**, **Design C or E = 150 % of FLA**, **Design D = 150 % of FLA** (verify against the manufacturer's OCPD list for Design D). Most breaker-sizing calculators skip this path entirely; the calculator handles it as a dedicated tab.

### Wire-size pairing (NEC 110.14(C))

NEC 110.14(C) requires conductor terminations to be rated at not less than the OCPD rating — for OCPDs ≤ 100 A, the **75 °C column** of NEC Table 310.16 is the inspector-favored reference. The calculator flags the appropriate ampacity column and cross-links to the [Wire Size Calculator](/tools/wire-size-calculator/) for the conductor side of the pair.

### 100 % client-side, no signup

All math runs in your browser. No form submission, no account, no email collection, no upload. Verify with DevTools → Network tab: zero outbound traffic beyond the initial page load.

## How to use this circuit breaker calculator

The calculator has **two modes** (resistive/general load and motor branch circuit) and **ten presets** (30 A dryer, 40 A range, 50 A subpanel, 60 A EV charger, 100 A subpanel, 200 A service, 32/40/48 A EV charger variants, 10/25 HP motors). Pick a preset for a one-click answer, or enter load data manually.

### Step 1 — Choose a preset or enter load manually

Click any preset chip (e.g., **EV L2 48A (continuous)**) to fill the inputs and surface a result instantly. To enter manually, switch to **Resistive** mode and type your load amps (or kW) into the corresponding field. For motor branch circuits, click the **Motor Branch Circuit (NEC 430)** tab and enter motor HP + voltage + phase + design letter.

### Step 2 — Set voltage, phase, and power factor

In **Resistive** mode, choose system voltage (120 / 208 / 220 / 240 / 277 / 347 / 380 / 480 / 600 V), phase (1Φ or 3Φ), and power factor (default 0.95; pure resistive loads can use 1.0). Toggle the **Continuous load** checkbox for loads expected to run more than 3 hours — EV chargers, grid-tie PV inverters, and storage heaters all qualify. In **Motor** mode, set motor voltage, phase, and NEMA/IEC design letter (A, B, C, E, D); power factor is not used in NEC 430 sizing.

### Step 3 — Read the OCPD result card

The result card shows **three numbers**: running amps (the actual load current), design amps (running × 1.25 if continuous, otherwise running amps directly), and the **recommended OCPD** — the smallest NEC 240.6(A) standard rating ≥ design amps. Below the OCPD number, a compliance badge indicates which rule fired:

- 🟢 **NEC 240.6(A) Direct Match** — running amps already align with a standard OCPD; no round-up required.
- 🟢 **NEC 240.4(B) Round-Up Applied** — next-larger OCPD permitted because no standard OCPD matches the conductor ampacity.
- 🟡 **NEC 430.52 × 250 % Applied** — motor branch circuit, Design A/B (verify motor nameplate design letter).
- 🟡 **NEC 430.52 × 150 % Applied** — motor branch circuit, Design C/E.
- 🔴 **Exceeds 800 A** — design current exceeds the 240.4(B) 800 A cap; use parallel conductors (NEC 310.10(H)) or service-entrance equipment.

Below the badge, the formula trace (e.g., `48 A × 1.25 = 60 A → 240.6(A) → 60 A OCPD`) shows exactly how the result was derived, so you can cite the Article number on a permit drawing.

## NEC breaker sizing basics

The full NEC 240 + 430 + 210.20(A) chain is the spine of US residential, commercial, and industrial electrical work. The four sub-sections below cover each link in that chain with the formulas, tables, and Inspector Reference Tables an electrician actually needs on the job site.

### NEC 240.6(A) standard sizes

NEC 240.6(A) lists the **standard ampere ratings** for fuses and inverse-time breakers. Only these sizes are permitted on a permit drawing:

| Standard OCPD size (A) | Common application |
|---:|---|
| 15 | General lighting / receptacle circuits (NEC 210.3) |
| 20 | Kitchen / bathroom / laundry receptacles (NEC 210.11(C)) |
| 30 | Electric dryer branch circuit (NEC 220.54) |
| 40 | Electric range branch circuit (NEC 220.55) |
| 50 | RV outlet / subpanel feeder (NEC 551) |
| 60 | Level-2 EV charger (48 A continuous, NEC 625) |
| 70 | Small workshop subpanel |
| 80 | Mid-size heat-pump / large air handler |
| 90 | 25 HP Design B motor (FLA × 250 % round-up) |
| 100 | Subpanel feeder / service entrance (small residence) |
| 125 | Larger subpanel feeder |
| 150 | Heat-pump / commercial subpanel |
| 175 | Commercial subpanel |
| 200 | Service entrance (typical residence) |
| 225 | Service entrance (mid-size residence) |
| 250 | Service entrance (large residence / small commercial) |
| 300 – 350 | Small commercial service entrance |
| 400 – 450 | Mid-size commercial service entrance |
| 500 – 600 | Large commercial service entrance |
| 700 – 800 | Industrial service entrance / parallel-feeder protection (NEC 240.4(B) cap) |

### NEC 240.4(B) next-larger rule

NEC 240.4(B) is the most-misunderstood article in residential wiring. The verbatim text says: *"The next higher standard rating of overcurrent device … shall be permitted for protection of conductors … where the ampacity of the conductors does not correspond to a standard ampere rating …"* — capped at **800 A**. Translated to the field:

- **Conductor sized at 50 A** (e.g., 6 AWG copper at 60 °C = 55 A or 75 °C = 65 A, designed against 50 A OCPD) → **50 A OCPD** is a direct match; no round-up. Bumping to 60 A is over-sizing and a code violation.
- **Conductor sized at 65 A** (6 AWG copper at 75 °C terminal rating) → no 65 A OCPD exists; round up to **70 A OCPD** (the next standard).
- **Conductor sized at 110 A** (e.g., 1 AWG copper at 75 °C = 130 A, designed for a 100 A subpanel but corrected to 110 A) → no 110 A OCPD exists; round up to **125 A OCPD**.

The rule does **not** apply if a standard OCPD already matches the conductor ampacity. The calculator surfaces this distinction with a 🟢 direct-match badge vs. a 🟡 round-up badge.

### NEC 210.20(A) / 215.3 continuous-load rule

NEC 210.20(A) governs branch-circuit OCPD sizing; NEC 215.3 governs feeder OCPD sizing. Both apply the same 125 % multiplier when the load is **continuous** (expected to run ≥ 3 hours, per NEC Article 100):

OCPD ≥ 1.25 × non-continuous load + continuous load

For a single-load continuous circuit, this simplifies to **OCPD ≥ 1.25 × full load**. Worked examples:

- **32 A continuous (Level-2 EV charger, 7.7 kW)** → 32 × 1.25 = 40 → **40 A OCPD** (direct match).
- **40 A continuous (Level-2 EV charger, 9.6 kW)** → 40 × 1.25 = 50 → **50 A OCPD** (direct match).
- **48 A continuous (Level-2 EV charger, 11.5 kW)** → 48 × 1.25 = 60 → **60 A OCPD** (direct match).

EV charging (NEC 625) is **always** treated as continuous by modern AHJ interpretation — that interpretation is the standard across the US and Canada.

### NEC 430.52 motor branch-circuit sizing

NEC 430.52 sizes OCPD for motors using **FLA × multiplier**:

- **Design A or B** (most common, NEMA standard): **250 % of FLA** on an inverse-time breaker.
- **Design C or E** (high starting torque, IEC high-efficiency): **150 % of FLA**.
- **Design D** (very high locked-rotor current): **150 % of FLA**, then verify against the manufacturer's published OCPD list.

Worked example — a **460 V 3-phase 25 HP Design B motor**: FLA from NEC Table 430.250 = 34 A; 34 × 2.50 = 85 A; next standard OCPD = **90 A**. Per NEC 430.52(C)(1) Exception 1, the next-larger standard OCPD is permitted when the calculated value doesn't match a standard. For motor feeder overcurrent protection, see NEC 430.62 (a different calculation); this calculator focuses on branch-circuit OCPD only.

### NEC 220 demand-factor pairing (advanced)

For services and subpanel feeders in residential and small-commercial work, NEC 220 demand factors can reduce the design load below the nameplate sum. NEC Table 220.55 (range demand) and 220.82 (optional method, single-family residence) are common. The calculator exposes a **demand-factor toggle** in advanced mode — apply a percentage (e.g., 0.65 for 12 kW range demand) to scale design amps before the 240.6(A) match. This is the only calculator in the cluster that surfaces demand-factor math explicitly; the other tools expect nameplate inputs.

## Breaker size for common services (presets)

The presets below pre-fill the calculator inputs with typical residential / small-commercial values. Click any preset for a one-click answer; the result card carries the NEC Article number for permit review.

### 30 A dryer circuit

A 240 V 24 A dryer (nameplate FLA, NEC 220.54 demand = 5,000 VA or 24 A minimum) → non-continuous → 24 A design amps → next standard OCPD = **30 A**. Pair with **10 AWG copper** (75 °C ampacity 35 A) on a 30 A 2-pole breaker. Verify with the dryer nameplate — modern dryers with steam cycles may draw 30 A continuously and require a **40 A OCPD** under NEC 210.20(A).

### 40 A electric range circuit

A 240 V 33 A electric range (NEC Table 220.55 demand applied to the nameplate) → non-continuous in most jurisdictions → 33 A design amps → next standard OCPD = **40 A**. Pair with **8 AWG copper** (75 °C ampacity 50 A) on a 40 A 2-pole breaker. Range hoods and warming drawers on the same circuit may push the load into continuous-load territory — check with the AHJ.

### 50 A RV / subpanel feeder

A 240 V 50 A RV outlet (NEC 551) or small subpanel feeder → non-continuous (typical intermittent RV use) → 50 A direct match → **50 A OCPD**. Pair with **6 AWG copper** (75 °C ampacity 65 A) on a 50 A 2-pole breaker. For a continuous-load subpanel (one that feeds an EV charger downstream, for example), bump to **60 A OCPD** under NEC 210.20(A).

### 60 A EV charger (Level 2, 11 kW)

Level-2 EV charging is **always continuous** (NEC 625 + 210.20(A)). A 48 A continuous load (a typical 11 kW Level-2 unit: Tesla, ChargePoint, JuiceBox, Emporia) → 48 × 1.25 = 60 → **60 A OCPD** (direct match). Pair with **4 AWG copper** (75 °C ampacity 85 A) on a 60 A 2-pole breaker. Always check the charger nameplate for actual FLA — some Level-2 units are 40 A continuous (requires 50 A OCPD) or 32 A continuous (requires 40 A OCPD). Verify the charger's actual demand with our [EV Charging Power Calculator](/tools/charging-power-calculator/).

### 100 A subpanel feeder

A 240 V 100 A subpanel feeder serving a workshop or detached garage → typically non-continuous at the feeder level (NEC 215.3) → 100 A direct match → **100 A OCPD**. Pair with **3 AWG copper** or **1 AWG aluminum** on a 100 A 2-pole breaker. For subpanels that feed continuous loads downstream (EV chargers, PV inverters), apply the 125 % multiplier at the **load** level, not at the feeder; feeder amps remain 100 A.

### 200 A service entrance

A 240 V 200 A residential service entrance → typically non-continuous at the service level when calculated per NEC 220.82 optional method → 200 A direct match → **200 A OCPD**. Pair with **2/0 AWG copper** or **4/0 AWG aluminum** on a 200 A 2-pole main breaker. For all-electric residences with continuous loads (PV inverter + EV + heat-pump compressor running simultaneously), check with the AHJ — some jurisdictions require **320 A or 400 A service** to keep feeder OCPDs under the 80 % continuous-load rule.

### 10 kW / 25 kW motor branch circuits

NEC 430.52 motor branch-circuit OCPD sizing — fundamentally different from resistive loads.

- **460 V 3-phase 10 HP Design B motor** → FLA = 14 A (NEC Table 430.250) → 14 × 2.50 = 35 → next standard OCPD = **35 A**. Pair with **8 AWG copper** (75 °C ampacity 50 A, NEC 110.14(C) ≥ 35 A OCPD).
- **460 V 3-phase 25 HP Design B motor** → FLA = 34 A → 34 × 2.50 = 85 → next standard OCPD = **90 A**. Pair with **3 AWG copper** (75 °C ampacity 100 A).
- **230 V 3-phase 25 HP Design C motor** → FLA = 68 A → 68 × 1.50 = 102 → next standard OCPD = **110 A**. Pair with **1 AWG copper** (75 °C ampacity 130 A).

For the kW → FLA pre-step, use our [Three-Phase Power Calculator](/tools/three-phase-power-calculator/).

## Wire size ↔ breaker size pairing (NEC 240.4(B))

The breaker and the conductor are **a paired system** — the breaker protects the conductor by tripping before the conductor overheats, and the conductor must be sized to carry the load without exceeding its insulation rating. NEC 110.14(C) + 240.4(B) govern the pair. The pairing table below maps typical NEC 240.6(A) breakers to the smallest 75 °C-rated copper conductor that satisfies both rules:

| OCPD (A) | Min. copper conductor (75 °C) | Conductor ampacity (A) | 240.4(B) round-up? |
|---:|---|---|---|
| 15 | 14 AWG | 20 | 🟢 direct match |
| 20 | 12 AWG | 25 | 🟢 direct match |
| 30 | 10 AWG | 35 | 🟢 direct match |
| 40 | 8 AWG | 50 | 🟢 direct match |
| 50 | 6 AWG | 65 | 🟢 direct match |
| 60 | 4 AWG | 85 | 🟢 direct match |
| 70 | 4 AWG | 85 | 🟡 round-up from 65 A conductor ampacity |
| 80 | 4 AWG | 85 | 🟡 round-up |
| 90 | 3 AWG | 100 | 🟡 round-up |
| 100 | 3 AWG | 100 | 🟢 direct match |
| 125 | 1 AWG | 130 | 🟡 round-up |

### How to pair the breaker with the conductor

Once the calculator returns the OCPD size, jump to the [Wire Size Calculator](/tools/wire-size-calculator/) to size the conductor. The pairing flow is bidirectional — wire-size calculators should reference back to the recommended breaker (NEC 240.6(A) standard OCPD), and breaker-size calculators should reference the conductor that pairs with the OCPD. Pairing both directions is what makes a permit drawing inspector-friendly.

For motor branch circuits, the conductor is sized per NEC 430.22 (125 % of motor FLA — a different calculation from the OCPD-sizing path), so the breaker and conductor decisions are independent. Confirm both with the calculator pair.

## FAQ

Seven common questions an electrician or homeowner asks on the permit desk — answers cite the NEC Article so the citation line is copy-paste-able onto a drawing.

### What size breaker do I need for 50 amps?

A 50 A continuous load requires a **50 A standard OCPD** on a conductor rated at least 50 A (NEC 240.4). For a 50 A non-continuous load (a typical subpanel feeder or RV outlet), pair it with **6 AWG copper** (75 °C ampacity 65 A) and a **50 A breaker** — direct match, no round-up. For a 50 A continuous load, NEC 210.20(A) requires OCPD ≥ 125 % of load = 62.5 A, which round-ups to the next standard OCPD = **70 A** under NEC 240.4(B). Most 50 A subpanels are non-continuous, so the 50 A breaker is correct — verify with the actual load profile before pulling the permit.

### Can I use a 60 amp breaker on a 50 amp circuit?

**Yes — but only under specific NEC 240.4(B) conditions.** The "next-larger standard OCPD" rule permits a 60 A breaker on a conductor whose ampacity does not correspond to a standard OCPD — for example, a **6 AWG copper conductor at 75 °C ampacity = 65 A**, which has no standard OCPD match (50 A and 60 A bracket it). In that case, **60 A is the code-compliant choice**. The rule does NOT apply if a standard OCPD (50 A) already matches the conductor ampacity; using 60 A there would be an over-size violation. For continuous loads, NEC 210.20(A) still requires the 125 % multiplier first — a 50 A continuous load still needs a 70 A OCPD.

### What is the NEC 240.4(B) round-up rule?

**NEC 240.4(B)** — *Overcurrent protection of conductors* — states: *"The next higher standard rating of overcurrent device … shall be permitted for protection of conductors … where the ampacity of the conductors does not correspond to a standard ampere rating …"* — but the next-larger OCPD is **capped at 800 A**. In practice: round up to the next standard OCPD from NEC 240.6(A) **only when no standard OCPD exactly matches the conductor ampacity**. Conductor sized at 65 A (6 AWG / 75 °C) → 70 A OCPD. Conductor sized at 50 A → 50 A OCPD (direct match, no round-up). This rule is the most common source of inspector pushback — verify with the AHJ before permit submission.

### What size breaker for a Level-2 (40-50 A) EV charger?

For a Level-2 EV charger (NEC 625 + 210.20(A) — EV charging is a **continuous load**, defined as running ≥ 3 hours): **32 A continuous → 40 A breaker** (32 × 1.25 = 40 A direct match), **40 A continuous → 50 A breaker** (40 × 1.25 = 50 A direct match), **48 A continuous → 60 A breaker** (48 × 1.25 = 60 A direct match). Pair the breaker with our [Wire Size Calculator](/tools/wire-size-calculator/) to size the conductor: a 60 A EV charger typically needs **4 AWG copper** (75 °C ampacity 85 A, but verify with the charger nameplate and AHJ). Common 11 kW Level-2 units (Tesla, ChargePoint, JuiceBox) draw 48 A continuous — use the **60 A EV charger preset** in our calculator for a one-click answer. Verify the charger's actual demand with our [EV Charging Power Calculator](/tools/charging-power-calculator/).

### How do you size a breaker for a motor?

Motor branch-circuit OCPD sizing follows **NEC 430.52** — fundamentally different from resistive loads. The formula: **OCPD ≥ FLA × multiplier**, where **FLA** (full-load amps) comes from NEC Table 430.250 (3-phase) or Table 430.6 (single-phase), and **multiplier** depends on NEMA/IEC design letter: **Design A or B (most common)** = 250 % of FLA, **Design C or E** = 150 % of FLA, **Design D** = 150 % of FLA (verify against manufacturer OCPD list). Example: **460 V 3-phase 25 HP Design B motor** → FLA = 34 A → 34 × 2.5 = 85 A → next standard OCPD = **90 A**. Round-up to next-larger standard OCPD is permitted under NEC 430.52(C)(1) Exception 1. For motor feeder overcurrent protection, see NEC 430.62.

### What is NEC 240.6(A)?

**NEC 240.6(A)** — *Standard Ampere Ratings* — lists the **27 standard OCPD sizes** recognized by the National Electrical Code: **15, 20, 25, 30, 35, 40, 45, 50, 60, 70, 80, 90, 100, 110, 125, 150, 175, 200, 225, 250, 300, 350, 400, 450, 500, 600, 700, 800 A**. These are the only OCPD sizes you can specify on a permit drawing — anything else (e.g., "55 A breaker") is non-standard and will be rejected by the Authority Having Jurisdiction (AHJ). Our calculator always returns a value from this list, with NEC 240.4(B) round-up logic applied when the load exceeds the largest direct match below 800 A.

### What's the difference between NEC 210.20(A) and 215.3?

**NEC 210.20(A)** governs **branch-circuit OCPD sizing** — the breaker on a single load circuit (a 20 A kitchen receptacle, a 30 A dryer, a 60 A EV charger). **NEC 215.3** governs **feeder OCPD sizing** — the breaker on a subpanel feeder or service-entrance conductor (a 100 A subpanel feed, a 200 A service). Both articles apply the **125 % continuous-load rule** identically: OCPD ≥ 1.25 × non-continuous load + continuous load. The distinction matters for which conductor you're sizing — branch-circuit conductors per NEC 310.16 + 110.14(C) terminal ratings; feeder conductors per NEC 215.2 + 220 (demand factors may apply for feeders only). For a single-family residence, the 125 % rule is the same on both sides; the difference shows up in commercial / multi-family demand-factor math.

### What breaker for a hot tub (NEC 680)?

A 240 V hot tub typically draws **30 A continuous** (per nameplate) → NEC 210.20(A) + 680 require OCPD ≥ 30 × 1.25 = 37.5 A → next standard OCPD = **40 A**. Conductor: **6 AWG copper** (75 °C ampacity 65 A) on a 40 A or 50 A GFCI breaker (50 A is also common for hot tubs with larger heaters). The GFCI protection requirement is **NEC 680.44** — must be a GFCI breaker (not just a GFCI receptacle) for spa/hot tub installations. Verify with the manufacturer's installation manual — some 240 V hot tubs draw up to 50 A continuous and require a **60 A breaker + 4 AWG copper**.

## Related Tools

- **[Wire Size Calculator](/tools/wire-size-calculator/)** — pair the breaker with the conductor per NEC 110.14(C) + 240.4(B).
- **[Three-Phase Power Calculator](/tools/three-phase-power-calculator/)** — kW → FLA pre-step for NEC 430 motor branch circuits.
- **[EV Charging Power Calculator](/tools/charging-power-calculator/)** — verify the actual EV charger demand before sizing the OCPD.

---

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Circuit Breaker Size Calculator",
  "applicationCategory": "UtilitiesApplication",
  "operatingSystem": "Web",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
  "description": "NEC-aware circuit breaker sizing calculator. Sizes OCPD per NEC 240.6(A) standard ratings with 240.4(B) round-up logic, 210.20(A) continuous-load 125% rule, and NEC 430.52 motor branch-circuit path. Client-side only — no signup, no upload.",
  "url": "https://elec.webpenson.com/tools/circuit-breaker-sizing-calculator/"
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to size a circuit breaker per NEC 240 / 430",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "Choose a preset or enter load",
      "text": "Pick a preset (EV charger 32/40/48 A, 50 A subpanel, 100 A subpanel, 200 A service, dryer, range, motor) or enter load manually in amps or kW."
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "Set voltage, phase, and power factor",
      "text": "Select system voltage (120/208/220/240/277/347/380/480/600 V), phase (single or three-phase), power factor (default 0.95). For motor branch circuits, enter HP and NEMA/IEC design letter (A/B/C/E/D)."
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "Read the OCPD result card",
      "text": "The result card shows running amps, design amps (× 1.25 if continuous), and the recommended standard OCPD from NEC 240.6(A). Compliance badge indicates NEC 240.4(B) round-up or NEC 430.52 motor multiplier applied."
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
      "name": "What size breaker do I need for 50 amps?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A 50 A continuous load requires a 50 A standard OCPD on a conductor rated at least 50 A (NEC 240.4). For a 50 A non-continuous load (a typical subpanel feeder or RV outlet), pair it with 6 AWG copper (75 °C ampacity 65 A) and a 50 A breaker — direct match, no round-up. For a 50 A continuous load, NEC 210.20(A) requires OCPD ≥ 125% of load = 62.5 A, which round-ups to the next standard OCPD = 70 A under NEC 240.4(B). Most 50 A subpanels are non-continuous, so the 50 A breaker is correct — verify with the actual load profile before pulling the permit."
      }
    },
    {
      "@type": "Question",
      "name": "Can I use a 60 amp breaker on a 50 amp circuit?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes — but only under specific NEC 240.4(B) conditions. The next-larger standard OCPD rule permits a 60 A breaker on a conductor whose ampacity does not correspond to a standard OCPD — for example, a 6 AWG copper conductor at 75 °C ampacity = 65 A, which has no standard OCPD match (50 A and 60 A bracket it). In that case, 60 A is the code-compliant choice. The rule does NOT apply if a standard OCPD (50 A) already matches the conductor ampacity; using 60 A there would be an over-size violation. For continuous loads, NEC 210.20(A) still requires the 125% multiplier first — a 50 A continuous load still needs a 70 A OCPD."
      }
    },
    {
      "@type": "Question",
      "name": "What is the NEC 240.4(B) round-up rule?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NEC 240.4(B) — Overcurrent protection of conductors — states: the next higher standard rating of overcurrent device shall be permitted for protection of conductors where the ampacity of the conductors does not correspond to a standard ampere rating — but the next-larger OCPD is capped at 800 A. In practice: round up to the next standard OCPD from NEC 240.6(A) only when no standard OCPD exactly matches the conductor ampacity. Conductor sized at 65 A (6 AWG / 75 °C) → 70 A OCPD. Conductor sized at 50 A → 50 A OCPD (direct match, no round-up). This rule is the most common source of inspector pushback — verify with the AHJ before permit submission."
      }
    },
    {
      "@type": "Question",
      "name": "What size breaker for a Level-2 (40-50 A) EV charger?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "For a Level-2 EV charger (NEC 625 + 210.20(A) — EV charging is a continuous load, defined as running ≥ 3 hours): 32 A continuous → 40 A breaker (32 × 1.25 = 40 A direct match), 40 A continuous → 50 A breaker (40 × 1.25 = 50 A direct match), 48 A continuous → 60 A breaker (48 × 1.25 = 60 A direct match). Pair the breaker with the Wire Size Calculator to size the conductor: a 60 A EV charger typically needs 4 AWG copper (75 °C ampacity 85 A, but verify with the charger nameplate and AHJ). Common 11 kW Level-2 units (Tesla, ChargePoint, JuiceBox) draw 48 A continuous — use the 60 A EV charger preset in our calculator for a one-click answer. Verify the charger's actual demand with our EV Charging Power Calculator."
      }
    },
    {
      "@type": "Question",
      "name": "How do you size a breaker for a motor?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Motor branch-circuit OCPD sizing follows NEC 430.52 — fundamentally different from resistive loads. The formula: OCPD ≥ FLA × multiplier, where FLA (full-load amps) comes from NEC Table 430.250 (3-phase) or Table 430.6 (single-phase), and multiplier depends on NEMA/IEC design letter: Design A or B (most common) = 250 % of FLA, Design C or E = 150 % of FLA, Design D = 150 % of FLA (verify against manufacturer OCPD list). Example: 460 V 3-phase 25 HP Design B motor → FLA = 34 A → 34 × 2.5 = 85 A → next standard OCPD = 90 A. Round-up to next-larger standard OCPD is permitted under NEC 430.52(C)(1) Exception 1. For motor feeder overcurrent protection, see NEC 430.62."
      }
    },
    {
      "@type": "Question",
      "name": "What is NEC 240.6(A)?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NEC 240.6(A) — Standard Ampere Ratings — lists the 27 standard OCPD sizes recognized by the National Electrical Code: 15, 20, 25, 30, 35, 40, 45, 50, 60, 70, 80, 90, 100, 110, 125, 150, 175, 200, 225, 250, 300, 350, 400, 450, 500, 600, 700, 800 A. These are the only OCPD sizes you can specify on a permit drawing — anything else (e.g., 55 A breaker) is non-standard and will be rejected by the Authority Having Jurisdiction (AHJ). Our calculator always returns a value from this list, with NEC 240.4(B) round-up logic applied when the load exceeds the largest direct match below 800 A."
      }
    },
    {
      "@type": "Question",
      "name": "What's the difference between NEC 210.20(A) and 215.3?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NEC 210.20(A) governs branch-circuit OCPD sizing — the breaker on a single load circuit (a 20 A kitchen receptacle, a 30 A dryer, a 60 A EV charger). NEC 215.3 governs feeder OCPD sizing — the breaker on a subpanel feeder or service-entrance conductor (a 100 A subpanel feed, a 200 A service). Both articles apply the 125% continuous-load rule identically: OCPD ≥ 1.25 × non-continuous load + continuous load. The distinction matters for which conductor you're sizing — branch-circuit conductors per NEC 310.16 + 110.14(C) terminal ratings; feeder conductors per NEC 215.2 + 220 (demand factors may apply for feeders only). For a single-family residence, the 125% rule is the same on both sides; the difference shows up in commercial / multi-family demand-factor math."
      }
    },
    {
      "@type": "Question",
      "name": "What breaker for a hot tub (NEC 680)?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A 240 V hot tub typically draws 30 A continuous (per nameplate) → NEC 210.20(A) + 680 require OCPD ≥ 30 × 1.25 = 37.5 A → next standard OCPD = 40 A. Conductor: 6 AWG copper (75 °C ampacity 65 A) on a 40 A or 50 A GFCI breaker (50 A is also common for hot tubs with larger heaters). The GFCI protection requirement is NEC 680.44 — must be a GFCI breaker (not just a GFCI receptacle) for spa/hot tub installations. Verify with the manufacturer's installation manual — some 240 V hot tubs draw up to 50 A continuous and require a 60 A breaker + 4 AWG copper."
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
    { "@type": "ListItem", "position": 3, "name": "Circuit Breaker Size Calculator", "item": "https://elec.webpenson.com/tools/circuit-breaker-sizing-calculator/" }
  ]
}
</script>

---

> ⚠️ **Reference only.** This calculator and its accompanying copy apply the 2023 NFPA-70 (National Electrical Code) formulas described above and are intended for **educational and reference use**. Confirm all breaker, conductor, and GFCI sizing decisions with a **licensed electrician** and your local **Authority Having Jurisdiction (AHJ)** before pulling a permit or energizing any circuit. NEC adoption and amendments vary by jurisdiction — the AHJ's interpretation is the final authority on your installation. All math runs 100 % client-side; your load data never leaves the browser.
