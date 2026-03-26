# Gradient Boosting Demystified: XGBoost vs Sklearn GBM

> A machine learning tutorial exploring the effect of number of trees, tree depth, and regularisation on gradient boosting performance.

---

## Overview

This repository contains the code and report for a tutorial on **Gradient Boosting algorithms**, with a focus on two widely-used implementations:

- **Scikit-learn `GradientBoostingClassifier`** — the classic, interpretable baseline
- **XGBoost `XGBClassifier`** — a highly optimised, regularised extension

The tutorial investigates three key hyperparameters through controlled experiments:

| Hyperparameter | What it controls |
|---|---|
| `n_estimators` | Number of boosting rounds (trees) |
| `max_depth` | Depth of each decision tree |
| Regularisation | Subsampling, feature sampling, L1/L2 penalties |

**Dataset:** Breast Cancer Wisconsin (Diagnostic) — 569 samples, 30 features, binary classification (malignant vs benign).

---


## Getting Started

### Prerequisites

Python 3.8 or higher is required. Install all dependencies with:

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost jupyter
```

### Running the Notebook

```bash
git clone https://github.com/YOUR_USERNAME/gradient-boosting-tutorial.git
cd gradient-boosting-tutorial
jupyter notebook gradient_boosting_tutorial.ipynb
```



---

## Experiments

### Experiment 1 — Number of Trees (`n_estimators`)

Trains a GBM with `max_depth=3` for n_estimators ranging from 1 to 300. Shows how train and test accuracy diverge as trees increase, illustrating the bias-variance trade-off.

### Experiment 2 — Tree Depth (`max_depth`)

Fixes `n_estimators=100` and varies `max_depth` from 1 to 8. Visualises the widening generalisation gap as depth increases, demonstrating why shallow trees (depth 2–4) are optimal for gradient boosting.

### Experiment 3 — Regularisation

Deliberately overfits with `max_depth=6`, then applies four regularisation configurations evaluated with 5-fold cross-validation. Shows how subsampling, feature sampling, and leaf constraints each reduce overfitting.

---

## Key Results

| Metric | Value |
|---|---|
| Test Accuracy | 0.9474 |
| ROC-AUC | 0.9940 |
| F1-Score | 0.9589 |

Best configuration: `n_estimators=100`, `max_depth=3`, `learning_rate=0.1`, `subsample=0.8`

---

## Accessibility

This tutorial was designed with accessibility in mind:

- All figures use a **colour-blind friendly palette** (based on the Wong 2011 colour set)
- Figures include descriptive captions
- Tables include clear headers and sufficient contrast
- Code is fully commented for screen reader compatibility

---

## References

1. Chen, T. & Guestrin, C. (2016). XGBoost: A Scalable Tree Boosting System. *KDD '16*. https://doi.org/10.1145/2939672.2939785
2. Friedman, J.H. (2001). Greedy function approximation: A gradient boosting machine. *Annals of Statistics*, 29(5), 1189–1232.
3. Pedregosa, F. et al. (2011). Scikit-learn: Machine Learning in Python. *JMLR*, 12, 2825–2830.
4. Wolberg, W.H., Street, W.N., & Mangasarian, O.L. (1995). Breast Cancer Wisconsin (Diagnostic) Data Set. UCI Machine Learning Repository.

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute this code with attribution.

