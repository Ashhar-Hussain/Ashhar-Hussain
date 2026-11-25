<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
    <img alt="Ashhar Hussain — Machine Learning Engineer and Researcher" src="assets/banner-light.svg" width="100%">
  </picture>
</p>

<p align="center">
  <a href="https://orcid.org/0009-0009-1568-9852"><img alt="ORCID" src="https://img.shields.io/badge/ORCID-0009--0009--1568--9852-A6CE39?style=flat-square&logo=orcid&logoColor=white"/></a>
  <a href="mailto:asharhussain.csit@uokajk.edu.pk"><img alt="Email" src="https://img.shields.io/badge/Email-asharhussain.csit%40uokajk.edu.pk-1D3B6E?style=flat-square&logo=gmail&logoColor=white"/></a>
  <img alt="Location" src="https://img.shields.io/badge/Based%20in-Pakistan-01411C?style=flat-square"/>
  <img alt="Open to" src="https://img.shields.io/badge/Open%20to-ML%20%2F%20AI%20roles%20%C2%B7%20funded%20research-C8952E?style=flat-square"/>
</p>

I build machine-learning models and then try hard to break them. My research is about what happens after the benchmark: models that score 99% and then miss more than a third of real fires under distribution shift, INT8 compression that is lossless in-domain and lossy in the field, and evaluation protocols that can tell the difference. Lately I have been working on generative models: diffusion and flow matching from scratch, LoRA and DreamBooth on Stable Diffusion, and what fast inference really costs.

Researcher at the Department of Computer Science & IT, University of Kotli (AJ&K). The portfolio projects below ship as executed notebooks you can rerun on a free Colab runtime, and the paper repositories hold the code behind J1 and J2.

### Featured work

