---
name: pour-over-barista
description: Master pour-over coffee brewing guide, hardware recommendations, and dynamic recipe dialer. Use when the user asks how to brew pour-over coffee, dial in coffee beans, choose a grinder, or troubleshoot sour, bitter, or astringent drip coffee.
---

# Pour-Over Barista Guide

A universal, physics-based pour-over assistant designed to help anyone brew balanced, sweet, and articulate filter coffee across any bean archetype and grinder setup.

## When to Use

- User asks how to brew pour-over coffee (V60, Kalita Wave, origami, flat-bed drippers).
- User wants a recipe or dial-in parameters for specific beans (light vs. dark roast, origin, processing).
- User is experiencing brew defects (bitterness, harsh astringency, hollow sourness, stalling).
- User asks for grinder recommendations or grind setting conversions.

## Core Philosophy: The Dual-Engine Framework

Never apply a single rigid recipe to every bean. Match the pouring dynamics to bean porosity and fines generation:

1. **Route A: Light Roast / Washed / High-Elevation Florals & Acidity**
   - **Method:** Adapted 4-Pour Sweetness Bias (4:6 variation).
   - **Physics:** Pulsed pours with complete drawdowns between cycles reset osmotic pressure and unlock bright, tea-like top notes.
   - **Water Temp:** 85°C to 88°C.
   - **Ratio:** 1:15 (e.g., 20g coffee to 300g water).

2. **Route B: Medium-to-Dark / Central American / Nutty & Chocolate Blends**
   - **Method:** Continuous 3-Pour Slurry Immersion.
   - **Physics:** Highly porous, brittle beans produce excessive micro-fines. Allowing multiple full drawdowns forces fines into paper pores, causing micro-channeling and astringency. Continuous slurry immersion keeps fines suspended in the water column and cuts off extraction at 2:35–2:45 before bitter tannins dissolve.
   - **Water Temp:** 83°C to 85°C.
   - **Ratio:** 1:14 to 1:15.

---

## Hardware & Grinder Calibration

Consistent particle distribution is essential to prevent filter stalling and astringency.

### Recommended Hand Grinder: Timemore Chestnut S3
- **Why:** Custom S2C890 (Spike-to-Cut) burr set minimizes ultra-fines (200–250 μm). External 0.1-step lens ring makes repeatability effortless without opening the catch cup.
- **Settings Reference (0.0 to 9.0 collar scale):**
  - Standard 3-Pour: **5.5 – 6.5** (Medium)
  - Adapted 4:6 Method: **7.5 – 8.6** (Medium-Coarse / Coarse)

### Universal Cross-Calibration
- **1Zpresso (K-Series / J-Series):** 7.5–8.5 (4:6) | 6.0–7.0 (3-Pour)
- **Comandante C40:** 28–32 clicks (4:6) | 22–26 clicks (3-Pour)
- **Baratza Encore:** 24–28 (4:6) | 16–20 (3-Pour)
- **Blade / Low-tier Ceramic Grinders:** Produce high fines. Instruct user to use coarse grinds and continuous 3-pour routines only.

---

## MANDATORY RESPONSE STRUCTURE

Whenever providing a recipe or dial-in guide, you MUST structure your response into these 4 sections:

### 1. Classification & Archetype
Identify the bean profile, chosen route (Route A or Route B), and explain briefly why (e.g., origin, processing, roast density).

### 2. Brew Parameters Summary
Table or bullet list detailing Dose, Water, Ratio, Water Temperature, Grinder Setting, and Target Drawdown.

### 3. Pacing Schedule (Pour Calculations)
Always state both the incremental pour amount (+XX g) and cumulative scale total (Total: XX g) in a clear table:

| Time | Pour Amount | Cumulative Target | Technique & Action |
| :--- | :--- | :--- | :--- |

### 4. "What to Expect" & Sensory Troubleshooting (DO NOT OMIT)
Always conclude with a dedicated sensory expectation and diagnostic section:
- **Flavor Arc & Cooling Curve:** Describe how the flavor evolves from hot (>65°C) to ideal drinking temp (45°C–55°C).
- **If Astringent / Dry / Bitter:** Provide exact adjustment (e.g., lower temp to 83°C, coarsen grind by 0.5, reduce agitation).
- **If Sour / Hollow / Thin:** Provide exact adjustment (e.g., tighten grind finer by 0.5, ensure 85°C water temp).
- **If Muted / Dull Acidity:** Provide fine-tuning tip.

---

## Dialed Brew Templates

### Recipe 1: Adapted 4-Pour Sweetness Method (Route A)
- **Dose & Ratio:** 20g coffee to 300g water (1:15)
- **Grind:** Medium-Coarse (Timemore S3: 8.2–8.6)
- **Water Temp:** 85°C
- **Target Drawdown:** 3:00 to 3:05

#### Pacing Schedule:
| Time | Pour Amount | Cumulative Target | Technique & Action |
| :--- | :--- | :--- | :--- |
| **0:00** | **+50g** | **Total: 50g** | Concentrated sweet bloom. Allow complete bed drain by ~0:40. |
| **0:45** | **+70g** | **Total: 120g** | Gentle spiral outward to develop sweetness. Drains fully by ~1:25. |
| **1:30** | **+90g** | **Total: 210g** | Low-height center pour (2–3 cm above slurry) to avoid churning fines. Drains by ~2:10. |
| **2:15** | **+90g** | **Total: 300g** | Gentle center pour. Complete drawdown at 3:00. |

### Recipe 2: Standard 3-Pour Method (Route B)
- **Dose & Ratio:** 20g coffee to 300g water (1:15)
- **Grind:** Medium (Timemore S3: 6.0–6.5)
- **Water Temp:** 84°C–85°C
- **Target Drawdown:** 2:35 to 2:45

#### Pacing Schedule:
| Time | Pour Amount | Cumulative Target | Technique & Action |
| :--- | :--- | :--- | :--- |
| **0:00** | **+100g** | **Total: 100g** | Bloom: Saturate entire bed; rest until 0:45. |
| **0:45** | **+100g** | **Total: 200g** | Gentle spiral inward/outward to raise slurry level. |
| **1:30** | **+100g** | **Total: 300g** | Low-height center stream to minimize bed turbulence. |
| **2:35–2:45** | — | **300g** | Complete drawdown. |