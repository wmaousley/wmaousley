<p align="center">
  <img src="https://raw.githubusercontent.com/wmaousley/MiniCrit-1.5B/main/assets/banner.png" width="100%" />
</p>

# MiniCrit-1.5B  
### Adversarial Financial Critic Model for Autonomous LLM Trading Systems

[![DOI](https://zenodo.org/badge/DOI/10.57967/hf/7013.svg)](https://doi.org/10.57967/hf/7013)
[![DOI](https://zenodo.org/badge/1095074338.svg)](https://doi.org/10.5281/zenodo.17594497)  
[![ORCID](https://img.shields.io/badge/ORCID-0009--0009--2503--2010-brightgreen.svg)](https://orcid.org/0009-0009-2503-2010)  
[![HuggingFace Dataset](https://img.shields.io/badge/HuggingFace-FinRebut--600-yellow.svg)](https://huggingface.co/datasets/wmaousley/finrebut-600)  
[![Model Card](https://img.shields.io/badge/Model%20Card-MiniCrit--1.5B-blue.svg)](model-card/model-card.md)  

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Python Version](https://img.shields.io/badge/python-3.10+-blue.svg)
![Model Size](https://img.shields.io/badge/model-1.5B_parameters-purple.svg)
![Dataset Size](https://img.shields.io/badge/dataset-600_samples-yellow.svg)
![LoRA](https://img.shields.io/badge/LoRA-Enabled-orange.svg)
![ATAC-LoRA](https://img.shields.io/badge/ATAC--LoRA-Training%20Pipeline-red.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)

---

# 🔥 Overview

**MiniCrit-1.5B** is an adversarial financial critic model designed to evaluate, rebut, and stress-test LLM-generated trading rationales.  
It functions as a **validator layer** inside multi-LLM autonomous trading engines, improving safety, reducing hallucinations, and increasing discipline in trading decisions.

This repository includes:

- **FinRebut-600** — 600 realistic rationales + adversarial counter-arguments  
- **MiniCrit-12k** — 12,132 institutional rationale–critique pairs  
- **0.5B LoRA critic checkpoint** (CPU-trainable)  
- **ATAC-LoRA training pipeline** and notebook  
- **Model card + Zenodo DOI + ORCID metadata**  
- **Forward-testing benchmarks** and full reproducibility workflow  

---

# 📚 Project Links

| Resource | Link |
|---------|------|
| **Repository** | https://github.com/wmaousley/MiniCrit-1.5B |
| **Dataset (FinRebut-600)** | https://huggingface.co/datasets/wmaousley/finrebut-600 |
| **Dataset (MiniCrit-12k)** | https://huggingface.co/datasets/wmaousley/minicrit-training-12k |
| **Zenodo DOI** | https://doi.org/10.5281/zenodo.17594497 |
| **ORCID** | https://orcid.org/0009-0009-2503-2010 |

---

# 🧠 Model Summary

- **Model Name:** MiniCrit-1.5B  
- **Type:** LoRA-extended adversarial financial critic  
- **Role:** Detect flawed reasoning, hallucinations, or missing evidence in LLM-generated trading rationales  
- **Training Pipeline:** Nightly ATAC-LoRA  
- **Datasets Included:**  
  - **FinRebut-600** (600 samples)  
  - **MiniCrit-12k** (12,132 samples, CC-BY-4.0)  
- **Target Hardware:** 8×A100-80GB (Lambda Labs grant request)  
- **Artifacts:** Checkpoints, notebook, scripts, dataset, model card  
- **Forward-Test Performance:**  
  - Sharpe ratio improved **from +0.2 → +0.8** on 1-week window  
  - Reduced hallucination-driven trade decisions  

---

# 📈 Training Results (v1.3.x)


| Metric | Value |
|--------|-------|
| Base model | Qwen2-0.5B-Instruct |
| LoRA rank | 16 |
| Loss (start → end) | **TBD** *(after you add screenshot)* |
| Training time | ~XX minutes (M2 Ultra) |
| Paper-trading Sharpe | **+0.8** vs **+0.2** baseline |
| Dataset | MiniCrit-12k |

<p align="center">
  <img src="assets/loss.png" width="85%" />
</p>


```
## 📁 Repository Structure

MiniCrit-1.5B/
├── data/
│ └── finrebut-600.csv
├── notebooks/
│ └── ATAC_LoRA_MiniCrit.ipynb
├── checkpoints/
│ └── minicrit_lora_0.5b.pt
├── paper/
│ └── minicrit_preprint.pdf
└── src/
└── training/

```
## 🚀 Quickstart

```bash
---

# 🚀 Quickstart

### 1. Create environment
```bash
python3.10 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Or open the training notebook:

```
notebooks/ATAC_LoRA_MiniCrit.ipynb
```

## 📄 Citation

Ousley, W. A. (2025). *MiniCrit-1.5B: Adversarial Financial Critic Model and  
FinRebut-600 Dataset (v1.2.0)*. Zenodo.  
https://doi.org/10.5281/zenodo.17594497

```bibtex
@dataset{ousley2025minicrit,
  author    = {William A. Ousley},
  title     = {{MiniCrit-1.5B: Adversarial Financial Critic Model and FinRebut-600 Dataset}},
  year      = {2025},
  version   = {1.2.0},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.17594497},
  url       = {https://doi.org/10.5281/zenodo.17594497}
}
```

## 🏅 Author

**William Alexander Ousley**  
PMP • CSIE • CSAP  
AI/ML Researcher — Autonomous Trading Systems  
ORCID: https://orcid.org/0009-0009-2503-2010


## 🤝 Contributors

MiniCrit is an independent research project maintained by:

- **William Alexander Ousley** — Creator, lead researcher, dataset engineer, and model developer.

Contributions are welcome.  
If you would like to collaborate (datasets, pipeline upgrades, reproducibility fixes, or model improvements), please open an issue or submit a pull request.


## 💠 Funding & Acknowledgements

This project is part of an ongoing effort to build transparent, open-source adversarial evaluators for financial LLM systems.

Special acknowledgements:

- **Lambda Labs Research Grant (Pending Review)** — 2,000 A100-80GB compute hours requested  
- **CloudRift Research Grant (Under Review)** — 1,000 GPU hours requested  
- **HuggingFace** — Hosting the FinRebut-600 dataset  
- **Zenodo / CERN** — DOI archival and long-term preservation  
- **GitHub** — Repository infrastructure and distribution ecosystem  

This is an independent research project and is not affiliated with any institution, employer, or sponsor.



## 🧭 Project Roadmap (2025)

**Phase 1 — Dataset Expansion (Q4 2025)**  
- Expand FinRebut-600 → **FinRebut-2000**  
- Add macro-driven and high-volatility rationale categories  
- Introduce multi-rater adjudication (LLM + human)

**Phase 2 — Model Improvements**  
- Scale MiniCrit-1.5B → **MiniCrit-3B** (LoRA or QLoRA)  
- Add cross-model adversarial scoring (multi-LLM validation)  
- Integrate chain-of-thought flaw and hallucination detection  

**Phase 3 — Evaluation Framework**  
- Build a standalone **MiniCrit Evaluator API**  
- Create benchmark tasks for:  
  - fallacy detection  
  - weak reasoning detection  
  - hallucination classification  
  - adversarial rebuttal generation  

**Phase 4 — Research Publication**  
- Draft full 8–12 page technical report  
- Publish via Zenodo / TechRxiv  
- Add appendix covering datasets, methodology, and ablations


## 🔄 System Workflow

```mermaid
flowchart TD

A[User or LLM Generates Trading Rationale] --> B[MiniCrit Model]
B --> C{Critique?}
C -->|Weak Reasoning| D[Generate Adversarial Rebuttal]
C -->|Acceptable| E[Score & Pass Forward]

D --> F[Store in FinRebut Dataset]
F --> G[Nightly ATAC-LoRA Training]

E --> H[Ensemble Validator]
H --> I[Autonomous Trading Engine]
```

**ASCII Fallback (for GitHub mobile or Markdown viewers that don't support Mermaid):**

```
[ Rationale ] → [ MiniCrit ] → { Acceptable? }
       | Yes → Score → Validator → Trade Engine
       | No  → Rebuttal → Dataset → Nightly Training
```
