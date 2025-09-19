# Wine Quality Analysis (Red & White)

Exploratory Data Analysis (EDA) and basic machine learning on the **Wine Quality Dataset**.  
The goal is to identify which chemical features most strongly influence wine quality and to test simple predictive models.

---

## 🔍 Research Questions

- Which features show the strongest correlation with wine quality?  
- How do red and white wines differ in their chemical profiles?  
- Can a simple ML model predict quality with reasonable accuracy?  

---

## 📦 Dataset

- **Source:** UCI / Kaggle Wine Quality dataset  
- **Samples:** Red = 1,599 | White = 4,898  
- **Target variable:** `quality` (0–10)  
- **Features:** `fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol`

---

## 🗂 Project Structure

```plaintext
wine-quality-analysis/
├─ data/
│  ├─ raw/            # original csv files
│  └─ processed/      # cleaned/combined versions
├─ notebooks/
│  ├─ 01_eda.ipynb    # exploratory analysis + plots
│  ├─ 02_model.ipynb  # optional ML models
│  └─ 03_viz.ipynb    # additional visualizations
├─ src/
│  ├─ utils.py        # helper functions
│  └─ features.py     # preprocessing & feature engineering
├─ reports/
│  ├─ figures/        # exported plots
│  └─ tables/         # summary tables
├─ requirements.txt
└─ README.md
```
---

## ⚙️ Quick Start

```plaintext
# create environment
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt

# place raw data in data/raw/:
# winequality-red.csv, winequality-white.csv

# run notebooks
jupyter lab
```
---

## 🧽 Data Preparation

- Checked missing values and outliers
- Standardized or merged red/white datasets
- Target: quality (continuous) or binned into classes for classification

```plaintext
# example: binning quality scores
df['quality_bin'] = pd.cut(df['quality'],
                           bins=[-1,5,6,10],
                           labels=['low','mid','high'])
```
---

## 📊 Key EDA Findings

- alcohol shows the strongest positive correlation with quality (r ≈ 0.44).
- volatile acidity is strongly negatively correlated (r ≈ –0.39).
- sulphates and citric acid contribute positively but with weaker effects.
- Red wines: higher volatile acidity, lower residual sugar.
- White wines: higher residual sugar, lower volatile acidity.

---

## 🤖 Basic Modeling

- **Regression:** Linear Regression, RandomForestRegressor
- **Classification:** RandomForestClassifier on binned classes

 Sample results:
- Linear Regression → RMSE = 0.78, R² = 0.32
- RandomForest Classifier → Accuracy = 0.68, F1 (macro) = 0.64
**Top features:** alcohol, volatile acidity, sulphates, citric acid

---

## 🧪 Reproducibility

- requirements.txt provided
- Random seeds fixed (random_state=42)
- Notebooks can be run end-to-end with consistent results

---

## 🚀 What I Learned

-How to clean, analyze, and visualize tabular datasets with Pandas/Seaborn
-How chemical properties correlate with wine quality
-How to build and evaluate simple ML models on classification/regression tasks

---

## 📈 Next Steps

- Feature engineering (interaction terms, nonlinear transformations)
- Handle class imbalance (SMOTE, class weights)
- Hyperparameter tuning for ML models
- Model interpretability (SHAP, permutation importance)

---

## 📎 License

- Code: MIT License
- Data: Original dataset license (UCI/Kaggle)
