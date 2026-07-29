---
title: Three-Phase Power Calculator — Active / Apparent / Reactive Power & Power Factor
description: Online three-phase power and power factor calculator. Enter line voltage V, line current A, and power factor cosφ to calculate active power P(kW), apparent power S(kVA), and reactive power Q(kvar). Supports unit switching (W↔kW, VAr↔kVAr) and recommends reactive power compensation capacitors to correct to 0.95. For factory distribution, motor sizing, transformer capacity verification, and reactive power penalty calculations.
categories:
  - Electrical Calculators
  - Three-Phase Power
  - Factory Essentials
  - Engineering Tools
images:
  - /images/tools/three-phase-power-calculator.svg
tags:
  - three-phase
  - power factor
  - cosφ
  - reactive compensation
  - kVAr
  - power triangle
  - GB/T 15543
  - industrial distribution
keywords:
  - three-phase power calculator
  - three-phase power
  - active power
  - reactive power
  - apparent power
  - PF compensation
  - power factor penalty
layout: page
translationKey: three_phase_power_calculator
draft: false
---

{{< three-phase-power-calculator >}}

### What is the Three-Phase Power / Power Factor Calculator?

The **Three-Phase Power / Power Factor Calculator** is an online quick-calculation tool for **factory electrical maintenance engineers, electrical designers, electromechanical students, and workshop electricians**. Based on the fundamental AC three-phase formula **P = √3 · U · I · cosφ**, it takes **line voltage U (V)**, **line current I (A)**, and **power factor cosφ** as inputs to instantly compute **active power P (kW)**, **apparent power S (kVA)**, and **reactive power Q (kvar)**, while automatically providing the reactive power compensation capacitor capacity (kVAr) needed to correct to **cosφ = 0.95**.

Whether it's factory distribution panel sizing, transformer capacity verification, reactive power compensation scheme design, or end-of-term exam formula reference, this tool delivers **quantitative results in 1 second**, eliminating manual calculation of √3 and trigonometric functions.

### How to Calculate Three-Phase Active Power? How to Use P = √3·U·I·cosφ?

The three-phase four-wire formula is **P = √3 · U_line · I_line · cosφ**, where U is line voltage (V) and I is line current (A). The √3 factor originates from the geometric relationship that **line voltage is √3 times the phase voltage** in a three-phase winding system (380V line voltage → 220V phase voltage).

**Example calculation**: Three-phase induction motor **380V × 50A × cosφ 0.85** → **P ≈ √3 × 380 × 50 × 0.85 ≈ 27.97 kW** (≈ 28 kW).

An important conceptual point that is frequently confused: **cosφ is not "the cosine of the phase difference angle" per se**, but rather **"the ratio of active power to apparent power"** — this is the most commonly misunderstood concept among junior and senior electrical engineering students. A factory induction motor at full load has a typical **cosφ = 0.85**, while an EV charger battery is nearly purely resistive with **cosφ = 0.98** — the same formula with these two default parameter sets yields significantly different results.

### How to Convert Between Apparent Power S, Active Power P, and Reactive Power Q?

The three powers form a **power triangle**: the hypotenuse is apparent power S, the adjacent side is active power P, and the opposite side is reactive power Q — i.e., **S² = P² + Q²**. Conversion formulas:

- **S = P / cosφ** (derived from the power triangle)
- **Q = P · tanφ** (where tanφ = sinφ / cosφ)
- **P = S · cosφ** (original definition)

**Engineering significance**: **Transformer nameplates are marked in kVA, not kW** — the transformer's core and winding dimensions determine the maximum apparent capacity S it can withstand, regardless of the load cosφ. If you need to select a transformer by kW, round down: **kVA ÷ actual cosφ = kW** (a 100 kVA transformer at cosφ 0.85 load can only stably output 85 kW of active power).

### How to Calculate Reactive Power Compensation Capacitor Capacity? How Many kvar Are Needed?

Compensation capacity formula: **Qc = P × (tanφ₁ − tanφ₂)**, where P is active power, tanφ₁ is the pre-correction tangent angle, and tanφ₂ is the post-correction target angle.

**Practical reference table** (compensation capacity required per 100 kW of active power, kvar):

