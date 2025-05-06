# Late Blight Risk Advisor – Huancavelica (Custom GPT)

This repository contains the configuration files, rules, prompts, and documentation for a custom GPT assistant designed to support rural potato farmers in Huancavelica, Peru. The assistant estimates late blight risk using local agronomic heuristics and weather-sensitive logic.

> Built using OpenAI’s GPT Builder and designed for low-connectivity, technician-mediated workflows.

---

## 🌱 Project Summary

- **Purpose**: Deliver expert-informed disease risk assessments in low-resource rural settings.
- **Use Case**: Farmers provide data to trained technicians, who query the GPT online, cache the response, and deliver it offline.
- **Focus Region**: Huancavelica, Peru (targeting potato varieties like Yungay and Amarilis)
- **Disease**: *Phytophthora infestans* (late blight)

---

## 🧠 What’s Inside

| Folder/File               | Description |
|---------------------------|-------------|
| `rules_late_blight.md`    | Agronomic rules used by the GPT |
| `varieties_andes.csv`     | Resistance profiles for Andean potato cultivars |
| `readme_gpt_setup.md`     | Setup guide for GPT Builder users |
| `calibration_history.md`  | Log of field validation and debugging iterations |
| `model_limitations.txt`   | Known boundaries and disclaimers |
| `roadmap.md`              | Future development plans |
| `Custom_GPT_Agriculture.md` | Full article describing the case study and methodology |

---

## ⚙️ Usage

This GPT is deployed via OpenAI’s GPT Builder. To replicate or adapt it:

1. Prepare a structured prompt using bilingual inputs
2. Load `rules_late_blight.md` into the system prompt or knowledge base
3. Add examples from `examples_benchmark.md` if applicable
4. Guide technicians to cache and deliver responses as outlined in `readme_gpt_setup.md`

---

## 📊 Field Performance

- **85% agreement** with agronomist labels in pilot testing
- Technician workflow designed for **<24h cached validity**
- Compatible with rural deployment on low-end devices

---

## 🔄 Adaptation

This framework can be adapted to:
- Other crops (e.g., maize, wheat)
- Other regions (with localized varieties and rules)
- Other languages (via bilingual prompts)

---

## 👥 Acknowledgments

This project draws on:
- Agronomic expertise from field teams in Huancavelica
- Climate-risk heuristics validated by Peruvian extension agents
- Model tuning and evaluation supported by OpenLLaMA experiments

---

## 📘 Citation

If you use or reference this work, please cite:

Alonso, J.L. (2025). Building Custom GPTs for Agriculture: Case Study of the Late Blight Risk Advisor in Huancavelica. GitHub Repository. https://github.com/jalonso2084/late-blight-gpt-huancavelica
