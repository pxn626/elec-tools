---
title: "EV Charger Power Calculator — Sizing & Three-Phase Power"
description: "Free online EV charger power calculator. Enter voltage V, current A, and power factor cosΦ to calculate active power kW, reactive power kVar, and apparent power kVA. Supports single-phase 220V and three-phase 380V, assisting with charger sizing."
categories:
  - "EV Charger Tools"
  - "Electrical Calculators"
  - "Engineering Tools"
layout: "page"
translationKey: "charging_power_calculator"
---

{{< charging-power-calculator >}}

### What is the EV Charger Power Calculator?

The **EV Charger Power Calculator** is an electrical calculation tool designed for EV charger installation engineers, electrical designers, and vehicle owners. Based on the fundamental AC circuit formulas **P = √3 × U × I × cosΦ** (three-phase) or **P = U × I × cosΦ** (single-phase), it provides real-time calculations of active power, reactive power, and apparent power for EV chargers.

Enter the voltage (single-phase 220V or three-phase 380V), current, and power factor to obtain the actual charging power of the EV charger, distribution capacity requirements, and recommended vehicle compatibility.

### Key Features

- **Single-phase / Three-phase auto-switch**: Supports 220V single-phase residential and 380V three-phase industrial meters
- **Triple power output**: Displays active kW, reactive kVar, and apparent kVA simultaneously, facilitating distribution design
- **EV charger sizing recommendations**: 8 tiers — 7kW / 11kW / 22kW / 43kW / 60–100kW / 120–160kW / 240kW / 400kW+, matching various vehicle classes and distribution capacities
- **Integrated cable specs**: Each tier recommendation includes the recommended leakage protection switch and cable cross-section directly — no need to check the FAQ
- **Typical scenario presets**: One-click loading for common EV charger tiers:
  - **AC tier**: Home 7kW (220V/32A), Three-phase 11kW (380V/16A), Three-phase 22kW (380V/32A), Three-phase 43kW (380V/63A, actual ≈40.5kW)
  - **DC cabinet tier**: 30kW / 60kW / 80kW / 100kW / 120kW / 160kW / 240kW / 400kW / 480kW (equivalent current values at the 380V three-phase input side)
- **High-power alerts**: Prompts for 690V/10kV medium-voltage distribution when current ≥400A, preventing 380V overload
- **Pure frontend**: No backend, no data upload — safe for sensitive distribution scenarios

### Frequently Asked Questions (FAQ)

#### What is the EV charger power calculation formula?

Three-phase formula: **P = √3 × U × I × cosΦ** (U = line voltage, I = line current). Single-phase formula: **P = U × I × cosΦ**. The power factor cosΦ is typically 0.95–1.0. EV battery charging is nearly purely resistive, so 0.98 is the common assumption.

#### How many amps does a 7kW EV charger need?

**Single-phase 220V × 32A ≈ 7kW** — a 7kW home charger requires a 32A leakage protection switch and 6mm² copper cable. For an 11kW three-phase charger, a three-phase 380V × 16A configuration is needed with 5×4mm² five-core cable.

#### What is the difference between 22kW and 11kW EV chargers?

**11kW is three-phase 380V × 16A** and **22kW is three-phase 380V × 32A**. Both require a three-phase meter, but 22kW doubles the charging speed. Note: Tesla Model 3/Y standard onboard charger limits to 11kW — even plugging into a 22kW charger will only yield 11kW.

#### How do I size an EV charger — 7kW / 11kW / 22kW? The tool's recommendation panel gives the corresponding leakage protection + cable specs directly.

- **7kW single-phase 220V**: Suitable for most home scenarios, no three-phase meter application needed — the mainstream choice
- **11kW three-phase 380V**: 57% faster charging, ideal for frequent commuters (2–3 charges per week)
- **22kW three-phase 380V**: Suitable for commercial locations or two-vehicle households — confirm vehicle compatibility (some models are limited to 11kW)
- **43kW three-phase 380V/63A**: Industrial scenarios or large buses — actual active input ≈40.5kW (cosΦ=0.98)
- **30–480kW DC cabinets**: Commercial fast charging, buses/logistics, ultra-fast charging stations — see the preset buttons above for detailed sizing
- Sizing formula: **Weekly charging demand kWh = battery capacity × 0.6** (日常 SOC range) ÷ charging power ≤ 7 (once per week) or ≤ 11 (2–3 times per week)

