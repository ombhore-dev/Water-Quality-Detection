# 💧 Water Quality Detection — ML Classification Model

> End-to-end Machine Learning project to predict water potability from physicochemical parameters using **Random Forest, SVM & Logistic Regression** — with hyperparameter tuning, feature importance analysis, and full EDA.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## 🔍 Problem Statement

Access to safe drinking water is a global public health priority. This project builds an ML classification model to predict whether water is **safe (potable)** or **unsafe** based on 9 physicochemical parameters — enabling faster, data-driven water safety screening.

---

## 🗂️ Project Structure

```
Water-Quality-Detection/
├── data/
│   └── water_potability.csv          # Kaggle Water Potability dataset
├── notebooks/
│   └── Water_Quality_Detection.ipynb # Full EDA + ML pipeline
├── requirements.txt
└── README.md
```

---

## 🚀 Key Results

| Model | Accuracy | ROC-AUC | CV Accuracy |
|---|---|---|---|
| Logistic Regression | ~62% | ~0.67 | ~62% |
| Random Forest | ~67% | ~0.72 | ~67% |
| SVM | ~67% | ~0.72 | ~66% |
| **Random Forest (Tuned)** | **~68%** | **~0.73** | **~68%** |

> 📌 ~68% accuracy is consistent with published benchmarks on this dataset. Water potability is a hard prediction problem — physicochemical parameters alone don't capture microbial content or treatment history.

---

## 📓 Notebook Breakdown

### 1. Exploratory Data Analysis
- Target distribution (safe vs unsafe)
- Feature distributions — safe vs unsafe overlay histograms
- Correlation heatmap
- Feature boxplots — outlier detection per class

### 2. Data Preprocessing
- Median imputation for missing values (pH, Sulfate, Trihalomethanes)
- Stratified train/test split (80/20)
- StandardScaler for distance-based models (LR, SVM)

### 3. Model Training & Evaluation
- 3 models: Logistic Regression, Random Forest, SVM
- Metrics: Accuracy, ROC-AUC, 5-Fold Cross Validation
- ROC curves for all models
- Confusion matrix for best model

### 4. Hyperparameter Tuning
- GridSearchCV on Random Forest
- Parameters tuned: `n_estimators`, `max_depth`, `min_samples_split`

### 5. Feature Importance
- Top predictors: **Sulfate, pH, Chloramines**
- Visualized via Random Forest feature importance scores

---

## 🔑 Top Findings

| # | Finding |
|---|---|
| 1 | **Sulfate** is the strongest predictor of water potability |
| 2 | **pH extremes** (too high or too low) correlate with unsafe water |
| 3 | **Chloramines** at elevated levels linked to unsafe classification |
| 4 | Features are largely independent — low multicollinearity |

---

## 🛠️ Setup & Run

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/Water-Quality-Detection.git
cd Water-Quality-Detection
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Download the dataset
Get the dataset from Kaggle:
👉 [Water Potability Dataset — Kaggle](https://www.kaggle.com/datasets/adityakadiwal/water-potability)

Place `water_potability.csv` in the `data/` folder.

### 4. Run the notebook
```
notebooks/Water_Quality_Detection.ipynb
```

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

---

## 📁 Dataset

**Source:** [Kaggle — Water Potability](https://www.kaggle.com/datasets/adityakadiwal/water-potability)
**Rows:** 3,276 water samples
**Features:** pH, Hardness, Solids, Chloramines, Sulfate, Conductivity, Organic Carbon, Trihalomethanes, Turbidity
**Target:** Potability (1 = Safe, 0 = Unsafe)
