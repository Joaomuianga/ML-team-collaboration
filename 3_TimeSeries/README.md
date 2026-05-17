# Assignment 3: Time Series Analysis
**Classifying Cardiac Arrhythmias: A Comparative Analysis**

## 📌 Overview
This assignment tackles the challenge of temporal modeling in healthcare. We engineer features from raw electrocardiogram (ECG) signals and compare sequence classifiers to categorize individual heartbeats into clinically meaningful arrhythmias.

## 📊 Dataset
* **Source:** MIT-BIH Arrhythmia Database (PhysioNet) accessed via the `wfdb` library.
* **Features:** 14 patient records, yielding ~35,000-40,000 labelled beats. 8 engineered features per beat capturing rhythm, morphology, and repolarisation.
* **Target:** AAMI 3-Class Scheme (Normal [N], Supraventricular ectopic [S], Ventricular ectopic [V]).

## 🧠 Methods Applied
Data is structured into sliding windows of $T=10$ consecutive beats. The models are built using **PyTorch**:
1.  **Recurrent Neural Networks (RNN):** A vanilla sequence classifier to understand the vanishing gradient problem.
2.  **Long Short-Term Memory (LSTM):** An extension to evaluate if gating mechanisms improve performance on this sequence length.

## 📈 Evaluation
Models are evaluated on an imbalanced dataset, making Macro F1 and per-class recall (especially for S and V beats) the primary metrics for success, alongside confusion matrices and clinical deployment viability.