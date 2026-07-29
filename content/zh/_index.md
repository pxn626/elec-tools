---
translationKey: home
title: 电气工具箱 — 充电桩 / 电池 / 配电 在线计算工具集
description: 免费在线电气工具集，提供充电时间、充电桩功率、三相电、断路器选型、线径选型、电缆载流量、变压器容量、电费估算 8 大工具，覆盖 GB/T 国标与 NEC 国际标准。工程师 + 车主双场景适配。
layout: page
draft: false
---

## 电气工程师 & 电动车车主必备工具集

本站所有计算工具**纯前端运行**——数据绝不上传,适合敏感配电场景。

### 充电桩选型与计算

- [充电时间计算器](/tools/charging-time-calculator/) — 输入电池 kWh + 功率 kW,实时计算 0→80%、20→80%、0→100% 充电时长,覆盖 7kW/11kW/22kW/120kW/250kW 全场景。
- [充电桩功率计算器](/tools/charging-power-calculator/) — 输入 V/A/cosΦ,得出有功 kW / 无功 kVar / 视在 kVA,辅助 7kW/11kW/22kW 选型与配电设计。

### 配电设计

- [三相电功率计算器](/tools/three-phase-power-calculator/) — 输入线电压 U、线电流 I、功率因数 cosφ,秒算有功 P / 视在 S / 无功 Q,并推荐补偿到 0.95 所需电容容量。
- [电费估算计算器](/tools/electricity-cost-calculator/) — 电器功率 + 日使用时长(或月总用电量) + 电价,速算日 / 月 / 年电费与 CO₂ 排放。

---

### 为什么选择本站?

- **纯前端运行** — 所有计算在浏览器本地完成,数据 100% 不离开设备
- **即时响应** — 无需上传文件、无需排队,毫秒级出结果
- **工程师视角** — 公式与推荐均按国标 GB/T 与工程实务编写
- **车主友好** — 通俗解释 + FAQ,小白也能看懂
- **持续维护** — 适配新车型 / 新充电标准,每月更新

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "电气工具箱",
  "url": "https://elec.webpenson.com/",
  "description": "免费在线电气工具集:充电桩 / 电池 / 配电计算工具,工程师与车主双场景适配。",
  "inLanguage": "zh-CN",
  "potentialAction": {
    "@type": "SearchAction",
    "target": "https://elec.webpenson.com/?zh-search={search_term_string}",
    "query-input": "required name=search_term_string"
  }
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "webpenson",
  "url": "https://elec.webpenson.com/",
  "logo": "https://elec.webpenson.com/logo.png",
  "description": "免费在线电气工具箱 — 充电桩、电池与配电计算工具。100% 纯前端运行,数据零上传。基于 NEC、GB/T 与 IEC 标准开发。",
  "sameAs": [
    "https://github.com/pxn626"
  ]
}
</script>
