# 🧠 AG-DenseNet121: Automated Liver Cirrhosis Stage Classification

> **M.Tech Dissertation Project | Published at NetCrypt International Conference 2026 (IEEE Xplore)**

An attention-guided deep learning model for automated classification of liver cirrhosis severity (Moderate vs. Severe) from T2-Weighted MRI images, outperforming state-of-the-art by **+13.44 percentage points**.

---

## 🏆 Key Results

| Metric | Score |
|--------|-------|
| Accuracy | **77.24%** |
| AUC-ROC | **0.849** |
| F1-Score | **0.756** |
| Precision | **0.788** |
| Recall | **0.751** |
| Severe-class Recall | **91%** |

> ⚡ Outperforms prior SotA **MambaVision-T (63.8%)** by **+13.44pp**

---

## 🏗️ Model Architecture

- **Backbone:** DenseNet121 (pretrained on ImageNet)
- **Attention:** Soft Attention Gates + SE (Squeeze-Excitation) Blocks
- **Feature Fusion:** 4-scale Global Average Pooling → 2816-dim representation
- **Explainability:** Grad-CAM + SHAP visualizations

---

## 📂 Dataset

- **CirrMRI600+** — 315 patients, 6,765 T2-Weighted 2D PNG slices
- **Task:** Binary classification — Moderate vs. Severe cirrhosis
- **Split:** 80% Train (5,454 slices) / 20% Test

---

## ⚙️ Training Configuration

| Parameter | Value |
|-----------|-------|
| Optimizer | AdamW (differential LR) |
| Scheduler | Cosine Annealing |
| Loss | Class-weighted Cross-Entropy |
| Label Smoothing | ε = 0.25 |
| Dropout | p = 0.65 |
| Precision | AMP/FP16 |

---

## 📁 Project Structure