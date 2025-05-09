version: v1.2  
# 🌦️ Expert Rules for Late Blight Risk Estimation

These agronomic rules were derived from expert consultations, Peruvian field studies, and late-blight forecasting literature. They guide the Late Blight Risk Advisor GPT in assessing outbreak likelihood based on environment and varietal susceptibility.

---

## 🔹 Core Risk Drivers  

### 1. **Humidity Thresholds**  
- RH > 80 % for extended periods raises infection risk.  
- **Sustained humidity** > 80 % for:  
  - 8 + hours in a day → **Moderate** risk.  
  - 2 + consecutive days → **High** risk.  

★ **Sub-threshold clause** – If RH is **65–80 %** *and* (rainfall ≥ 10 mm in 24 h **or** canopy leaf-wetness ≥ 12 h) *and* temp 10–18 °C, elevate baseline one level (e.g., Low → Moderate).

### 2. **Temperature Interaction**  
- Optimal infection window: **15–18 °C**.  
- Risk tapers below 13 °C or above 22 °C.

### 3. **Rainfall & Wetness**  
- Light/moderate rain spreads spores and keeps leaves wet.  
★ **Rainfall modifier**  
  - Precip ≥ 20 mm in 24 h **or** ≥ 30 mm cumulative over 3 days → elevate risk by **one level**.  
- Prolonged dry breaks (> 48 h) can offset high humidity.

---

## 🔹 Risk Classification Heuristics  

| Risk Level | Environmental Pattern |
|------------|----------------------|
| **Low** | RH < 80 % *or* brief spikes with dry recovery; temperature not optimal |
| **Moderate** | RH > 80 % for 1 day *or* sub-threshold clause triggered |
| **High** | RH > 80 % for ≥ 2 days & temp 15–18 °C **or** rainfall modifier **or** susceptible-variety + no fungicide |

---

## 🔹 Modifiers and Precedence  

### Variety-susceptibility index  
| Index | Description | Examples* |
|-------|-------------|-----------|
| 1 | Highly resistant | CIP 308495.227 |
| 2 | Moderately resistant | INIA-302 Amarilis (north) |
| 3 | Intermediate | INIA-303 Canchan |
| 4 | Moderately susceptible | INIA-321 Kawsay |
| 5 | Highly susceptible | Yungay, Amarilis (central/south) |

> *See `varieties_andes.csv` for full list.

Rules:  
- **Index ≥ 4** → elevate baseline one level.  
- **Index = 5** → elevate baseline two levels *if* any other risk factor is Moderate.

### Fungicide timing  
- Spray ≤ 5 days ago lowers risk one level.  
- No spray during a High-risk window → elevate one level.

### High elevation (> 3 200 m) + cloud/fog  
- Can sustain hidden humidity; treat RH reading as 5 % higher when elevation rule applies.

Apply **“highest risk wins.”**

---

## 🔹 Microclimate Checklist  
(unchanged)

---

## 🔹 Temporal Reminder  
GPT has no memory between turns. **Always ask for humidity duration** if user omits it.

---

## 🔹 Calibration Note  
Validated against Huancavelica outbreaks 2018-2024; thresholds updated April 2025.

---

## 🔹 Expert Notes  
- Multi-day RH > 80 % + 15–18 °C remains the strongest predictor.  
- Flag `Confidence: Low` if RH > 90 % while temp < 13 °C (possible data error).  
