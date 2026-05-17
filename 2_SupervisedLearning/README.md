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

## 👥 Team Workflow & Task Distribution
The development pipeline was divided into five modular roles to efficiently cover data preparation and algorithm benchmarking:

1. **Data Explorer (Role 1):** Handled data loading, class balance reporting, and exploratory data analysis (EDA), generating feature distributions (histograms/boxplots) and correlation heatmaps to understand baseline relationships.
2. **Feature Engineer (Role 2):** Managed the stratified train/test partitioning, handled standard scaling, and conducted near-zero variance and correlation-based feature filtering to minimize multicollinearity.
3. **KNN and Logistic Regression Specialist (Role 3):** Built and optimized K-Nearest Neighbors pipelines (sweeping $k$ parameters) and trained regularized Logistic Regression estimators, analyzing model coefficients for clinical interpretability.
4. **SVM Specialist (Role 4):** Evaluated performance over Linear, Polynomial, and RBF kernels, implementing hyperparameter grid searches across $C$ and $\gamma$ spaces.
5. **Neural Network Specialist (Role 5):** Configured multi-layer perceptron hidden structures, benchmarked loss reduction behaviors using different activation functions, and tracked training curves.

*Note: Model Comparison (Task 7) and the Written Report (Task 8) were completed as a shared team synthesis effort.*

## 📂 Project Structure

```text
2_SupervisedLearning/
│
├── data/
│   ├── 1_raw/                       # Original X and y datasets
│   └── 2_processed/                 # Scaled and train/test split data (Role 2)
│
├── docs/
│   ├── guide/                       # Assignment instructions and guidelines
│   └── report/
│       └── Team11_SupervisedLearning_Report.pdf  # Final scientific report
│
├── figures/
│   └── exploration/                 # Saved EDA visualizations: boxplots, heatmaps, histograms (Role 1)
│
├── notebooks/                       # Modular machine learning pipeline
│   ├── 1_Preprocessing.ipynb
│   ├── 2_KNN.ipynb
│   ├── 3_LogisticRegression.ipynb
│   ├── 4_SupportVectorMachine.ipynb
│   ├── 5_NeuralNetwork.ipynb
│   └── Team11_SupervisedLearning_Notebook.ipynb  # Final unified deliverable
│
├── results/                         # Evaluation outputs and model comparisons (Task 7)
│   ├── roc_curves.png
│   └── summary_results.csv
│
└── README.md                        # This file