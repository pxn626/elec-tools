---
title: "穿管填充率计算器 - NEC Chapter 9 / Annex C 在线工具"
description: "免费 NEC 穿管填充率计算器,输入线规(AWG)、wire type 和数量,得最小 ANSI 穿管 trade size 与填充率 %,符合 NEC Chapter 9 Table 4 和 Annex C。支持 EMT、PVC-40、PVC-80、RMC、IMC,纯前端无需注册。"
categories:
  - 电气工具
  - NEC 规范
  - 穿管选型
  - 线槽填充率

images:
  - "/images/tools/conduit-fill-calculator.svg"
tags:
  - "穿管填充率"
  - "NEC 穿管计算"
  - "EMT 填充率"
  - "PVC 穿管"
  - "Chapter 9 Table 4"
  - "Annex C"
  - "线槽填充"
  - "THHN 穿管"
  - "线规与管径"
keywords:
  - "穿管填充率计算器"
  - "NEC 穿管计算"
  - "EMT 填充率计算"
  - "PVC 穿管填充"
  - "Chapter 9 Table 4"
  - "Annex C"
  - "线槽填充率"
layout: "page"
translationKey: "conduit_fill_calculator"
date: "2026-07-28T04:00:00+00:00"
draft: false
---

# 穿管填充率计算器 - NEC Chapter 9 / Annex C 在线工具

## TL;DR

**穿管填充率**是导线截面积占穿管内截面积的百分比。NEC (NFPA 70,美国国家电气规范) 对其做出上限规定:**3 根及以上 40%,2 根 53%,1 根或 ≤ 24 英寸短管 60%**(依据 NEC Chapter 9 Note 1 和 NEC 310.15(C)(3))。

本工具实现 **NEC Chapter 9 Table 4**(穿管截面积)和 **Chapter 9 Table 5**(导线含绝缘外径),覆盖 **5 种穿管**(EMT、PVC-40、PVC-80、RMC、IMC)和 **5 种 wire type**(THHN/THWN-2、XHHW/XHHW-2、USE-2/RHH、NM-B、UF-B),提供三种计算模式:

- **模式 A - 校验:** 选定穿管 + trade size + 线规 + 数量 → 看填充率与合规。
- **模式 B - 推荐:** 选定穿管 + 线规 + 数量 → 推荐最小合规 trade size。
- **模式 C - 混线:** 同管多线规 → 算总填充率。

所有计算 **纯前端在浏览器内运行**,无上传、无注册、无服务端处理。

> **术语保留:** NEC / Chapter 9 / Annex C / THHN / XHHW / USE-2 / NM-B / UF-B / AWG / kcmil / EMT / PVC-40 / PVC-80 / RMC / IMC / trade size / nipple / EGC。这些英文术语在中文版保持英文以便查阅 NEC 原表。

---

## 什么是穿管填充率?

### NEC 40% / 53% / 60% 规则

按 NEC Chapter 9 Table 4 Note 1,穿管填充率公式:

```
填充率 % = 导线总截面积 / 穿管内截面积 × 100%
```

上限依导体根数(载流导体,CCC)而定:

