# Results

Key figures from the modelling and evaluation pipeline in [`../research_project.ipynb`](../research_project.ipynb).

| File | What it shows | Why it matters |
|------|---------------|----------------|
| `class_distribution.png` | Count of beats per AAMI class (N, SVEB, VEB, F, Q) | Confirms the heavy class imbalance (>70% Normal) that drives the evaluation strategy |
| `pca_projection.png` | 2-D PCA of the engineered features, coloured by class | Shows VEB separating from Normal while SVEB overlaps — explains where the models struggle |
| `rf_confusion_matrix.png` | Confusion matrix, Random Forest (test set) | Reveals that high accuracy hides low sensitivity on abnormal beats — the core finding |
| `rf_roc_pr_curves.png` | Per-class ROC and Precision–Recall curves, Random Forest | Used to pick operating points that respect the survey's acceptable false-positive rate |
| `rf_feature_importance.png` | Top engineered features by importance | Interpretability — which ECG features (RR intervals, QRS morphology) drive predictions |
| `dl_calibration_curve.png` | Calibration curve + Brier score, deep-learning model | Shows whether predicted probabilities are trustworthy, not just the labels |

> Generated from the MIT-BIH Arrhythmia dataset (PhysioNet). Subject-wise train/validation/test split; figures reflect held-out, unseen-patient test data.