#### How do I size distribution switches and cables?

- **7kW**: 32A leakage protection + 6mm² copper core + 1.5P circuit breaker
- **11kW**: Three-phase 16A leakage protection + 5×4mm² five-core cable + 3P circuit breaker
- **22kW**: Three-phase 32A leakage protection + 5×6mm² five-core cable + 3P circuit breaker
- **43kW**: Three-phase 63A leakage protection + 5×10mm² five-core cable + 3P 80A circuit breaker
- **60–120kW DC cabinet**: Three-phase 100A leakage protection + 5×16mm² cable; cabinet has built-in DC/DC rectification module
- **160–240kW dual-gun**: Three-phase 250A main leakage protection + busbar supply
- **400–480kW ultra-fast charging**: Typically 690V/10kV medium-voltage entry, liquid-cooled terminals — requires dedicated power system design
- For runs exceeding 50m, upsizing cables one tier (e.g., use 10mm² for 7kW) to prevent excessive voltage drop

#### What is the power factor cosΦ?

The power factor is the ratio of active power to apparent power, **cosΦ = P / S**. EV battery charging is nearly purely resistive, with power factors reaching 0.95–1.0. For EV charger power calculations, 0.98 is the typical assumption.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "What is the EV charger power calculation formula?", "acceptedAnswer": {"@type": "Answer", "text": "Three-phase: P = √3 × U × I × cosΦ; single-phase: P = U × I × cosΦ. cosΦ is typically 0.95–1.0; for EV charging, use 0.98."}},
    {"@type": "Question", "name": "How many amps does a 7kW EV charger need?", "acceptedAnswer": {"@type": "Answer", "text": "Single-phase 220V × 32A ≈ 7kW, requiring a 32A leakage protection switch + 6mm² copper cable. The 11kW three-phase charger requires three-phase 380V × 16A + 5×4mm² five-core cable."}},
    {"@type": "Question", "name": "What is the difference between 22kW and 11kW EV chargers?", "acceptedAnswer": {"@type": "Answer", "text": "11kW = three-phase 380V × 16A; 22kW = three-phase 380V × 32A. The 22kW is twice as fast, but Tesla Model 3/Y standard onboard charger limits to 11kW."}},
    {"@type": "Question", "name": "How do I size an EV charger — 7kW / 11kW / 22kW?", "acceptedAnswer": {"@type": "Answer", "text": "7kW single-phase 220V for home use; 11kW three-phase 380V for frequent commuters; 22kW for commercial/two-vehicle households. 43kW (63A three-phase, actual ≈40.5kW) for industrial use. The tool's recommendation panel automatically outputs the corresponding leakage protection + cable specs based on power — no need to check the FAQ. Sizing formula: weekly demand kWh = capacity × 0.6, divided by power equals charging hours."}},
    {"@type": "Question", "name": "How do I size distribution switches and cables?", "acceptedAnswer": {"@type": "Answer", "text": "7kW: 32A leakage + 6mm² + 1.5P breaker; 11kW: three-phase 16A leakage + 5×4mm² + 3P breaker; 22kW: three-phase 32A leakage + 5×6mm² + 3P breaker; 43kW: three-phase 63A leakage + 5×10mm² + 3P 80A breaker; 60–120kW DC cabinet: three-phase 100A leakage + 5×16mm²; 400–480kW ultra-fast: 690V/10kV medium-voltage. For runs > 50m, upsize one tier."}},
    {"@type": "Question", "name": "What is the power factor cosΦ?", "acceptedAnswer": {"@type": "Answer", "text": "Power factor is the ratio of active power to apparent power, cosΦ = P / S. EV battery charging is nearly purely resistive, with power factors of 0.95–1.0, typically taken as 0.98."}}
  ]
}
</script>
