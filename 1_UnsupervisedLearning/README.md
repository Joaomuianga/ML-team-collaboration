# Assignment 1: Unsupervised Learning Methods
**Clustering Patient Data: A Comparative Analysis**

## 📌 Overview
[cite_start]This assignment focuses on discovering meaningful patient subgroups without using diagnostic labels[cite: 197]. [cite_start]We apply and compare three unsupervised learning methods to cluster clinical measurements, mirroring the real-world challenge of identifying patient profiles before a formal diagnosis is available[cite: 196, 198].

## 📊 Dataset
* [cite_start]**Source:** Heart Disease dataset (UCI Machine Learning Repository)[cite: 201, 202].
* [cite_start]**File:** `processed.cleveland.data`[cite: 204].
* [cite_start]**Features:** 303 patient records with 13 clinical features (e.g., age, cholesterol, resting blood pressure) and one hidden target variable[cite: 204, 205].

## 🧠 Methods Applied
1.  [cite_start]**Dimensionality Reduction:** Principal Component Analysis (PCA) for 2D and 3D visualization[cite: 467, 468].
2.  [cite_start]**K-Means Clustering:** Tuned using the Elbow Method and Silhouette Scores[cite: 239, 240].
3.  [cite_start]**Gaussian Mixture Models (GMM):** Optimized using BIC/AIC criteria[cite: 247].
4.  [cite_start]**Hierarchical Clustering:** Evaluated using different linkage methods (Ward, complete, average) via dendrograms[cite: 252].

## 📈 Evaluation
[cite_start]The target label is only revealed at the final stage to evaluate how well our clusters align with the binarized ground truth (healthy vs. diseased) using the **Adjusted Rand Index (ARI)** and confusion matrices [cite: 257-259, 452].

## 🏁 Conclusions
* [cite_start]**Best Performing Method:** Hierarchical Clustering ($k=2$) achieved the highest validation alignment with an **ARI score of 0.3037**[cite: 587, 606]. [cite_start]It naturally captured the macroscopic clinical reality by separating healthy individuals from sick patients with minimal fragmentation[cite: 587, 588].
* [cite_start]**Algorithmic Trade-offs:** * **K-Means ($k=4$)** effectively pinpointed "very healthy" and "very sick" cohorts but struggled with mixed borderline cases, suffering an ARI drop (0.2468) due to over-fragmenting the binary target[cite: 589, 590, 597].
    * [cite_start]**GMM ($k=7$)** yielded the lowest ARI score (0.2021) as 303 records proved insufficient to properly estimate complex covariance matrices, resulting in massive clinical oversegmentation[cite: 591, 604, 614].
* [cite_start]**Key Insight:** Healthcare data structure is highly non-linear with severe class overlap[cite: 447, 469]. [cite_start]Feature selection confirmed that local structure is driven heavily by clinical variables such as major vessels (`ca`), maximum heart rate (`thalach`), and chest pain type (`cp_4`)[cite: 502, 512, 518].