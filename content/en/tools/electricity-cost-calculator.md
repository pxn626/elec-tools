---
title: "Electricity Cost Calculator — Household Appliance Daily / Monthly / Annual Cost Estimator"
description: "Free online electricity cost estimator. Enter appliance wattage W and daily usage hours (or monthly kWh) plus electricity rate ¥/kWh to calculate daily/monthly/annual costs. Includes presets for LED lights, refrigerators, air conditioners, and water heaters. Assists with household energy savings."
categories:
  - "Electrical Calculators"
  - "Electricity Cost Estimation"
  - "Energy-Saving Tools"
  - "Household Essentials"


images:
  - "/images/tools/electricity-cost-calculator.svg"
tags:
  - "electricity cost"
  - "tiered pricing"
  - "kWh"
  - "home appliances"
  - "LED"
  - "air conditioner"
  - "electric water heater"
  - "CO₂ emission"
keywords:
  - "electricity cost calculator"
  - "home electricity cost"
  - "monthly kWh"
  - "tiered electricity pricing"
  - "energy savings"
  - "carbon footprint"
layout: "page"
translationKey: "electricity_cost_calculator"
---

{{< electricity-cost-calculator >}}

### What is the Electricity Cost Calculator?

The **Electricity Cost Calculator** is an online quick-calculation tool for household users, tenants, and small commercial operators. Based on the national standard **GB/T 32151.1** for household energy classification and the general **residential tiered electricity pricing** formula, it takes two key inputs — **single-appliance wattage + daily usage hours**, or **total monthly consumption in kWh** — and overlays the local **electricity rate (¥/kWh)** to instantly compute **daily / monthly / annual electricity costs**, **share of monthly income**, and **annual CO₂ emissions**.

Whether you need to calculate the monthly electricity bill for high-consumption appliances like air conditioners, refrigerators, and water heaters, or evaluate the additional household electricity cost from adding an EV charger or floor heating system, this tool delivers a quantitative reference in under one second.

### Key Features

- **Dual input modes**: Supports "appliance wattage + usage hours" for single-appliance estimation (suitable for analyzing specific appliances) and "total monthly kWh" for whole-house estimation (suitable when no equipment list is available)
- **Built-in appliance presets**: One-click fill for LED lights / refrigerators / air conditioners / water heaters / washing machines / microwaves / TVs / computers — no manual wattage lookup needed
- **Daily / Monthly / Annual three-tier cost output**: Displays daily kWh, daily cost, monthly cost, and annual cost simultaneously, with customizable calculation period days (suitable for commercial electricity billing)
- **Tiered electricity pricing support**: Residential tiered pricing automatically applies Tier 1 / Tier 2 / Tier 3 rates based on monthly cumulative kWh (thresholds and rates are manually configurable)
- **Share of monthly income**: Enter household monthly disposable income — the tool automatically calculates electricity cost as a percentage, aiding energy-saving decisions (IEA recommendation: < 4%)
- **Annual CO₂ estimation**: Estimates annual carbon emissions using China's grid average CO₂ emission factor of 0.581 kg/kWh — raising awareness of carbon neutrality
- **Pure frontend**: All calculations run locally in the browser — household electricity data is 100% never uploaded

### Frequently Asked Questions (FAQ)

#### What is the electricity cost calculation formula?

**Basic formulas**:

- **Daily consumption (kWh) = Wattage (W) × Daily usage hours (h) / 1000**
- **Daily cost (¥) = Daily consumption (kWh) × Electricity rate (¥/kWh)**
- **Monthly cost = Daily cost × 30** (adjustable to 30.4 days)
- **Annual cost = Monthly cost × 12**

If entering by total monthly consumption: **Monthly cost = Monthly kWh × Weighted average rate** (tiered pricing requires segment-by-segment calculation).

#### How is residential tiered electricity pricing calculated?

Most Chinese provinces use a **three-tier structure**:

- **Tier 1** (monthly ≤ ~216 kWh): Base rate (≈¥0.52/kWh, varies slightly by region)
- **Tier 2** (216–420 kWh): Base rate × 1.05–1.5×
- **Tier 3** (> 420 kWh): Base rate × 1.5–3×

This calculator allows manual configuration of three-tier thresholds and rates, applying them automatically. Commercial and industrial electricity uses time-of-use peak/valley pricing, which is not covered by this tool.

#### Which uses more electricity — air conditioning or a water heater?

Reference data (typical Chinese household usage):

