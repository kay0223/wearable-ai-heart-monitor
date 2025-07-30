# Real-Time Cardiac Anomaly Detection with AI and Wearable Health Monitors

## Overview

This repository contains the research, datasets, and code implementations for the project:
**"Wearable Health Monitors and AI: Real-Time Anomaly Detection in Heart Diseases"**.
The goal is to develop AI-powered models capable of detecting anomalies in heart activity using real-time data from wearable health monitoring devices.

---

## Objectives
- Develop a **real-time anomaly detection model** for heart diseases using wearable devices.
- Utilize **time-series physiological signals** (e.g., ECG) from public datasets like **MIT-BIH Arrhythmia**.
- Apply **machine learning** and **deep learning** methods for accurate detection.
- Integrate AI models into a potential real-time monitoring system for early intervention.

---

## Repository Structure
```
.
├── data/               # Raw and preprocessed datasets
├── notebooks/          # Jupyter notebooks for experiments
├── src/                # Source code for model development
│   ├── preprocessing/  # Data cleaning and preprocessing scripts
│   ├── models/         # Machine learning & deep learning models
│   ├── evaluation/     # Model evaluation scripts
├── results/            # Plots, metrics, and experimental results
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

---

## Dataset
We plan to use the following datasets from [PhysioNet](https://physionet.org/):
- **MIT-BIH Arrhythmia Database**
- **MIT-BIH Supraventricular Arrhythmia Database**
- **INCART 12-lead Arrhythmia Database**
- **Sudden Cardiac Death Holter Database**

---

## Methods & Techniques
- **Signal Preprocessing:** Noise filtering, segmentation, normalization
- **Feature Engineering:** Heart rate variability (HRV), morphological features
- **Machine Learning Models:** Random Forest, SVM, Logistic Regression
- **Deep Learning Models:** LSTMs, CNNs for time-series ECG analysis
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-score, ROC-AUC

---

## Installation
```bash
# Clone this repository
git clone https://github.com/kay0223/real-time-cardiac-anomaly-ai.git

# Navigate to the project folder
cd real-time-cardiac-anomaly-ai

# Install dependencies
pip install -r requirements.txt
```

---

## Expected Outcomes
- Real-time detection of cardiac anomalies
- Integration capability with wearable devices for live monitoring
- A foundation for further research into AI-driven cardiac healthcare solutions

---

## References
- Moody, G. B., & Mark, R. G. (2001). The impact of the MIT-BIH Arrhythmia Database. *IEEE Engineering in Medicine and Biology Magazine*.
- Bala, A., et al. (2025). Exploring the Impact of Wearable Health Devices on Chronic Disease Management.
- Obaidur, A., et al. (2024). Real-Time Predictive Health Monitoring Using AI-Driven Wearable Sensors.
- Wu, C. T., Wang, S. M., Su, Y. E., Hsieh, T. T., Chen, P. C., Cheng, Y. C., ... & Lai, F. (2022). A precision health service for chronic diseases: development and cohort study using wearable device, machine learning, and deep learning. IEEE journal of translational engineering in health and medicine, 10, 1-14.
- Wu, Z., Guo, C. Deep learning and electrocardiography: systematic review of current techniques in cardiovascular disease diagnosis and management. BioMed Eng OnLine 24, 23 (2025). 
- Okpanachi, Akuchinyere & Emmanuel, Igba & Imoh, Paul & Dzakpasu, Noble & Nyaledzigbor, Mathew. (2025). Leveraging Digital Biomarkers and Advanced Data Analytics in Medical Laboratory to Enhance Early Detection and Diagnostic Accuracy in Cardiovascular Diseases. International Journal of Scientific Research in Science and Technology. 12. 468-495. 10.32628/IJSRST251222590. 


---

## Contributing
We welcome contributions! Please fork the repo and submit a pull request.

---

## Contact
For questions or collaborations, reach out to:
- **Kay** - kay0223@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/kay-jiang-10306480/
