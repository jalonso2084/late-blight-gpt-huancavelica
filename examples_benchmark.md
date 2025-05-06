# 📊 Benchmark Examples – Late Blight Risk Scenarios

_Last updated: 2025-05-01_

These prompt-response examples are adapted from benchmark cases used during fine-tuning. They help guide the GPT in making consistent risk assessments based on expert heuristics and updated rule logic.

---

## 🧪 Example 1: High Risk

**Prompt:**
```
Location: Huancavelica  
Variety: Amarilis  
Humidity: 85% sustained for 2 days  
Average Temperature: 17°C  
Fungicide applied: No  
```

**Response:**
Risk Level: **High**  
Confidence: High  
Reason: Prolonged high humidity with optimal temperature range (15–18°C) and no fungicide. Amarilis is moderately susceptible in this region.

---

## 🧪 Example 2: Moderate Risk (Adjusted Logic)

**Prompt:**
```
Location: Northern Peru  
Variety: Canchán  
Humidity: 81% during the last 10 hours  
Average Temperature: 16°C  
Rainfall: Light  
Fungicide applied: Yes  
```

**Response:**
Risk Level: **Moderate**  
Confidence: High  
Reason: Humidity above threshold for extended hours and temperature in ideal range. Although Canchán has moderate resistance, the environmental pattern alone reaches Moderate risk. No elevation was applied because the baseline was already Moderate.

---

## 🧪 Example 3: Low Risk

**Prompt:**
```
Location: Huancavelica  
Variety: UNICA  
Humidity: 78%  
Temperature: 14°C  
Rainfall: None  
```

**Response:**
Risk Level: **Low**  
Confidence: High  
Reason: Humidity below 80%, temperature slightly below risk range. UNICA has high resistance, and no contributing stressors are present.

---

## 🧪 Example 4: Edge Case – Moderate

**Prompt:**
```
Location: Ayacucho  
Variety: Yungay  
Humidity: 82% for 6 hours  
Temperature: 18°C  
Fungicide: Yes  
```

**Response:**
Risk Level: **Moderate**  
Confidence: Low  
Reason: Humidity briefly crossed threshold but did not reach 8 hours. However, Yungay is highly susceptible, which elevates the risk from Low to Moderate.

---

## 🧪 Example 5: High Elevation Microclimate

**Prompt:**
```
Location: Huancavelica (3,400 m elevation)  
Variety: Amarilis  
Humidity: 80–83% cloud cover over 3 days  
Temperature: 15.5°C  
Fungicide: No  
```

**Response:**
Risk Level: **High**  
Confidence: High  
Reason: Sustained humidity due to persistent fog/cloud cover, moderate temperature, and no fungicide. Elevation and varietal vulnerability increase the risk.

---

## Usage Notes

- The GPT will automatically lower confidence and request clarification if humidity duration, variety, or fungicide status are missing.
- Responses follow the modifier precedence described in `rules_late_blight.md`.

## 🧪 Example 6: Recent Fungicide → Lowered Risk

**Prompt:**
```
Location: Huancavelica  
Variety: Yungay  
Humidity: 82% sustained for 1 day  
Average Temperature: 16.5°C  
Fungicide applied: 2 days ago  
```

**Response:**
Risk Level: **Low**  
Confidence: High  
Reason: Humidity and temperature suggest Moderate baseline, but a fungicide was applied recently (within the 5-day protection window). This mitigates risk even for a susceptible variety like Yungay.