# Dry Bean Classification System

## Background
You are to automate the classification of dry beans into **seven species** based on their **morphological features**. Manual sorting is slow and prone to error, hence the need for an ML-driven solution.

---

## Dataset Summary
- **Source**: Dry Bean Dataset
- **Samples**: 13,611
- **Target Classes**: 7 bean types (e.g., Seker, Barbunya, Bombay, etc.)
- **Selected Features Used**:
  - `Perimeter`
  - `Eccentricity`
  - `Solidity`
  - `roundness`
  - `ShapeFactor1`
  - `ShapeFactor2`
  - `ShapeFactor4`

> *Other features were dropped due to perfect or near-perfect feature-to-feature correlation, or weak target correlation.*

---

## Workflow Summary

### 1. Exploratory Data Analysis (EDA)
- Distribution plots for selected features
- Boxplots & pairplots to visualize class separation
- Correlation heatmap for feature selection

### 2. Model Training
Trained and evaluated the following models:
- Logistic Regression (Best performing)
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

All models evaluated using **cross-validation** for robust performance measurement.

### 3. Feature Selection
- **Recursive Feature Elimination (RFE)** used to identify optimal feature subsets.

### 4. Dimensionality Reduction
- **PCA** applied to:
  - Reduce dimensionality
  - Visualize class separation in 2D

### 5. Hyperparameter Tuning
- `GridSearchCV` and `RandomizedSearchCV` used to tune:
  - Gradient Boosting
  - XGBoost

### 6. Evaluation Metrics
- Confusion matrices
- Classification reports
- Per-class accuracy visualizations

---

## Results & Insights
- Most influential features: **Solidity**, **ShapeFactors**, and **Eccentricity**
- **Logistic Regression** delivered:
  - Highest accuracy
  - Best balance of simplicity and performance
  - Lower risk of overfitting compared to tree-based models
- PCA visualization showed distinct clustering of several bean types
- Even with reduced dimensionality, performance remained strong

---

## Recommendation
We recommend deploying the **Logistic Regression model** in the automated dry bean sorting system. It provides:
- High accuracy
- Fast inference
- Model transparency & interpretability
- Low resource requirements

---

## Deployment
The best model was deployed via **Streamlit**, providing:
- Upload interface for new bean measurements
- Instant classification feedback

---

## Author
**Benedict Ouma**, 2025  
*Forensic & Agricultural ML Solutions*
