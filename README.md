# Malicious URL Detection

[![Kaggle Dataset](https://img.shields.io/badge/Kaggle-Dataset-blue?logo=kaggle&style=flat-square)](https://www.kaggle.com/datasets/sid321axn/malicious-urls-dataset/data)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1kSgwDW8XVo6Gi86HGjHM6YCaWaGk_VBM?usp=sharing)

**A robust, scalable SVM + Random Forest ensemble for real-time malicious URL detection.** Trained on \~651K URLs (benign, defacement, phishing, malware) with SMOTE balancing and multi-level features (URL, domain, TF-IDF, CTI). Achieves \~92% accuracy and 0.94 AUC-ROC.

---

# Project Overview

This repository implements a hybrid SVM (RBF) + Random Forest (100 trees) soft-voting ensemble to detect malicious URLs. It includes data preprocessing, three levels of feature engineering (URL-level, domain-level, TF-IDF text features), CTI enrichment, SMOTE balancing, model training/evaluation, and scripts/notebooks for inference and visualization.

Key highlights

* Dataset sources: ISCX-URL-2016, PhishTank, Malware Domain Blacklist.
* Dataset size: \~651,191 URLs (428,103 benign; 96,457 defacement; 94,111 phishing; 32,520 malware).
* Train/test split: 80/20.
* Performance: Accuracy ≈ 0.92, Precision/Recall/F1 ≈ 0.91, AUC-ROC ≈ 0.94.
* Important features: `pri_domain`, `special_chars_count`, `url_len`.

---

# Quickstart

## Prerequisites

* Python 3.8+
* git
* Jupyter / JupyterLab (optional)
* See `requirements.txt` for Python dependencies.

## Clone

```bash
git clone [gh repo clone Mrmesmerized/Malicious-URL-Detection-using-Machine-Learning]
cd [Malicious-URL-Detection-using-Machine-Learning]
```

# Project Structure

```
├─ Preprocessing Objects/
│  ├─ feature_columns.joblib
│  ├─ label_index.joblib
│  └─ pri_domain_index.joblib
├─ notebooks/             
│  └─ MUD_MLT.ipynb              
├─ LICENSE
├─ README.md
└─ requirements.txt
```

---

# Evaluation & Metrics

Evaluation scripts produce standard classification reports and ROC curves. By default training logs accuracy, precision, recall, F1, AUC-ROC, confusion matrices, and per-class breakdown to ensure equitable performance across classes.

---

# Data & Licensing

* **Data:** Due to licensing and scale, raw datasets are **not** included. Please download from Kaggle [![Kaggle Dataset](https://img.shields.io/badge/Kaggle-Dataset-blue?logo=kaggle&style=flat-square)](https://www.kaggle.com/datasets/sid321axn/malicious-urls-dataset/data)

* **License:** This project is released under the **MIT License**. See `LICENSE` for details.

---

# Contributing

Contributions welcome! If you'd like to:

1. Fork the repo.
2. Create a feature branch.
3. Submit a PR describing changes and tests.

Please add tests for new code and document any dataset preprocessing steps.

---

# Contact & Credits

Author: `Promise Ayomide Adebayo`
Email / Contact: `mesmerizedmonds@gmail.com`
If you use this code in research or production, please cite this repository.

---
