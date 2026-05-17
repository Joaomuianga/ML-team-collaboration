# Assignment 1: Unsupervised Learning Methods
**Clustering Patient Data: A Comparative Analysis**

## 📌 Overview
This assignment focuses on discovering meaningful patient subgroups without using diagnostic labels. We apply and compare three unsupervised learning methods to cluster clinical measurements, mirroring the real-world challenge of identifying patient profiles before a formal diagnosis is available.

## 📊 Dataset
* **Source:** Heart Disease dataset (UCI Machine Learning Repository).
* **File:** `processed.cleveland.data`.
* **Features:** 303 patient records with 13 clinical features (e.g., age, cholesterol, resting blood pressure) and one hidden target variable.

## 🧠 Methods Applied
1. **Dimensionality Reduction:** Principal Component Analysis (PCA) for 2D and 3D visualization.
2. **K-Means Clustering:** Tuned using the Elbow Method and Silhouette Scores.
3. **Gaussian Mixture Models (GMM):** Optimized using BIC/AIC criteria.
4. **Hierarchical Clustering:** Evaluated using different linkage methods (Ward, complete, average) via dendrograms.

## 📈 Evaluation
The target label is only revealed at the final stage to evaluate how well our clusters align with the binarized ground truth (healthy vs. diseased) using the **Adjusted Rand Index (ARI)** and confusion matrices.

## 📂 Project Structure

```text
1_UnsupervisedLearning/
│
├── data/
│   ├── 01_raw/                      # Original UCI dataset
│   ├── 02_cleaned/                  # Imputed and standardized data
│   └── 03_selected/                 # Feature selection outputs and PCA models
│
├── docs/
│   ├── guide/                       # Assignment instructions
│   └── report/
│       └── Team11_UnsupervisedLearning_Report.pdf  # Final scientific report
│
├── Figures/                         # Saved visualizations (boxplots, scatter matrices)
│
├── notebooks/                       # Modular pipeline
│   ├── 1_DataExploration_StatisticsVisualization.ipynb
│   ├── 2_PCA_FeatureSelection.ipynb
│   ├── 3_KMeans.ipynb
│   ├── 4_GMM.ipynb
│   ├── 5_HierarchicalClustering.ipynb
│   └── Team11_UnsupervisedLearning_Notebook...     # Final unified deliverable
│
└── README.md                        # This file