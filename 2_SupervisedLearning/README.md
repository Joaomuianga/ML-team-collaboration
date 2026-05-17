# Assignment 2: Supervised Learning Methods
**Classifying Breast Cancer: A Comparative Analysis**

## 📌 Overview
The objective of this assignment is to build a reliable binary classifier to distinguish malignant from benign breast-cancer diagnoses. We train, tune, and compare five supervised classification algorithms, focusing on high accuracy, interpretability, and the clinical cost of misclassification.

## 📊 Dataset
* **Source:** Breast Cancer Wisconsin (Diagnostic) Dataset via `sklearn.datasets`.
* **Features:** 569 patient records with 30 real-valued features computed from digitised images of fine needle aspirates (FNA).
* **Target:** Binary (0 = malignant, 1 = benign).

## 🧠 Methods Applied
1. **K-Nearest Neighbours (KNN):** Accuracy evaluated across a sweep of k=1 to 20.
2. **Logistic Regression:** Tuned over various regularisation parameters (C) with learned coefficient weight inspection.
3. **Support Vector Machines (SVM):** Compared using Linear, RBF, and Polynomial kernels, with grid search optimization for RBF.
4. **Neural Networks:** Multi-Layer Perceptron (`MLPClassifier`) tested with different hidden-layer architectures and activation functions.

## 📈 Evaluation
Models are evaluated and compared using Accuracy, Macro F1-score, ROC curves, and AUC, alongside an analysis of computational training times.

## 📂 Project Structure

```text
2_SupervisedLearning/
│
├── data/
│   ├── 1_raw/                       # Original X and y datasets
│   └── 2_processed/                 # Scaled and train/test split data (X_train, y_train, etc.)
│
├── docs/
│   ├── guide/                       # Assignment instructions and guidelines
│   └── report/
│       └── Team11_SupervisedLearning_Report.pdf  # Final scientific report
│
├── figures/
│   └── exploration/                 # Saved EDA visualizations (boxplots, heatmaps, histograms)
│
├── notebooks/                       # Modular machine learning pipeline
│   ├── 1_Preprocessing.ipynb
│   ├── 2_KNN.ipynb
│   ├── 3_LogisticRegression.ipynb
│   ├── 4_SupportVectorMachine.ipynb
│   ├── 5_NeuralNetwork.ipynb
│   └── Team11_SupervisedLearning_Notebook.ipynb  # Final unified deliverable
│
├── results/                         # Evaluation outputs and model comparisons
│   ├── roc_curves.png
│   └── summary_results.csv
│
└── README.md                        # This file (Project overview & conclusions)