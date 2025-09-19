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
