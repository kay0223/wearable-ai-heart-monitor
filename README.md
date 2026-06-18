# Real-Time Cardiac Anomaly Detection with AI and Wearable Health Monitors

Machine-learning and deep-learning models for detecting cardiac anomalies in ECG signals, built as a data-science research project on the **MIT-BIH Arrhythmia** benchmark. The work pairs a model-benchmarking pipeline (classical + deep learning) with a user survey that grounds the model's design choices in real patient, caregiver and clinician needs.

> Academic project — *MDS606 Data Science Research & Ethics*, Sydney Polytechnic Institute (2025). Group research proposal; this repository focuses on the modelling and evaluation work.

---

## My contribution

This was a five-person group project. **My individual contribution covered the modelling, evaluation and research-design components:**

- Designed the **research methodology and evaluation framework** for comparing AI models against rule-based baselines.
- Built and benchmarked the **machine-learning pipeline** end to end (see [`notebooks/`](notebooks/)): data preparation, model training, evaluation and visualisation.
- Designed and analysed the **user survey** (descriptive statistics, chi-square / cross-tabulation, and thematic analysis of open-ended responses) and translated the findings into concrete model requirements.

Teammates contributed the literature review, ethics, budget/timeline and parts of the written proposal.

---

## Approach

**Data.** MIT-BIH Arrhythmia Database (PhysioNet), with heartbeats grouped into the five clinically meaningful **AAMI classes**: Normal (N), Supraventricular ectopic (SVEB), Ventricular ectopic (VEB), Fusion (F), and Unknown (Q).

**Methodology highlights** (designed to reflect real-world deployment):

- **Subject-wise 60/20/20 split** by patient record — models are always tested on *unseen patients*, preventing patient leakage and over-optimistic scores.
- **Train-only scaling** — z-score normalisation fitted on the training set and applied to validation/test, avoiding data leakage.
- **Class-imbalance handling** — class weighting (Normal beats are >70% of the data), with minority classes prioritised in evaluation.

## Models

| Type | Models |
|------|--------|
| Classical baselines | Logistic Regression, Random Forest (balanced class weights) |
| Deep learning (PyTorch) | 1D Convolutional Neural Network (CNN-1D), Bidirectional LSTM (BiLSTM) |

## Evaluation

Because accuracy is misleading on imbalanced clinical data, the pipeline reports:

- **Macro AUROC, AUPRC and F1** (equal weight to minority/abnormal classes)
- **Per-class ROC and Precision–Recall curves**
- **Confusion matrices**
- **Calibration curves + Brier score** (are the predicted probabilities trustworthy?)
- **Decision-curve analysis** (any-arrhythmia vs normal)
- **PCA visualisation** and **Random Forest feature importance** for interpretability

The Random Forest reaches high headline accuracy by over-predicting "Normal," but falls short on the **sensitivity** that cardiac screening requires — which is the motivation for the deep-learning models that handle the imbalanced minority classes better.

## Connecting the survey to the model

A preliminary survey of patients, caregivers and clinicians informed the design:

- ~40% expressed moderate-to-high trust in AI-based ECG alerts; ~30% low trust.
- Median **acceptable false-positive rate of 1–5%** → the model should prioritise **specificity**, and operating points are chosen from PR curves accordingly.
- 60%+ raised privacy concerns → favour **explainable models** and on-device/local processing.

These thresholds feed directly into how alert operating points (and smoothing/debounce settings) are selected during evaluation.

---

## Repository structure

```
.
├── notebooks/        # Jupyter notebook(s): full modelling & evaluation pipeline
├── results/          # Saved plots (class distribution, ROC/PR, confusion matrix, calibration)
├── requirements.txt  # Python dependencies
├── LICENSE
└── README.md
```

> **Note on data:** the MIT-BIH dataset is not redistributed here. Download it from [PhysioNet](https://physionet.org/content/mitdb/) and place it under a local `data/` folder.

## Tech stack

`Python` · `pandas` · `NumPy` · `scikit-learn` · `PyTorch` · `Matplotlib`

## How to run

```bash
# Clone
git clone https://github.com/kay0223/wearable-ai-heart-monitor.git
cd wearable-ai-heart-monitor

# (Optional) create a virtual environment
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook notebooks/
```

> The notebook includes a `FAST` flag that subsamples the data for a quick end-to-end run; set it to `False` and increase epochs for full training.

---

## Team

Group 1 — MDS606 Data Science Research & Ethics, Sydney Polytechnic Institute:
Kay Jiang, Sharon Kandie, Julian David Ravelo Cuartas, Molly Cherotich, Zhibing Zheng.

## License

Released under the [MIT License](LICENSE).

## Contact

**Kay Jiang** · [kay0223@gmail.com](mailto:kay0223@gmail.com) · [LinkedIn](https://www.linkedin.com/in/kay-jiang-10306480/)

