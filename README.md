# Malicious URL Detection

[![Dataset](https://www.kaggle.com/datasets/sid321axn/malicious-urls-dataset/data) \[![Open in Colab][colab-badge]]\[[COLAB\_LINK](https://colab.research.google.com/drive/1kSgwDW8XVo6Gi86HGjHM6YCaWaGk_VBM?usp=sharing)]

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
git clone [GITHUB_REPO_URL]
cd [REPO_NAME]
```

## Virtual environment & install

```bash
python -m venv env
# Activate:
# Windows:
# .\env\Scripts\activate
# macOS / Linux:
source env/bin/activate

pip install -r requirements.txt
```

## Run interactively (Colab)

Click the badge above or open:
`[COLAB_LINK]` — contains an executable notebook with preprocessing, training, and demo inference.

---

# Usage

## Training (local)

```bash
python scripts/train.py \
  --data-path [PATH_TO_CSV_OR_FOLDER] \
  --output models/ensemble.pkl \
  --smote True \
  --rf-trees 100 \
  --svm-kernel rbf
```

(Placeholders in brackets require your input.)

## Inference (single URL)

```bash
python scripts/predict.py --model models/ensemble.pkl --url "http://example.com/login"
```

## Batch inference

```bash
python scripts/batch_predict.py --model models/ensemble.pkl --input urls_to_score.csv --output predictions.csv
```

---

# Notebooks & Demos

* `notebooks/` — EDA, feature engineering walkthrough, model training notebook.
* `notebooks/demo.ipynb` — simple demo and visualization of metrics and feature importances.
* `notebooks/README.md` — brief guide to run notebooks.

---

# Project Structure (example)

```
├─ data/                     # raw and processed data (not included)
├─ notebooks/                # analysis and Colab-ready notebooks
├─ scripts/
│  ├─ train.py
│  ├─ predict.py
│  └─ batch_predict.py
├─ models/                   # saved model artifacts (large files excluded)
├─ src/
│  ├─ featurize.py
│  ├─ dataset.py
│  └─ utils.py
├─ requirements.txt
├─ LICENSE
└─ README.md
```

*(Adjust paths/files to match this repo.)*

---

# Evaluation & Metrics

Evaluation scripts produce standard classification reports and ROC curves. By default training logs accuracy, precision, recall, F1, AUC-ROC, confusion matrices, and per-class breakdown to ensure equitable performance across classes.

---

# Data & Licensing

* **Data:** Due to licensing and scale, raw datasets are **not** included. Please download raw sources and place them in `data/raw/`:

  * ISCX-URL-2016: `[INSERT_LINK_or_INSTRUCTIONS]`
  * PhishTank: `[INSERT_LINK_or_INSTRUCTIONS]`
  * Malware Domain Blacklist: `[INSERT_LINK_or_INSTRUCTIONS]`

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

Author: `[AUTHOR_NAME]`
Email / Contact: `[CONTACT_PLACEHOLDER]`
If you use this code in research or production, please cite this repository.

---