| Pre-correction cosφ → Target cosφ | 0.90 | 0.95 |
|---|---|---|
| 0.70 | 53 | 74 |
| 0.80 | 32 | 42 |
| 0.85 | 19 | 28 |

**National standard references**: GB/T 11024-2010 *Shunt Capacitors for AC Power Systems with Nominal Voltage up to 1 kV*; supplementary selection per DL/T 842-2003 *Technical Conditions for Low-Voltage Shunt Capacitor Installation*. This tool automatically calculates Qc from the user's input of active power P and pre/post-correction cosφ, and provides recommendations based on the nearest standard capacitor cabinet size.

### How to Convert Power Units? W, kW, MW; VAr, kVAr, MVAr?

- **1 W = 10⁻³ kW = 10⁻⁶ MW**; **1 VAr = 10⁻³ kVAr = 10⁻⁶ MVAr**
- **Retain 3 significant figures** (W level: 0.000 three decimals; MW level: 0.00 three significant figures)
- **Display kW / kVA in parallel** (the P / S ratio equals cosφ — no additional calculation needed)
- Single-phase 220V formula: No √3 factor, **P = U · I · cosφ**

The tool internally computes in SI units (watts / volt-amperes / vars) and converts to the user-selected unit for display — ensuring that an input accurate to 1 W correctly scales to MW-level output and vice versa.

### Frequently Asked Questions (FAQ)

#### What is the three-phase power formula? How to calculate P, Q, S?

Three-phase four-wire basic formulas (line voltage, line current):

- **P = √3 · U · I · cosφ** (active power, kW)
- **Q = √3 · U · I · sinφ** (reactive power, kvar)
- **S = √3 · U · I** (apparent power, kVA)

For single-phase, remove the √3 factor: **P = U · I · cosφ**.

**Verification example**: 380V / 100A / cosφ 0.85 → P ≈ 55.7 kW, S ≈ 65.6 kVA, Q ≈ 34.6 kvar (plug in to verify).

Note: The more practical engineering interpretation of cosφ is "the proportion of active power to apparent power" rather than "the cosine of the phase difference angle itself."

**Reference**: GB 50052-2009 *Code for Design of Electric Power Supply Systems*.

#### How to calculate power factor cosφ? How to back-calculate from voltage, current, and active power readings?

Definition: **cosφ = P / S = P / √(P² + Q²)**.

Back-calculation from measurement: Use readings from an **active energy meter + a reactive energy meter**, first find **tanφ = Q / P** (reactive kvar ÷ active kW), then look up cosφ — most industrial electricity meters provide both active and reactive cumulative readings, so just divide directly.

**Typical cosφ ranges by load type**:

- **Purely resistive** (electric heating, incandescent lamps): ≈ 1.0
- **Induction motor at full load**: 0.85–0.9; **at no-load** drops to 0.2–0.3
- **VFD / rectifier / switch-mode power supply**: 0.95–0.98
- **Electric arc furnace / large rectifier**: 0.6–0.8

**Reference**: GB/T 15543-2008 *Power Quality — Three-Phase Voltage Unbalance*.

#### What are the dangers of low power factor? Will electricity charges be surcharged?

Three major risks:

1. **Transformer / line "the same kVA can't drive more active power"** — transmission capacity is wasted
2. **Line copper loss I²R and voltage drop both increase** (current travels more, losses grow with the square)
3. **Most regions impose reactive power penalty for cosφ < 0.9**

The national "Power Factor Adjustment Electricity Fee Method" stipulates: **0.90 is the threshold**, each 0.01 below adds **0.5% surcharge**; below **0.65, a +10% penalty applies**; correcting to **above 0.95 grants a 0.15% rebate per 0.01 above** (specific provincial details vary; refer to local utility documents).

**Cost calculation example**: A factory with 500 kVA transformer and cosφ 0.65 corrects to 0.95 — **annual savings in reactive power fees + line loss合计 ≈ ¥80,000–150,000** — this is why industrial users universally install capacitor compensation.

#### How to calculate reactive power compensation capacitor capacity? How to convert Qc = kvar?

Engineering formula: **Qc = P × (tanφ₁ − tanφ₂)**, where P is active power.