| Project | What | Key result | Stack |
|---|---|---|---|
| [**genai-diffusion-lab**](https://github.com/Ashhar-Hussain/genai-diffusion-lab) | Flow matching vs DDPM from scratch, LoRA vs full fine-tuning, DreamBooth-LoRA on SD 1.5, and what fast inference costs | DreamBooth-LoRA: rank 4 at 250 steps balances subject vs prompt fidelity in a 1.5 MB adapter; on a T4, DPM-Solver++ 15 is 9.2× faster than fp32 with no CLIP-T loss, LCM-LoRA 32.6× at a measurable cost | PyTorch · diffusers · peft · Colab T4 |
| [**rag-retrieval-ablation**](https://github.com/Ashhar-Hussain/rag-retrieval-ablation) | Retrieval scored separately from generation: BM25, dense, hybrid, re-ranking, local LLM | Re-ranking lifts Recall@1 from 0.77 to 0.89 on 1,000 questions, yet a 0.5 B local LLM gains only +0.03 F1 (not significant); misses become wrong answers, never refusals | sentence-transformers · Qwen2.5 · SQuAD |
| [**Evaluation-Code**](https://github.com/Ashhar-Hussain/Evaluation-Code) | Code for paper J1: explainable wildfire detection under distribution shift | 6 models at 97.9–99.0% in-domain all lose ~24 points on an independent dataset | TensorFlow · Grad-CAM · SHAP |
| [**TinyMWAMNet**](https://github.com/Ashhar-Hussain/TinyMWAMNet) | Code for paper J2: INT8 quantization of microcontroller-sized detectors under shift | PTQ costs ≤1 point in-domain but up to 5.8 points under shift, mostly missed fires | LiteRT · TFLM · QAT |
| [**gharchive-spark-lakehouse**](https://github.com/Ashhar-Hussain/gharchive-spark-lakehouse) | Bronze/silver/gold PySpark pipeline with data contracts and an Airflow DAG | 1.87 M events; the contract caught a real 2026 upstream change (-97.9% volume, push events gone) and held back affected tables; Parquet 25× faster than JSON | PySpark · Parquet · DuckDB · Polars |
| [**bank-marketing-decision-ml**](https://github.com/Ashhar-Hussain/bank-marketing-decision-ml) | Leakage, regime change and profit-based decisions on UCI Bank Marketing | Leak + random split inflate ROC-AUC from 0.68 to 0.95; the model chosen on rolling windows beats LightGBM on the final period (+0.063 AUC, 95% CI 0.049–0.077) | scikit-learn · LightGBM · Optuna |
| [**retail-analytics-sql**](https://github.com/Ashhar-Hussain/retail-analytics-sql) | SQL-first analytics on a million online-retail transactions | 1.07 M lines → £19.6 M clean revenue; top 20% of customers = 77% of revenue; 7-sheet Excel pack | DuckDB SQL · pandas · Excel |

### Papers and manuscripts

- **[J1]** A. Hussain\*, A. Kabir, N. Ali, M. Y. Shabir, M. Rashid, Z. Mehmood. *Benchmark Accuracy Overstates the Performance of Explainable Wildfire Detection Models Under Distribution Shift.* Discover Artificial Intelligence (Springer Nature), revised submission in review. [code](https://github.com/Ashhar-Hussain/Evaluation-Code)
- **[J2]** A. Hussain\*. *Lossless In-Domain, Lossy under Shift: Post-Training Quantization Can Make Tiny Machine Learning Wildfire Detectors Miss Fires.* Engineering Applications of Artificial Intelligence (Elsevier), submitted. [code](https://github.com/Ashhar-Hussain/TinyMWAMNet) · [supplementary](https://github.com/Ashhar-Hussain/supplementary)
- **[M1]** A. Hussain et al. *MTL-LDL-SG: a lightweight multi-task network for tomato leaf disease classification, lesion segmentation and severity estimation.* Ready for submission (Elsevier).

### Research pilots

- [`VFU-StressTest`](https://github.com/Ashhar-Hussain/VFU-StressTest) — reproduction of an AAAI 2026 vertical federated unlearning method under party, trigger and relearning stress (PyTorch, 5 seeds)
- [`visual-security-pilot`](https://github.com/Ashhar-Hussain/visual-security-pilot) — learned U-Net attacks on perceptually encrypted images; SSIM predicts leakage (ρ = 0.91) but attacker training data matters
- [`Config-Drift-CPU-Pilot`](https://github.com/Ashhar-Hussain/Config-Drift-CPU-Pilot) — FP16/INT8/INT4 inference: 8-bit keeps accuracy but changes 4–7× more predictions under shift
- [`inference-timing-pilot`](https://github.com/Ashhar-Hussain/inference-timing-pilot) — neural-network latencies are autocorrelated, so independence-based timing analysis underestimates misses 1.5–2.5×
- [`TS-OOD-Pilot`](https://github.com/Ashhar-Hussain/TS-OOD-Pilot) — time-series OOD gains depend on the shift type; conformal coverage drops from 90% to 57% under amplitude shift
- [`shapelet-early-reliability`](https://github.com/Ashhar-Hussain/shapelet-early-reliability) — the most 'efficient' early classifier was the least reliable: −34.5 points at a new site
- [`fsoc-divergence-rl-demo`](https://github.com/Ashhar-Hussain/fsoc-divergence-rl-demo) — a Q-learning controller fails under unseen heavy rain; a simple envelope guard recovers 28 points

### How I work

- **Pre-specify, then run.** Shift axes, metrics and tests are fixed before the first result.
- **Seeds and statistics.** Multi-seed runs, paired bootstrap, McNemar with Holm correction; differences inside the noise are reported as such.
- **Negative results count.** If the new component does not help, the write-up says so.
- **Resumable by default.** Notebooks checkpoint to Drive and skip finished work after a disconnect.

### Toolbox

<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"/> <img alt="TensorFlow" src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white"/> <img alt="Hugging Face" src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black"/> <img alt="diffusers" src="https://img.shields.io/badge/diffusers-FF9D00?style=flat-square"/> <img alt="scikit-learn" src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white"/> <img alt="LightGBM" src="https://img.shields.io/badge/LightGBM-2E8B57?style=flat-square"/> <img alt="Apache Spark" src="https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white"/> <img alt="DuckDB" src="https://img.shields.io/badge/DuckDB-FFF000?style=flat-square&logo=duckdb&logoColor=black"/> <img alt="SQL" src="https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white"/> <img alt="pandas" src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white"/> <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/> <img alt="Git" src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white"/> <img alt="Google Colab" src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=black"/> <img alt="TensorFlow Lite" src="https://img.shields.io/badge/TensorFlow%20Lite-FF6F00?style=flat-square&logo=tensorflow&logoColor=white"/> <img alt="LaTeX" src="https://img.shields.io/badge/LaTeX-008080?style=flat-square&logo=latex&logoColor=white"/>

### Activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Ashhar-Hussain/Ashhar-Hussain/output/github-snake-dark.svg">
  <img alt="Contribution graph as a snake" src="https://raw.githubusercontent.com/Ashhar-Hussain/Ashhar-Hussain/output/github-snake.svg">
</picture>
