# 🔥 Calories Burnt Prediction

A Machine Learning regression project predicting calories burnt during exercise using XGBoost — achieving **1.22 calorie MAE** and **99.92% R²** on test data.

---

## 📌 Project Overview

This project predicts how many calories a person burns during an exercise session based on physiological and workout features. Two separate datasets (exercise data and calorie records) are merged and fed into a regularized XGBoost model.

**Best performing model in the portfolio** — predictions accurate to within 1.22 calories on average on completely unseen data.

---

## 📊 Dataset

**Files:** `exercise.csv` + `calories.csv` (merged on User_ID)

| Property | Value |
|---|---|
| Total Records | 15,000 |
| Missing Values | None |
| Features | 7 (after dropping User_ID) |
| Train / Test Split | 80% / 20% |

### Features

| Feature | Description |
|---|---|
| Gender | male / female (Label encoded: male=1, female=0) |
| Age | Age in years |
| Height | Height in centimeters |
| Weight | Weight in kilograms |
| Duration | Exercise duration in minutes |
| Heart_Rate | Average heart rate during exercise (bpm) |
| Body_Temp | Body temperature during exercise (°C) |

**Target:** Calories burnt during exercise session

---

## 📈 Results

| Metric | Training | Test |
|---|---|---|
| Mean Absolute Error | 0.9566 calories | 1.2242 calories |
| R² Score | 0.9996 | 0.9992 |

The model explains **99.92% of variance** in calorie burn on unseen data. Negligible gap between training and test metrics — no meaningful overfitting.

---

## 🔍 Key Findings from Correlation Analysis

Features most strongly correlated with calories burnt:
- **Duration** — strongest predictor
- **Heart_Rate** — strong positive correlation
- **Body_Temp** — strong positive correlation
- **Weight** — moderate positive correlation
- **Height** — minimal direct correlation

---

## 🛠️ Tech Stack

- Python 3.x
- NumPy
- Pandas
- Seaborn / Matplotlib
- Scikit-learn (train_test_split, MAE, R²)
- XGBoost (XGBRegressor)

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/AliSufyaan/calories-burnt-prediction.git
   cd calories-burnt-prediction
   ```

2. **Install dependencies**
   ```bash
   pip install numpy pandas seaborn matplotlib scikit-learn xgboost jupyter
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook Calories_Burnt_Prediction.ipynb
   ```

---

## 📁 Project Structure

```
calories-burnt-prediction/
├── Calories_Burnt_Prediction.ipynb    # Main notebook
├── exercise.csv                       # Exercise physiological data
├── calories.csv                       # Calorie records per user
└── README.md                          # You are here
```

---

## ⚠️ Limitations

- Dataset appears synthetic/controlled — real-world calorie prediction would have more noise
- No cross-validation applied — single train-test split
- Feature importance visualization not included

---

## 🧠 What I Learned

- Merging two datasets using `pd.concat()` on a shared index
- Why XGBoost does not require feature scaling — tree-based models are scale-invariant
- Importance of consistent encoding between training and prediction system — gender mapping must be identical in both places
- Using both MAE and R² together for a complete regression evaluation picture
- `astype(float)` is essential when prediction input comes from string splitting

---

## 📚 Reference

- Dataset: [Kaggle Calories Burnt Prediction](https://www.kaggle.com/datasets/fmendes/fmendesdat263xdemos)