**Practical reference table** (compensation capacity required per 100 kW active power):

| Pre-correction cosφ → Target cosφ | 0.90 | 0.95 |
|---|---|---|
| 0.70 | Requires 53 kvar | Requires 74 kvar |
| 0.80 | Requires 32 kvar | Requires 42 kvar |
| 0.85 | Requires 19 kvar | Requires 28 kvar |

**References**: GB/T 11024-2010 *Shunt Capacitors for AC Power Systems with Nominal Voltage up to 1 kV*; supplementary selection per DL/T 842-2003 *Technical Conditions for Low-Voltage Shunt Capacitor Installation*. This tool calculates Qc automatically from inputs of P and pre/post-correction cosφ, and recommends the nearest standard capacitor cabinet size.

#### What is the difference between the three power factor target values — 0.85, 0.90, and 0.95?

- **0.85**: Typical full-load value for induction motors — **acceptable status quo for factories** (runs fine without compensation)
- **0.90**: **Threshold per China's Power Factor Adjustment Electricity Fee Method** — penalties apply if not met
- **0.95**: **Engineering design target** — the balance point between compensation cost and electricity fee rebate

**Break-even analysis**:

- Compensating **0.65 → 0.90**: Low cost per kvar
- **0.90 → 0.95**: Moderate cost per kvar
- **0.95 → 1.0**: Cost per kvar increases steeply but returns diminish — **0.95 is the industry-wide consensus break-even point**

Recommendation: When a factory's cosφ is consistently below 0.85, design directly for a 0.95 target rather than correcting to 0.90 first and then to 0.95 — avoiding duplicate investment.

**Reference**: DL/T 842-2003 + State Grid Corporation's *Power Factor Adjustment Electricity Fee Method*.

#### What is the difference between apparent power S and active power P? Why are transformer nameplates in kVA?

**Definition comparison**:

- **P** is the portion that actually does work (converts to mechanical / heat / light), unit kW
- **S** is the overall "voltage-current package" capacity, unit kVA
- They are related by cosφ: **P = S · cosφ**

**Engineering reason why transformer nameplates are in kVA, not kW**: cosφ is determined by the load and is beyond the equipment manufacturer's control — the transformer can only guarantee the "maximum apparent capacity S"; if marked in kW, the transformer could actually overload and burn out under low cosφ loads (because at the same kVA, a low cosφ means less active power, but the apparent power is already at its limit).

**Illustrative comparison**: EV charger batteries are nearly purely resistive, cosφ ≈ 0.98 — **S and P differ by less than 2%** — so EV charger nameplates have flexibility in marking both kW and kVA.

#### How much electricity cost can a factory save by improving power factor from 0.7 to 0.95 over one year?

**Case setup**: A machinery processing factory, **monthly active energy 80,000 kWh, average cosφ 0.7, current reactive power penalty coefficient +10%**.

Three benefits after correcting to 0.95:

- **(a) Reactive power fee**: Changes from +10% to −0.75% (rebate) — direct electricity bill reduction
- **(b) Reduced line losses**: Approximately 30% reduction (lower current, I²R decreases with the square)
- **(c) Transformer capacity release**: 25% increase (the same 500 kVA transformer can drive 25% more active load after compensation — equivalent to free capacity expansion)

Combined **annual savings ≈ ¥120,000–180,000**; compensation capacitor investment ¥180,000–250,000 — **payback in 1.5 years**, after which it's pure profit.