| Appliance | Wattage | Daily Usage | Daily Cost (@¥0.55/kWh) |
|---|---|---|---|
| 1.5P Air conditioner (cooling) | 800–1200W | 8h (summer) | ¥3.5–5.3 |
| Electric water heater (60L) | 1500–2000W | 2h | ¥1.7–2.2 |
| Refrigerator (Grade 1 efficiency) | 80–150W | 24h | ¥1.1–2.0 |
| LED lights (10 fixtures) | 100W | 5h | ¥0.3 |
| Washing machine (tumble) | 200–500W | 1h | ¥0.1–0.3 |

**Air conditioning accounts for 50–70% of summer household electricity bills** — prioritize optimizing air conditioner usage (raising the thermostat by 1°C saves 6–8%).

#### How do I estimate total monthly household consumption?

**Method 1: Check your electricity bill** — Read the average monthly kWh from the last 3 months.

**Method 2: Estimate from appliance list** — List all appliances with estimated wattage and daily usage hours. This calculator can handle them one by one.

**Method 3: Use typical values by housing type**:

- 1–2 person apartment in a first-tier city: **100–200 kWh/month**
- 3-person family, 80–120m²: **200–400 kWh/month**
- Villa / large apartment: **500–1500 kWh/month**

#### How accurate is the CO₂ estimate?

This calculator uses **0.581 kg CO₂ / kWh** — the 2024 China grid average CO₂ emission factor (published by the National Development and Reform Commission). Actual figures fluctuate with time period, region, and generation mix:

- Provinces dominated by thermal power (Shandong / Inner Mongolia / Shanxi): Actual factor 0.7–0.9
- Provinces with high hydropower / renewable energy share (Yunnan / Sichuan / Qinghai): Actual factor 0.2–0.4

For precise carbon accounting, consult the latest provincial grid emission factor or use **green electricity (zero emissions)** at 0.

#### How much will a home EV charger increase my monthly electricity bill?

A 7kW home EV charger (220V / 32A), with a typical vehicle consumption of 15 kWh per 100 km and monthly mileage of 1500 km:

- Monthly charging: 1500 / 100 × 15 = **225 kWh/month**
- Monthly cost increase: 225 × 0.55 = **¥124/month** (≈ ¥1,500/year)

If on a peak/valley electricity rate (nighttime ¥0.30/kWh): **¥67/month** (saves 46%) — applying for a peak/valley meter + charging at night is recommended.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "What is the electricity cost calculation formula?", "acceptedAnswer": {"@type": "Answer", "text": "Daily kWh = Wattage W × hours / 1000; daily cost = daily kWh × rate ¥/kWh; monthly cost = daily cost × 30. This tool supports both single-appliance and total monthly kWh inputs."}},
    {"@type": "Question", "name": "How is residential tiered electricity pricing calculated?", "acceptedAnswer": {"@type": "Answer", "text": "Three tiers: Tier 1 (monthly ≤216kWh) ≈¥0.52/kWh; Tier 2 (216–420kWh) ×1.05–1.5×; Tier 3 (>420kWh) ×1.5–3×. This tool supports manual configuration of all tier thresholds and rates."}},
    {"@type": "Question", "name": "Which uses more electricity — air conditioning or a water heater?", "acceptedAnswer": {"@type": "Answer", "text": "1.5P air conditioner (800–1200W, 8h/day) consumes ~6–10 kWh daily, costing ¥3.5–5.3; electric water heater (1500–2000W, 2h/day) consumes ~3–4 kWh, costing ¥1.7–2.2. Air conditioning accounts for 50–70% of summer household electricity bills."}},
    {"@type": "Question", "name": "How do I estimate total monthly household consumption?", "acceptedAnswer": {"@type": "Answer", "text": "Three methods: check the electricity bill, estimate from appliance list (this tool handles it one by one), or use typical values by housing type. 1–2 person apartment: 100–200 kWh/month; 3-person family: 200–400 kWh/month."}},
    {"@type": "Question", "name": "How accurate is the CO₂ estimate?", "acceptedAnswer": {"@type": "Answer", "text": "This tool uses the 2024 China grid average CO₂ emission factor of 0.581 kg/kWh. Thermal-power-dominated provinces: 0.7–0.9; hydropower/renewable provinces: 0.2–0.4. For precise carbon accounting, consult the latest provincial grid factor."}},
    {"@type": "Question", "name": "How much will a home EV charger increase my monthly electricity bill?", "acceptedAnswer": {"@type": "Answer", "text": "7kW home charger (220V/32A), 1500km/month at 15kWh/100km = 225kWh/month, cost increase ¥124 (¥1,500/year). With peak/valley rate (nighttime ¥0.30/kWh) saves 46%."}}
  ]
}
</script>


## References

- EIA Residential Energy Consumption Survey (RECS)
- EPA Carbon Footprint Calculator Methodology