| 导体根数 | 上限(NEC 引用) |
|---|---|
| 1 根 | 60% |
| 2 根 | 53% |
| 3 根及以上 | 40% |
| 短管 (≤ 24") | 60%(不论根数) |

**为什么是这些数字?** Annex C 表 C.1 到 C.12 是预先算好的查表,按"最差 OD 配最差穿管 OD"向下取整得来。40% 留出余量给:
- **散热**(I²R 焦耳热);
- **拉线空间**(长距离 + 弯头拉线需要);
- **未来换线**(热胀冷缩不损伤绝缘)。

### 为什么重要?

- **散热问题:** 导体电流平方乘电阻(I²R)产热。过密导致热散不出去,绝缘加速老化。
- **拉线摩擦:** 40% 余量给够空间让长管 + 弯的导线拉得过去,绝缘不被擦破。
- **绝缘损伤:** 过满管在热胀冷缩循环中,绝缘与管壁相互摩擦破损。

### 哪些导体算填充?

按 NEC 300.17 + 310.15(C) informational note,**计入填充**:
- 相线 / 火线
- 零线(NEC 310.15(B)(5) 单独列出的高次谐波不需降容时也算)
- **设备接地线 EGC**(**永远算**,常见错误就是不接地线)

**不计入**:
- NM-B / UF-B 整根 cable 的外护套(本工具把整根 cable 当作单一实体 OD 算,见下面"线缆类型")
- 穿管接头、锁紧螺母、护套

---

## 工具支持的穿管类型

### EMT (Electrical Metallic Tubing,薄壁金属管)

**用途:** 室内干燥、暴露敷设、轻工业。北美住宅和轻型商用最常用,1/2" trade size 起即可做支路。

**内截面积**(NEC Chapter 9 Table 4,1/2" 到 4"):
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

**用途:** 室外、地下、腐蚀环境。PVC-80(更厚壁)用于易受物理损伤的场合。同 trade size 内截面积比 EMT 小 5-7%。

### RMC (Rigid Metal Conduit) / IMC (Intermediate Metal Conduit)

**用途:** 重型室内外、暴露敷设、危险场所。RMC 最重,IMC 是中间档"轻量 RMC"。因壁更厚,内截面积比 EMT 略小。

### Flex / LFMC

工具暂未实现,如有特定厂家 OD 数据,可用 Mode A 自填 custom OD。

---

## 工具支持的线缆类型(绝缘外径)

### THHN / THWN-2

**北美最常用建筑线。** 热塑性绝缘,干燥环境 90°C (THHN),潮湿环境 75°C (THWN-2)。外径范围 14 AWG 0.111 in 到 500 kcmil 0.995 in。

### XHHW / XHHW-2

**交联聚乙烯绝缘**,干/湿均 90°C。同线规 OD 比 THHN 大(壁厚),但耐热更好。常用于馈线。

### USE-2 / RHH / RHW

**地下服务入口**线缆。直埋/室外用。同线规 OD 通常比建筑线大。常用于光伏 DC 电路、服务入口、室外馈线。

### NM-B / UF-B (电缆形式)

**非金属护套电缆**(Romex® 是品牌)。NM-B 用于室内干燥;UF-B 用于直埋/室外。**注意:** 这两种线规在本工具算的是 **整根 cable 的 OD(含护套)**,不是 cable 内部的单根导体。也就是说"Number of Conductors"对 NM-B / UF-B 而言实际是"Number of Cables"。

### 自填 OD

如果你的线型不在表内(矿物绝缘 MI / 铁氟龙等),用 free input OD 即可。

---

## 计算器使用方法

### 模式 A — 校验

已知穿管和线规,想确认填充率在限值内。

1. 选 **Conduit Type** (EMT、PVC-40 等)和 **Trade Size** (1/2"、3/4" 等)。
2. 选 **Wire Type** 和 **AWG / kcmil**。
3. 填 **Number of Conductors** —— 包括所有载流导体 **加设备接地线**。
4. 如果是短管 (≤ 24" 段),勾选 **Nipple (≤ 24")** —— 上限变成 60%。
5. 点 **Calculate**。

结果卡片显示:穿管内截面积、单根导体面积、导线总截面积、填充率、对应 NEC 上限、合规判定。

### 模式 B — 推荐

已知线规和导体根数,想得到最小合规的 trade size。

1. 选 **Conduit Type**、**Wire Type**、**AWG**、**Number of Conductors**。
2. 必要时勾选 **Nipple (≤ 24")**。
3. 点 **Recommend**。

工具从最小 trade size 往上迭代,显示最小刚好不超限的 trade size,以及该 size 下的填充率。

### 模式 C — 混线

同一穿管不同线规或线型(典型:照明 + 信号共管)。

1. 选 **Conduit Type**,必要时勾选 nipple。
2. 默认一行,点 **+ Add Wire Group** 增加。
3. 每行选 **Wire Type**、**AWG**、**Count**。
4. 点 **Calculate Mixed Fill**。

工具对所有行算 (π/4 × OD² × count) 求和,除以最小容得下的穿管内截面积,报结果。

### Preset:充电桩 / 光伏 / 车库 240V

点 preset chip 自动填 Mode C 表单:

- **充电桩 (NEMA 14-50):** EMT 中 2 × 6 AWG + 2 × 10 AWG THHN/THWN-2(2 火 + 地 + 零)。
- **光伏组串汇流:** EMT 中 4 × 10 AWG USE-2(屋顶汇流箱到逆变器)。
- **车库 240V 插座:** PVC-40 中 2 × 6 AWG + 1 × 10 AWG + 1 × 12 AWG THHN/THWN-2(住宅车库子配电进线)。

---

## 计算示例(5 例验证 + 1 例光伏)

> 质量门:每个示例都通过 **两份独立答案**:(1) 工具自动算;(2) 人工用 NEC Chapter 9 Tables 4 和 5 算。如果不一致,**工具错了**,人工不算错。

### 例 1 — 3 × 12 AWG THHN 穿 1/2" EMT(典型住宅支路)

**输入:** Conduit = EMT 1/2"; Wire = THHN 12 AWG; Count = 3(火 + 零 + 接地)。

**计算(按 NEC Chapter 9 Tables 4 & 5):**
- 12 AWG THHN OD = 0.130 in → 单根面积 = π/4 × 0.130² = 0.01327 in²
- 1/2" EMT 内截面积 = 0.304 in²
- 总导线截面积 = 3 × 0.01327 = 0.03982 in²
- 填充率 = 0.03982 / 0.304 = **13.10%**
- 上限(3 根及以上)= 40%
- 合规:✓ 远低于 40% —— 这是北美 120V 普通插座支路最常见的配置。

### 例 2 — 常见配置:9 × 12 AWG THHN 穿 3/4" EMT

**输入:** Conduit = EMT 3/4"; Wire = THHN 12 AWG; Count = 9(多个支路共管)。

**计算:**
- 12 AWG THHN 面积 = 0.01327 in²/根(同例 1)
- 3/4" EMT 内截面积 = 0.533 in²
- 总导线截面积 = 9 × 0.01327 = 0.11943 in²
- 填充率 = 0.11943 / 0.533 = **22.40%**
- 上限(9 根)= 40%
- 合规:✓ **远在限值内,典型多回路共管场景。** Annex C 表 C.1 给出 3/4" EMT 装 12 AWG THHN 的上限是 **16 根**(再加 1 根就必须跳到 1" EMT)。本次配 9 根,占 22.4% —— 还有 17.6 个百分点的余量,适合未来加回路。

### 例 3 — 4 × 6 AWG XHHW 穿 3/4" PVC-40 → 升 1" PVC-40

**输入:** Conduit = PVC-40 3/4"; Wire = XHHW 6 AWG; Count = 4(子配电进线或 50A 回路)。

**计算:**
- 6 AWG XHHW OD = 0.289 in → 单根面积 = π/4 × 0.289² = 0.06560 in²
- 3/4" PVC-40 内截面积 = 0.508 in²
- 总导线截面积 = 4 × 0.06560 = 0.26239 in²
- 填充率 = 0.26239 / 0.508 = **51.65%**
- 上限(4 根)= 40%
- 合规:✗ **超 40% 上限 11.65 个百分点。**

**升档再算 — 1" PVC-40:**
- 1" PVC-40 内截面积 = 0.832 in²
- 填充率 = 0.26239 / 0.832 = **31.54%**
- 合规:✓ 合规,余量 8.46 个百分点。

**推荐:** 用 1" PVC-40(最小合规升级)。除非预留扩容,不必跳到 1-1/4"。

### 例 4 — 混线:4 × 12 AWG + 2 × 14 AWG THHN 穿 1" EMT

**输入:** Conduit = EMT 1"; 组 1 = THHN 12 AWG × 4; 组 2 = THHN 14 AWG × 2(信号线与支路共管)。

**计算:**
- 12 AWG THHN 面积 = 0.01327 in²(同例 1)
- 14 AWG THHN OD = 0.111 in → 单根面积 = π/4 × 0.111² = 0.00968 in²
- 总导线截面积 = 4 × 0.01327 + 2 × 0.00968 = 0.05309 + 0.01935 = 0.07244 in²
- 1" EMT 内截面积 = 0.864 in²
- 填充率 = 0.07244 / 0.864 = **8.38%**
- 上限(6 根)= 40%
- 合规:✓ **余量极大;3/4" EMT 也能满足(填充率 13.62%)—— 按经济性选型。**

Annex C 不能直接查混线 —— 工具先按 Table 4 求总截面积。

### 例 5 — 充电桩 (NEMA 14-50):4 根线穿 3/4" EMT

**输入:** Conduit = EMT 3/4"; Wire = THHN/THWN-2(室外充电桩潮湿环境用 THWN-2);组 1 = 6 AWG × 2(L1 + L2);组 2 = 10 AWG × 1(EGC);组 3 = 10 AWG × 1(零线)。

**计算(含零线):**
- 6 AWG THHN/THWN-2 OD = 0.268 in → 面积 = π/4 × 0.268² = 0.05641 in²
- 10 AWG THHN OD = 0.164 in → 面积 = π/4 × 0.164² = 0.02112 in²
- 总面积 = 2 × 0.05641 + 2 × 0.02112 = 0.11282 + 0.04224 = 0.15506 in²
- 3/4" EMT 内截面积 = 0.533 in²
- 填充率 = 0.15506 / 0.533 = **29.09%**
- 上限(4 根)= 40%
- 合规:✓ 远低于 40%。(不含零线:25.13% 填充率,也合规;240V EVSE 不含零线省 1 根 —— 工具的 EV preset 默认 4 根。)

**常见错误:** 不算接地线(NEC 300.17)。

### 例 6 — 光伏组串汇流:4 × 10 AWG USE-2 穿 1" EMT

**输入:** Conduit = EMT 1"; Wire = USE-2 10 AWG; Count = 4(屋顶安装中,4 路光伏组串从组串汇流到逆变器的 DC 电路)。

**计算:**
- 10 AWG USE-2 OD = 0.193 in → 单根面积 = π/4 × 0.193² = 0.02926 in²
- 总导线截面积 = 4 × 0.02926 = 0.11704 in²
- 1" EMT 内截面积 = 0.864 in²
- 填充率 = 0.11704 / 0.864 = **13.55%**
- 上限(4 根)= 40%
- 合规:✓ **余量充足,后续加 1-2 路不必重新拉线。** USE-2 是光伏 DC 电路暴露室外穿管的典型绝缘(NEC 690.31)。

工具的 Solar PV preset 自动填这 4 根线进 Mode C。

---

## NEC 依据 — Chapter 9 与 Annex C

### Chapter 9 Table 4 — 穿管内截面积

本表给出每种穿管类型在每个 trade size 的内截面积(in²)。工具内置 NFPA 70-2023 全表的 EMT、PVC-40、PVC-80、RMC、IMC(各 9 个 trade size)。

### Chapter 9 Table 5 — 含绝缘导线外径

本表给出每个 wire type / AWG 组合的含绝缘 OD(in)。NEC 要求填充率用 **含绝缘 OD**,**不是裸铜 OD**。

### Annex C 表 C.1 到 C.12

Annex C 是预先算好的"多少根导线"查表,用公式 `⌊上限 × A_穿管 / A_导线⌋` 推算。单 wire type 场景下 Annex C 直接给答案;混线或 custom OD 场景必须用公式(本工具的 Mode C)。

### NEC 2020 vs 2023 差异说明

NEC Chapter 9 Table 4 + Table 5 在 2020 / 2023 数字稳定不动。Annex C 各表向下取整,例如公式 16.06 上限时 Annex C 给 16(不给 17)。本工具 A / B / C 三模式按公式真算填率,再跟规则比对 —— 比 Annex C 边界取整更精确。

---

## 常见问题 (FAQ)

### 1. 40% 填充率规则是什么?

按 NEC Chapter 9 Table 4 Note 1,填充率由导体根数决定:**1 根 60%、2 根 53%、3 根及以上 40%**。填充率 = 全部导线截面积之和(含 EGC 设备接地线)÷ 穿管内截面积(NEC Table 4)。对 **≤ 24 英寸的 nipple 短管**,NEC 310.15(C)(3) 允许 60%,不论根数。

### 2. 3/4" EMT 能穿多少根 12 AWG THHN?

按公式 `⌊0.40 × 0.533 / 0.01327⌋ = 16`,Annex C 表 C.1 上限是 **16 根 12 AWG THHN 在 3/4" EMT**。以 9 根为例:9 × π/4 × 0.130² = 0.1194 in² 总导线截面积。3/4" EMT 内截面积 0.533 in²。填充率 = 0.1194 / 0.533 = **22.40%** —— 远低于 40%。如果取上限 16 根,填充率变为 **39.83%**(刚不超)。超过 16 根就必须换 1" EMT(内截面积 0.864 in²,17 根时填率降到 24.55%)。

### 3. 接地线算不算填充?

**算。** 按 NEC 300.17 和 310.15(C) informational note,EGC 设备接地线和 bonding 导体计入填充。常见尺寸:60A 回路 10 AWG 裸铜、100A 8 AWG、200A 6 AWG。

### 4. NEC Chapter 9 Table 4 和 Annex C 的区别?

**Chapter 9 Table 4** 给每个穿管类型在每个 trade size 的内截面积(in²)。**Annex C** 表 C.1 到 C.12 给按 wire type 和 AWG 预先算好的"导线根数"。Annex C 数字由 Table 4 + Table 5 通过 `⌊上限 × A_穿管 / A_导线⌋` 公式(向下取整)推导。混线或 custom OD 用 Table 4(Mode C);单 wire type 速查用 Annex C。

### 5. 一根穿管能混线规吗?

**可以**,只要总填充率不超 40%(2 根 53%,1 根或短管 60%)。算法:所有导线的 (π/4 × OD² × 根数) 求和,除以穿管内截面积(NEC Chapter 9 Table 4)。例:1" EMT 中 4 × 12 AWG THHN(面积 0.01327 in²/根)+ 2 × 14 AWG THHN(面积 0.00968 in²/根):填充率 = (4 × 0.01327 + 2 × 0.00968) / 0.864 = 0.07244 / 0.864 = **8.38%** —— 余量 31.6 个百分点,合规。

### 6. ≤ 24 英寸短管 nipple 的填充率不同吗?

**是的。** 按 NEC 310.15(C)(3),**两个箱体之间 ≤ 24 英寸的 nipple 短管**允许填充率到 **60%,不论导体根数**。因为短段散热可以传到两端箱体,拉线热也不易堆积。典型应用:两个相邻配电箱之间 6 英寸短管、panelboard 和计表槽之间短管。EGC 接地线仍要算,60% 上限对所有 nipple 一致。

### 7. Conduit body(LB / Condulet)穿管盒填充率算法一样吗?

**一样**,但算法基础是 **体积不是面积**。NEC 314.16 和 Chapter 9 Table 4 都适用。先求每根导体的 (π/4 × OD²) 体积,求和后除以 conduit body 内部体积(查厂家 spec)。40% / 53% / 60% 上限同。本工具现只算直管段;conduit body 场景请按厂家体积表(Crouse-Hinds、O-Z/Gedney、Hubbell 等)核验。

### 8. PVC-40 和 EMT 填充率算法不同吗?

**算法相同** —— NEC Chapter 9 Table 4 同 40% / 53% / 60% 上限,Table 5 同 OD。唯一区别:PVC-40 同 trade size 内截面积比 EMT 小约 4.7%(例如 3/4" PVC-40 = 0.508 in² vs 3/4" EMT = 0.533 in²)。所以 PVC-40 同 trade size 比 EMT 少装 1-2 根。PVC-80 更紧(3/4" 时 0.456 in²)。选型前务必核实图纸上标注的 PVC 等级。

---

## 相关工具

- **[线规计算器 (Wire Size Calculator)](/tools/wire-size-calculator/)** — 起点:安培数 → AWG 线规;然后回到本工具选穿管。
- **[电缆载流量查表 (Cable Current-Carrying Capacity Lookup)](/tools/cable-current-carrying-capacity-lookup/)** — 温度 / 成束降容验算后再定穿管。
- **[断路器选型 (Circuit Breaker Sizing Calculator)](/tools/circuit-breaker-sizing-calculator/)** — 按 NEC 240 / 110.14(C) 配 OCPD。
- **[变压器容量选型 (Transformer Capacity Selection)](/tools/transformer-capacity-selection/)** — kVA → 次级 FLA 算大电流馈线。
- **[压降计算器 (Voltage Drop Calculator)](/tools/voltage-drop-calculator/)** — 长距离敷设? 验 V_drop ≤ 3% (NEC 210.19(A) Informational Note 4)。
- **[接地电阻 & 短路计算器 (Ground Resistance & Short-Circuit Calculator)](/tools/ground-resistance-short-circuit-calculator/)** — 接地极电阻 + 故障电流配 EGC 尺寸。

---

## 免责声明

**仅作参考** —— 实际施工请以当地采用的最新 **NEC** 版本和地方 **AHJ (Authority Having Jurisdiction)** 规定为准。本工具不替代专业工程师或持证电工的审核。终版设计必须经注册专业工程师盖章,或按当地法规要求由持证电工实施。

**数据源:** NEC Chapter 9 Tables 4 和 5 取自 NFPA 70-2023(编写时的最新版本;以上穿管和线型数字在 NEC 2020 / NEC 2023 之间稳定)。Annex C 表 C.1 根数上限由公式(⌊上限 × A_穿管 / A_导线⌋)推导 —— 临界选型时务必核对你采用的 NEC 印刷版。

---

<!-- JSON-LD: WebApplication -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "穿管填充率计算器",
  "alternateName": "NEC 穿管填充率计算器",
  "description": "免费 NEC 穿管填充率计算器。输入线规(AWG)、wire type 和数量,得最小 ANSI 穿管 trade size 与填充率 %,符合 NEC Chapter 9 Table 4 和 Annex C。支持 EMT、PVC-40、PVC-80、RMC、IMC。纯前端无需注册、无需上传。",
  "url": "https://elec.webpenson.com/zh/tools/conduit-fill-calculator/",
  "applicationCategory": "EngineeringApplication",
  "applicationSubCategory": "ElectricalDesignTool",
  "operatingSystem": "Any (Web Browser)",
  "inLanguage": "zh-CN",
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
  "keywords": "穿管填充率计算器,NEC 穿管计算,EMT 填充率计算,PVC 穿管填充,Chapter 9 Table 4,Annex C,线槽填充率,THHN 穿管,线规与管径"
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
      "name": "40% 填充率规则是什么?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "按 NEC Chapter 9 Table 4 Note 1,填充率由导体根数决定:1 根 60%、2 根 53%、3 根及以上 40%。填充率 = 全部导线截面积之和(含设备接地线 EGC)÷ 穿管内截面积(NEC Chapter 9 Table 4)。对 ≤ 24 英寸的 nipple 短管,NEC 310.15(C)(3) 允许 60%,不论根数。"
      }
    },
    {
      "@type": "Question",
      "name": "3/4 英寸 EMT 能穿多少根 12 AWG THHN?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "按公式 floor(0.40 × 0.533 / 0.01327) = 16,Annex C 表 C.1 上限是 16 根 12 AWG THHN 在 3/4 英寸 EMT。以 9 根为例:9 × π/4 × 0.130² = 0.1194 in² 总导线截面积。3/4 英寸 EMT 内截面积 0.533 in²,填充率 0.1194 / 0.533 = 22.40% —— 远低于 40%。到上限 16 根时,填充率 39.83%。超 16 根必须换 1 英寸 EMT(内截面积 0.864 in²,17 根填率降到 24.55%)。"
      }
    },
    {
      "@type": "Question",
      "name": "接地线算不算填充?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "算。按 NEC 300.17 和 310.15(C) informational note,设备接地线 EGC 和 bonding 导体计入填充计算。常见尺寸:60 A 回路 10 AWG 裸铜、100 A 8 AWG、200 A 6 AWG。唯一例外是穿管 EGC 全程不断、按 NEC 250.122 选型 —— 但仍占物理空间,必须计入。"
      }
    },
    {
      "@type": "Question",
      "name": "Chapter 9 Table 4 与 Annex C 的区别?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Chapter 9 Table 4 给每个穿管类型在每个 trade size 的内截面积(in²)。Annex C 表 C.1 到 C.12 给按 wire type 和 AWG 预先算好的导线根数查表。Annex C 数字由 Table 4 除以 Table 5 面积,通过公式 floor(上限 × A_穿管 / A_导线)向下取整。混线或 custom OD 用 Table 4(Mode C),单 wire type 速查用 Annex C。"
      }
    },
    {
      "@type": "Question",
      "name": "一根穿管能混线规吗?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "可以,只要总填充率不超过 40%(2 根 53%,1 根或短管 60%)。算法:每根导体的 (π/4 × OD² × 根数) 求和,除以穿管内截面积(NEC Chapter 9 Table 4)。例:1 英寸 EMT 中 4 × 12 AWG THHN(面积 0.01327 in²/根) + 2 × 14 AWG THHN(面积 0.00968 in²/根):填充率 = (4 × 0.01327 + 2 × 0.00968) / 0.864 = 0.07244 / 0.864 = 8.38% —— 余量大,合规。"
      }
    },
    {
      "@type": "Question",
      "name": "短管 ≤ 24 英寸 nipple 的填充率不同吗?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "是的。按 NEC 310.15(C)(3),两个箱体之间 ≤ 24 英寸的 nipple 短管段允许填充率到 60%,不论导体根数。这认可短段散热可传导到两端箱体,拉线热也不易堆积。典型应用:两个相邻配电箱之间 6 英寸短管、panelboard 和计表槽之间短管。EGC 接地线仍要算,60% 上限对所有 nipple 都适用。"
      }
    },
    {
      "@type": "Question",
      "name": "Conduit body(LB 拉线盒)填充率算法一样吗?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "一样,但算法基础是体积不是面积。NEC 314.16 和 Chapter 9 Table 4 都适用。每根导体的 (π/4 × OD²) 求和,除以 conduit body 内部体积(查厂家 spec)。40% / 53% / 60% 上限与穿管相同。工具现只算直管段;conduit body 场景请按厂家体积表(Crouse-Hinds、O-Z/Gedney 等)核验。"
      }
    },
    {
      "@type": "Question",
      "name": "PVC-40 和 EMT 填充率算法不同吗?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "算法相同 —— NEC Chapter 9 Table 4 同 40% / 53% / 60% 上限,Table 5 同 OD。唯一区别:PVC-40 同 trade size 内截面积比 EMT 小约 4.7%(例如 3/4 英寸 PVC-40 = 0.508 in² 对比 3/4 英寸 EMT = 0.533 in²)。所以 PVC-40 同 trade size 比 EMT 少装 1-2 根。PVC-80 更紧(3/4 英寸时 0.456 in²)。选型前务必核图纸上 PVC 等级。"
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
  "name": "如何按 NEC Chapter 9 计算穿管填充率",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "选定穿管类型和 trade size(或线规)",
      "text": "选 Conduit Type(EMT、PVC-40、PVC-80、RMC、IMC)和 Trade Size(1/2 英寸到 4 英寸);或从 Mode B 开始,直接选 Wire Type(THHN、XHHW、USE-2、NM-B、UF-B 或自定义 OD) + AWG/kcmil + 导体根数。"
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "填导体根数,必要时勾选短管 nipple",
      "text": "填载流导体根数 + 设备接地线 EGC(EGC 按 NEC 300.17 计入填充)。如果管段 ≤ 24 英寸短管,勾选 nipple 把上限从 40% 改到 60%(NEC 310.15(C)(3))。"
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "读取结果卡片",
      "text": "结果卡片显示:(a) 穿管内截面积 in²(Chapter 9 Table 4),(b) 单根导体截面积(Table 5),(c) 总导线截面积,(d) 填充率,(e) 合规判定(合规或超限)。Mode B 推荐给出最小合规 trade size;Mode C 混线给出每行细节与总和跟各 trade size 对比。"
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
      "name": "首页",
      "item": "https://elec.webpenson.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "工具",
      "item": "https://elec.webpenson.com/tools/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "穿管填充率计算器",
      "item": "https://elec.webpenson.com/zh/tools/conduit-fill-calculator/"
    }
  ]
}
</script>
