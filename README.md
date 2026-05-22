# House Price Prediction

[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Project Type](https://img.shields.io/badge/Project-Internship-orange.svg)]()

An end-to-end Machine Learning pipeline utilizing classification, regression, and unsupervised clustering techniques to predict property values, identify locality tiers, and segment real estate markets across 5 major economic hubs in India.

**Presenter / Core Developer:** MODASSIR QUAISAR  
**Project Context:** Internship Research & Operationalization Project  

---

## 📌 Executive Summary

Real estate evaluation is a complex, non-linear problem driven by structural layout, localized socioeconomics, and geographical accessibility. This project leverages an aggregated dataset of **12,000 residential records** across Mumbai, Bangalore, Hyderabad, Pune, and Nagpur to build a modular, automated appraisal system. 

By employing a multi-phase machine learning toolkit, the framework successfully automates neighborhood classification (with up to 97% accuracy), predicts structural asset values (explaining 91.5% of market variance), and discovers latent buyer personas using unsupervised market clustering.

---

## 🛠️ The Analytical Toolkit (Algorithms Used)

The framework evaluates and cross-compares six fundamental algorithms across three analytical phases:

1. **Classification (Locality Tiering):**
   * **Logistic Regression (L2 Regularization):** Establishes parametric decision boundaries to classify neighborhoods into Budget, Mid, and Premium brackets.
   * **Decision Tree Classifier:** Generates interpretable, non-linear hierarchical logical splits for categorical categorization.
   * **K-Nearest Neighbors (KNN):** Implements localized instance-based voting to identify spatial clusters based on feature proximity.

2. **Regression (Continuous Asset Appraisal):**
   * **Simple Linear Regression:** Serves as a baseline model predicting price exclusively via spatial area dimensions.
   * **Multi-Linear Regression:** Integrates the full multidimensional matrix (structural, localized safety indices, transit weights) to minimize cost functions.

3. **Clustering (Market Segmentation):**
   * **k-means Clustering:** Operates an unsupervised Euclidean distance optimization algorithm ($K=3$) to profile distinct socioeconomic real estate brackets.

---

## 📊 Dataset & Feature Engineering

The underlying data repository (`house_price_dataset_india_12k.csv`) consists of **12,000 records** and **21 strategic attributes**.

### Data Integrity & Physical Guards
To enforce real-world structural consistency, rigorous automated programmatic validation rules were applied:
* **Spatial Constraint:** Carpet Area $\le$ Super-Built Area
* **Vertical Constraint:** Unit Floor Level $\le$ Total Building Floors
* **Outlier Strategy:** Intentionally preserved 545 high-end luxury outlier data points to avoid truncating high-value premium models.

### Preprocessing Pipeline
* **Categorical Encoding:** One-Hot Vectorization applied to nominal features (`City`, `Furnishing Status`).
* **Feature Scaling:** Applied standard Z-score normalization ($\mu = 0, \sigma = 1$) across distance-sensitive features to eliminate metric scaling bias.
* **Partitioning:** Partitioned into an 80/20 train-test split ensuring out-of-sample cross-validation.

---

## 📈 Key Performance Metrics & Results

### Phase 1: Locality Classification Results
| Algorithm Configuration | Testing Accuracy | Macro F1-Score | Strategic Assessment |
| :--- | :---: | :---: | :--- |
| **Logistic Regression (L2)** | **97.00%** | **0.97** | Optimal Linear Separation |
| **Decision Tree Classifier** | 91.00% | 0.91 | Highly Interpretable Splits |
| **K-Nearest Neighbors (KNN)**| 76.42% | 0.76 | Distorted by Multidimensional Noise |

*Insight: The high accuracy of Logistic Regression proves that property price tiers are strongly linearly separable once size-to-cost scales are properly normalized.*

### Phase 2: Valuation Engine Performance
* **Simple Linear Regression (Baseline - Area Only):** Achieved an $R^2 = 54.3\%$.
* **Multi-Linear Regression (Comprehensive Stack):** Achieved an **$R^2 = 91.5\%$**. 
* *Operational Impact:* Expanding to the multi-linear structure reduced Root Mean Squared Error (RMSE) drastically from ₹45 Lakhs down to **₹19.4 Lakhs**. Negative regression coefficients confirmed that structural age significantly reduces market capitalization, while positive weights highlighted transit connectivity alpha.

### Phase 3: Unsupervised Market Archetypes (k-means)
By implementing k-means with $K=3$, the algorithm mapped out three intuitive market segments:
1. **Luxury Elite:** Average space $\approx$ 1,677 sqft, Average Price $\approx$ ₹2.14 Crores, Close proximity to city center ($\approx$ 10.6 km).
2. **Mid-Market Core:** Average space $\approx$ 1,082 sqft, Average Price $\approx$ ₹1.10 Crores, Mid-distance ($\approx$ 11.2 km).
3. **Suburban Budget:** Average space $\approx$ 741 sqft, Average Price $\approx$ ₹57.36 Lakhs, Far suburban ring ($\approx$ 18.0 km).

---
