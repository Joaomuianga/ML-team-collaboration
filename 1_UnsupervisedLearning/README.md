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

## 👥 Team Workflow & Task Distribution
The pipeline for this project was divided into five specialized roles to ensure modular development and seamless collaboration across the team:

1. **Data Explorer (Role 1):** Responsible for initial data loading, managing missing value imputations, exploring baseline summary statistics, and plotting feature distributions (`1_DataExploration_StatisticsVisualization.ipynb`).
2. **PCA & Feature Selector (Role 2):** Applied Principal Component Analysis (PCA) for dimensionality reduction and implemented supervised feature selection methods (ANOVA, ReliefF, Wrapper, RFE) to identify core features (`2_PCA_FeatureSelection.ipynb`).
3. **K-Means Specialist (Role 3):** Implemented the K-Means clustering algorithm, optimized the choice of $k$ using Elbow and Silhouette metrics, and mapped cluster assignments (`3_KMeans.ipynb`).
4. **GMM Specialist (Role 4):** Fitted Gaussian Mixture Models, optimized component counts using AIC/BIC criteria, and analyzed soft vs. hard clustering boundaries (`4_GMM.ipynb`).
5. **Hierarchical Clustering Specialist (Role 5):** Evaluated and compared multiple linkage methods (Ward, complete, average) via dendrograms and selected optimal cutting thresholds (`5_HierarchicalClustering.ipynb`).

*Note: Task 6 (Evaluation Against Ground Truth using ARI metrics) and Task 7 (Written Report) were completed as a shared team synthesis effort.*

## 📈 Evaluation
The target label is only revealed at the final stage to evaluate how well our clusters align with the binarized ground truth (healthy vs. diseased) using the **Adjusted Rand Index (ARI)** and confusion matrices.

## 📂 Project Structure

```text
1_UnsupervisedLearning/
│
├── data/
│   ├── 01_raw/                      # Original UCI dataset
│   ├── 02_cleaned/                  # Imputed and standardized data (Role 1)
│   └── 03_selected/                 # Feature selection outputs and PCA models (Role 2)
│
├── docs/
│   ├── guide/                       # Assignment instructions
│   └── report/
│       └── Team11_UnsupervisedLearning_Report.pdf  # Final scientific report
│
├── Figures/                         # Saved visualizations: boxplots, scatter matrices (Role 1)
│
├── notebooks/                       # Modular pipeline
│   ├── 1_DataExploration_StatisticsVisualization.ipynb
│   ├── 2_PCA_FeatureSelection.ipynb
│   ├── 3_KMeans.ipynb
│   ├── 4_GMM.ipynb
│   ├── 5_HierarchicalClustering.ipynb
│   └── Team11_UnsupervisedLearning_Notebook.ipynb  # Final unified deliverable
│
├── Team11_UnsupervisedLearning.zip  # Final submission archive
└── README.md                        # This file