**Reference**: Actual energy-saving measurement from the *Industrial Energy Conservation Management Measures*.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "Three-Phase Power Calculator",
  "applicationCategory": "UtilitiesApplication",
  "operatingSystem": "Web",
  "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" },
  "description": "Free three-phase power calculator. Calculates active power (P/kW), reactive power (Q/kvar), apparent power (S/kVA), and power factor. Supports balanced and unbalanced loads. Supports GB/T 15543 and NEC standards. No signup required.",
  "url": "https://elec.webpenson.com/en/tools/three-phase-power-calculator/"
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://elec.webpenson.com/" },
    { "@type": "ListItem", "position": 2, "name": "Tools", "item": "https://elec.webpenson.com/tools/" },
    { "@type": "ListItem", "position": 3, "name": "Three-Phase Power Calculator", "item": "https://elec.webpenson.com/en/tools/three-phase-power-calculator/" }
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "What is the three-phase power formula? How to calculate P, Q, S?", "acceptedAnswer": {"@type": "Answer", "text": "Three-phase four-wire formulas: P = √3 × U × I × cosφ (active kW), Q = √3 × U × I × sinφ (reactive kvar), S = √3 × U × I (apparent kVA). Single-phase removes √3: P = U × I × cosφ. Example: 380V/100A/cosφ 0.85 → P≈55.7kW, S≈65.6kVA, Q≈34.6kvar. Reference GB 50052-2009."}},
    {"@type": "Question", "name": "How to calculate power factor cosφ? How to back-calculate from meter readings?", "acceptedAnswer": {"@type": "Answer", "text": "Definition: cosφ = P / S = P / √(P² + Q²). Use active + reactive meter readings to back-calculate tanφ then look up cosφ. Typical values: purely resistive ≈1.0; induction motor full-load 0.85–0.9, no-load 0.2–0.3; VFD/rectifier 0.95–0.98; arc furnace 0.6–0.8. Reference GB/T 15543-2008."}},
    {"@type": "Question", "name": "What are the dangers of low power factor? Will electricity charges be surcharged?", "acceptedAnswer": {"@type": "Answer", "text": "Three risks: ① Transformer/line transmission capacity is wasted; ② Line I²R copper loss and voltage drop both increase; ③ China's Power Factor Adjustment Electricity Fee Method sets 0.9 as the threshold — each 0.01 below adds 0.5% surcharge; below 0.65 adds +10% penalty; correcting to above 0.95 grants 0.15% rebate per 0.01 above."}},
    {"@type": "Question", "name": "How to calculate reactive power compensation capacitor capacity? How to convert Qc = kvar?", "acceptedAnswer": {"@type": "Answer", "text": "Engineering formula: Qc = P × (tanφ₁ − tanφ₂), P is active power. Practical table (per 100kW): cosφ 0.70→0.90 requires 53 kvar; 0.70→0.95 requires 74 kvar; 0.80→0.95 requires 42 kvar; 0.85→0.95 requires 28 kvar. Reference GB/T 11024-2010."}},
    {"@type": "Question", "name": "What is the difference between the three power factor target values — 0.85, 0.90, and 0.95?", "acceptedAnswer": {"@type": "Answer", "text": "0.85 is the typical full-load value for induction motors; 0.9 is the threshold per the Power Factor Adjustment Electricity Fee Method (penalties apply); 0.95 is the engineering design target — the balance point between compensation cost and rebate. The 0.95→1.0 marginal cost increases steeply with diminishing returns, so 0.95 is the industry-wide break-even point. Reference DL/T 842-2003."}},
    {"@type": "Question", "name": "What is the difference between apparent power S and active power P? Why are transformer nameplates in kVA?", "acceptedAnswer": {"@type": "Answer", "text": "P = ∫UI cosφ dt is the portion doing actual work (mechanical/heat/light); S = ∫UI dt is the overall voltage-current capacity; P = S·cosφ. Transformer nameplates are in kVA because cosφ is determined by the load and beyond the manufacturer's control — the transformer can only guarantee maximum apparent capacity S. At low cosφ loads, a kW-marked transformer could overload. EV charger battery cosφ is 0.98, so S and P differ by less than 2%."}},
    {"@type": "Question", "name": "How much electricity cost can a factory save by improving power factor from 0.7 to 0.95 over one year?", "acceptedAnswer": {"@type": "Answer", "text": "Case: Monthly active 80,000 kWh, cosφ 0.7, reactive power penalty +10%. After correcting to 0.95: reactive power fee changes from +10% to -0.75% (rebate); line loss reduced ~30%; transformer capacity released 25%. Combined annual savings ¥120,000–180,000, compensation capacitor investment ¥180,000–250,000, 1.5-year payback. Reference Industrial Energy Conservation Management Measures."}}
  ]
}
</script>


## References

- GB/T 15543-2008 Power Quality Three-phase Voltage Unbalance
- GB 50052-2009 Code for Design of Power Supply and Distribution Systems
