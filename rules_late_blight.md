version: v1.1
# 🌦️ Expert Rules for Late Blight Risk Estimation

These agronomic rules were derived from expert consultations, Peruvian field studies, and late blight forecasting literature. They guide the Late Blight Risk Advisor GPT in assessing the likelihood of outbreaks based on environmental conditions and varietal susceptibility.

---

## 🔹 Core Risk Drivers

### 1. **Humidity Thresholds**
- If relative humidity is **above 80%** for extended periods, infection risk increases significantly.
- **Sustained humidity** >80% for:
  - **8+ hours in a day** → triggers **Moderate** risk.
  - **2 or more consecutive days** → triggers **High** risk.

### 2. **Temperature Interaction**
- Late blight thrives when average daily temperatures are between **15°C and 18°C**.
- Risk increases when **high humidity and suitable temperature occur together**.
- Temperatures consistently **below 13°C** or **above 22°C** tend to reduce risk.

### 3. **Rainfall & Wetness**
- Light to moderate rainfall promotes spore movement and canopy wetness.
- Dry periods can offset high humidity conditions, reducing the risk.

---

## 🔹 Risk Classification Heuristics

| Risk Level | Environmental Pattern |
|------------|------------------------|
| **Low**    | Humidity < 80% or brief spikes with dry recovery; temperature not optimal |
| **Moderate** | Humidity > 80% for one full day with avg. temp 15–18°C |
| **High**   | Humidity > 80% sustained for 2–3+ days, temp 15–18°C, or additional risk factors (susceptible variety, rain, no fungicide) |

---

## 🔹 Modifiers and Precedence

- **Susceptible variety**: Elevate risk by one level *only if the environmental baseline is Low or borderline Moderate.*
- **Fungicide use**: Lowers risk only if applied within 3–5 days of risk period onset.
- **No fungicide during high-risk window**: Elevate risk level.
- **High elevation (>3,200 m)** with cloud cover can sustain hidden humidity.

> 🧠 When combining modifiers, apply the **"highest risk wins"** logic.

> If multiple moderate risk factors combine (e.g., marginal humidity, no fungicide, susceptible variety), elevate risk conservatively to Moderate or High.: if any factor pushes risk to High, report High unless contradicting evidence exists.

---

## 🔹 Microclimate Checklist

To refine risk assessment in mountainous or valley zones, consider:
- Persistence of **cloud or fog cover**
- **Drainage quality** and soil saturation
- Field location relative to slope (low spots hold moisture)
- **Canopy closure** or density (increases wetness retention)

These factors may intensify humidity effects even at moderate levels.

---

## 🔹 Temporal Reminder

GPT has no memory between user turns. **Always specify humidity duration** explicitly (e.g., “for 2 days”) to ensure correct risk classification.

---

## 🔹 Calibration Note

These rules were validated against outbreak reports from Huancavelica, Peru (2018–2024), using daily SENAMHI data and INIA field observations. Thresholds reflect expert consensus and can be revised as more outbreak data become available.

---

## 🔹 Expert Notes

- The most reliable outbreak indicator is **multi-day humidity >80% + temperature between 15–18°C**.
- Risk may be underestimated if user omits humidity duration.
- False positives may occur if only one risk factor is elevated.

---

> 🧠 Confidence Warning: If RH > 90% and temperature < 13°C, this may indicate contradictory inputs. Flag as `Confidence: Low` and request clarification.