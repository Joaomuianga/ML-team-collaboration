# Assignment 2: Supervised Learning Methods
**Classifying Breast Cancer: A Comparative Analysis**

## 📌 Overview
[cite_start]The objective of this assignment is to build a reliable binary classifier to distinguish malignant from benign breast-cancer diagnoses[cite: 302]. [cite_start]We train, tune, and compare five supervised classification algorithms, focusing on high accuracy, interpretability, and the clinical cost of misclassification[cite: 301, 356].

## 📊 Dataset
* [cite_start]**Source:** Breast Cancer Wisconsin (Diagnostic) Dataset via `sklearn.datasets`[cite: 307, 308].
* [cite_start]**Features:** 569 patient records with 30 real-valued features computed from digitised images of fine needle aspirates (FNA)[cite: 311].
* [cite_start]**Target:** Binary ($0 = \text{malignant}$, $1 = \text{benign}$)[cite: 313].

## 🧠 Methods Applied
1.  [cite_start]**K-Nearest Neighbours (KNN):** Accuracy evaluated across a sweep of $k=1$ to 20[cite: 332].
2.  [cite_start]**Logistic Regression:** Tuned over various regularisation parameters ($C$) with learned coefficient weight inspection[cite: 337, 342].
3.  [cite_start]**Support Vector Machines (SVM):** Compared using Linear, RBF, and Polynomial kernels, with grid search optimization for RBF[cite: 344, 346].
4.  [cite_start]**Neural Networks:** Multi-Layer Perceptron (`MLPClassifier`) tested with different hidden-layer architectures and activation functions[cite: 349, 350].

## 📈 Evaluation
[cite_start]Models are evaluated and compared using Accuracy, Macro F1-score, ROC curves, and AUC, alongside an analysis of computational training times[cite: 354, 355].

## 🏁 Conclusions
* [cite_start]**Best Predictive Performance:** Both **Logistic Regression ($C=0.1$)** and **SVM (RBF Kernel, $C=10, \gamma=0.01$)** achieved the highest test accuracy (**96.49%**) and Macro F1-score (**0.9627**)[cite: 823, 897, 1095]. [cite_start]The SVM models demonstrated the peak discriminative capacity with an outstanding AUC of **0.994**[cite: 1090, 1095].
* [cite_start]**Clinical Deployment Choice:** **Logistic Regression** is the recommended model for real-world deployment[cite: 1096]. [cite_start]It achieves near-identical accuracy to SVM but operates at a fraction of the computational expense (0.004s vs 0.0186s training time)[cite: 1095, 1097, 1103]. [cite_start]Most crucially, it offers full **interpretability**, allowing clinicians to evaluate risk through explicit coefficient weights[cite: 1104].
* [cite_start]**Algorithmic Trade-offs:** * **Neural Networks** experienced slight overfitting (lowest AUC of 0.9395), proving that its architectural complexity exceeded the information density of the 569 patient records[cite: 1092, 1095, 1117].
    * [cite_start]**KNN (k=11)** was competitive (94.74% accuracy) but suffered from feature redundancy and noise in higher-dimensional spaces[cite: 789, 1095, 1111].
* [cite_start]**Key Insight:** Strict feature scaling (`StandardScaler`) was mandatory to prevent massive size-metric disparities from introducing distance calculation bias[cite: 667, 668, 1113, 1114]. [cite_start]Preserving the native, mild class imbalance through stratification ensured the models learned realistic clinical probabilities[cite: 1119, 1121].