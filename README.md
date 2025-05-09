# Late Blight Risk Advisor – Huancavelica (Custom GPT)

This repository contains the full configuration, rule files, prompt examples, and documentation used to build the **Late Blight Risk Advisor – Huancavelica**, a technician-mediated GPT designed to assess potato late blight risk in the Peruvian highlands.

> Powered by OpenAI’s GPT Builder. Grounded in regional agronomic logic. Designed for low-connectivity environments.

---

## 🌱 Project Summary

- **Goal**: Deliver explainable, localized disease risk assessments to farmers in Huancavelica, Peru.
- **Deployment Model**: Trained technicians collect field data offline → query GPT online → deliver stored advice offline.
- **Target Pathogen**: *Phytophthora infestans* (late blight)
- **Crops Covered**: Local potato varieties (e.g., Yungay, Amarilis)
- **Language Support**: Spanish, English, and bilingual response logic

---

## 🔁 Workflow Overview

**Farmer observes field** → **Technician collects data (offline)** →  
**Inputs info into GPT (online)** → **Caches result** →  
**Delivers advice back to the farm (offline)**

---

## 🧠 Files Included

| File | Description |
|------|-------------|
| `rules_late_blight.md` | Logic rules based on humidity, temperature, rainfall, variety, and fungicide use |
| `varieties_andes.md` | Zone-specific resistance notes for common potato cultivars |
| `examples.benchmark.md` | Prompt-aligned test cases used for tuning and QA |
| `readme_gpt_setup.md` | Setup instructions, system prompt, response template, and usage policy |
| `calibration_history.md` | Risk threshold calibration based on real outbreak data (2018–2024) |
| `model_limitations.txt` | Known issues in prior LoRA classifier models and why this GPT was built |
| `roadmap.txt` | Planned improvements and modular extensions |
| `Custom_GPT_Agriculture.md` | Full technical article describing the rationale, build process, and impact |

---

## 📊 Evaluation & Accuracy

After rule refinement, the GPT now aligns with expert-labeled scenarios in **8 out of 9 test cases** (≈ 89% agreement) from Huancavelica.

- Key improvements: added rainfall thresholds, clarified borderline humidity rules, updated varietal susceptibility
- Evaluation based on blind testing of final risk label (Low / Moderate / High)
- Results may vary outside the tested region or season

> Ongoing testing is underway to expand the benchmark set and validate across diverse planting dates.

**Test it live** → [Late Blight Risk Advisor – Huancavelica (GPT)](https://chat.openai.com/g/g-68151466fca48191a953493191429b2e-late-blight-risk-advisor-huancavelica)

> Requires a free or paid ChatGPT account (with GPT Builder access).

---

## 🔄 Adaptation & Reuse

This GPT can be cloned and adapted for:

- Other crops (e.g., maize, wheat, cassava)
- Other diseases (e.g., rust, wilt, late leaf spot)
- Other regions (with localized climate and varietal data)
- Other languages (add logic in system prompt for multilingual or dialect-specific responses)

All logic and benchmark data are modular and can be swapped via `rules_*.md`, `examples_*.md`, and `varieties_*.md` files.

---

## 🛠️ Limitations

- Risk classifications are for decision support only — not formal diagnoses
- Model depends on accurate user inputs (e.g., humidity source, variety name)
- Prompt phrasing may impact outputs slightly
- Confirm visible symptoms in the field and consult local agronomists before acting

---

## 👥 Acknowledgments

This project was developed with support from:
- Expert agronomists from Peru’s Sierra region
- Prior model tuning experiments using OpenLLaMA + LoRA

---

## 📘 Citation

If you use or adapt this project, please cite:

> Alonso, J.L. (2025). *Building Custom GPTs for Agriculture: Case Study of the Late Blight Risk Advisor in Huancavelica*. GitHub Repository. https://github.com/jalonso2084/late-blight-gpt-huancavelica

---

## 📫 Questions?

Contact via GitHub or open an issue in this repository.
