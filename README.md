# MiniCrit-1.5B  
### Adversarial Financial Critic Model for Autonomous LLM Trading Systems

[![DOI](https://zenodo.org/badge/1095074338.svg)](https://doi.org/10.5281/zenodo.17594497)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0009--2503--2010-brightgreen.svg)](https://orcid.org/0009-0009-2503-2010)
[![HuggingFace Dataset](https://img.shields.io/badge/HuggingFace-FinRebut--600-yellow.svg)](https://huggingface.co/datasets/wmaousley/finrebut-600)

---

## 🔥 Overview  
**MiniCrit-1.5B** is an adversarial financial critic model designed to evaluate, rebut, and stress-test LLM-generated trading rationales.  
It functions as a *validator layer* inside multi-LLM autonomous trading engines.

This repository contains:

- **FinRebut-600** — 600 real, realistic human-style rationales & counter-arguments  
- **0.5B LoRA critic checkpoint** (CPU-trainable)  
- **Nightly training pipeline** (ATAC-LoRA style)  
- **Research-ready notebook & scripts**  
- **Zenodo DOI + ORCID integration** for grant & publication workflows  

---

## 📚 Project Links

- 📦 **Repo:** https://github.com/wmaousley/MiniCrit-1.5B  
- 📊 **Dataset (FinRebut-600):** https://huggingface.co/datasets/wmaousley/finrebut-600  
- 📜 **Zenodo DOI:** https://doi.org/10.5281/zenodo.17594497  
- 🧑‍🔬 **ORCID:** https://orcid.org/0009-0009-2503-2010  

---

## 🧠 Model Summary

- **Model:** MiniCrit-1.5B (LoRA-extended financial critic)  
- **Purpose:** Detect flawed reasoning, hallucinations, or weak logic in trading rationales  
- **Training:** ATAC-LoRA pipeline, updated nightly  
- **Hardware:** 8×A100 (Lambda grant target), CPU-trainable dev variant included  
- **Performance:**  
  - Paper-trading forward test: **Sharpe +0.8** vs **+0.2 baseline**  
  - 600 curated sentences → adversarial rebuttal pairs  

---

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



---

## 🚀 Quickstart

```bash
pip install -r requirements.txt
python src/training/train_lora.py --dataset data/finrebut-600.csv

notebooks/ATAC_LoRA_MiniCrit.ipynb

Ousley, W. A. (2025). MiniCrit-1.5B: Adversarial Financial Critic Model 
and FinRebut-600 Dataset (v1.2.0) [Data set]. Zenodo.
https://doi.org/10.5281/zenodo.17594497

@dataset{ousley2025minicrit,
  author       = {William A. Ousley},
  title        = {{MiniCrit-1.5B: Adversarial Financial Critic Model and
                   FinRebut-600 Dataset}},
  year         = 2025,
  version      = {1.2.0},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.17594497},
  url          = {https://doi.org/10.5281/zenodo.17594497}
}


🏅 Author
William Alexander Ousley
PMP • CSIE • CSAP
AI/ML Researcher — Autonomous Trading Systems
ORCID: https://orcid.org/0009-0009-2503-2010

---

## 🤝 Contributors

MiniCrit is an independent research project maintained by:

- **William Alexander Ousley** — Creator, lead researcher, dataset engineer, and model developer.

Community contributions (datasets, rebuttal samples, improvements to the LoRA pipeline, reproducibility fixes, etc.) are welcome.  
Submit pull requests or open issues if you'd like to collaborate.

---

## 💠 Funding & Acknowledgements

This project is part of an ongoing effort to build transparent, open-source adversarial evaluators for financial LLM systems.

Special acknowledgements:

- **Lambda Labs Research Grant (Pending Review)** — Application submitted for 2,000 A100-80GB compute hours for ATAC-LoRA scaling.
- **CloudRift Research Grant (Under Review)** — Application submitted for 1,000 GPU hours.
- **HuggingFace** — Hosting the FinRebut-600 dataset.
- **Zenodo / CERN** — Providing DOI-based archival for v1.2.0.
- **GitHub** — Repository distribution ecosystem.

This work is completely independent and not affiliated with any institution, employer, or sponsor.

---

## 🧭 Project Roadmap (2025)

**Phase 1 — Dataset Expansion (Q4 2025)**
- Expand FinRebut-600 → **FinRebut-2000**
- Add *high-volatility* and *macro-driven* rationale categories
- Introduce multi-rater adjudication (LLM + human)

**Phase 2 — Model Improvements**
- Scale MiniCrit-1.5B → **MiniCrit-3B** (LoRA or QLoRA)
- Add multi-LLM adversarial scoring (cross-model consensus)
- Integrate chain-of-thought detection for hallucination traps

**Phase 3 — Evaluation Framework**
- Build a standalone **MiniCrit Evaluator API**
- Create benchmark tasks for:
  - fallacy detection  
  - weak reasoning detection  
  - hallucination classification  
  - adversarial rebuttal generation

**Phase 4 — Research Publication**
- Draft full technical report (8–12 pages)
- Publish on Zenodo / TechRxiv
- Prepare conference-style appendix (datasets, methods, ablations)

---


