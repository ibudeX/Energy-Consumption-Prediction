# ⚡ Energy Consumption Prediction Using Supervised Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)  ![Libraries](https://img.shields.io/badge/Libraries-pandas%20|%20scikit--learn%20|%20matplotlib%20|%20xgboost%20|%20seaborn-yellowgreen)  ![Status](https://img.shields.io/badge/Status-Completed-brightgreen)  ![ML Task](https://img.shields.io/badge/Type-Regression-orange)

## 📌 Objective
This project predicts **energy consumption** in smart buildings using **supervised machine learning** techniques.  
By analyzing factors like **temperature, humidity, HVAC usage, lighting usage, and occupancy**, the goal is to provide actionable insights for **energy efficiency** and **smart building automation**.

---

## 📂 Step 1: Data Collection & Loading
- **Source:** Dataset from Kaggle via `kagglehub`
- **Shape:** 10 columns, 24,000+ records
- **Observation:**  
  - `Holiday`, `HVACUsage`, and `LightingUsage` are categorical  
  - Time data available in `Timestamp`

---

## 🛠 Step 2: Data Preprocessing
- Converted `Timestamp` → datetime
- Mapped categorical variables:  
  - `Holiday`, `HVACUsage`, `LightingUsage` → 0/1  
  - `DayOfWeek` → 0–6 (Monday–Sunday)
- Removed `Timestamp` column for modeling
- Standardized features using `StandardScaler`

---

## 📊 Step 3: Exploratory Data Analysis (EDA)
- **Histograms**: Temperature, Humidity, Occupancy, HVAC Usage
- **Correlation Heatmap**:  
  - Energy consumption strongly correlated with `HVACUsage` & `Occupancy`
  - Mild correlation with `Temperature` & `Humidity`

| Distribution of Energy Consumption | Correlation Heatmap |
|------------------------------------|---------------------|
| ![Histogram](https://github.com/user-attachments/assets/e0ddde10-e29b-4467-8d6e-09525cf80c99) | ![Heatmap](https://github.com/user-attachments/assets/72d0e279-8890-4943-8fb0-dc91fa41faac) |


---

## 🧠 Step 4: Feature Engineering
- **Target variable**: `EnergyConsumption`
- **Feature set**: All other variables after encoding
- Applied scaling for better model performance

---

## 🤖 Step 5: Model Building & Training
- **Train/Test Split**: 67% / 33%
- Models used:
  1. **Linear Regression**
  2. **Random Forest Regressor**
  3. **XGBoost Regressor**

---

## 📈 Model Evaluation

| Model                  | R² Score | MAE      | MSE      | Notes |
|------------------------|----------|----------|----------|-------|
| Linear Regression      | ~0.45    | Moderate | Moderate | Good interpretability, weaker on non-linear trends |
| Random Forest Regressor| ~0.84    | Low      | Low      | Handles non-linearity, robust to noise |
| XGBoost Regressor      | ~0.87    | Lowest   | Lowest   | Best accuracy, excellent generalization |

---

## 🔍 Insights & Discoveries
1. **Feature Importance**  
   - HVAC Usage & Occupancy → top predictors  
   - Temperature & DayOfWeek → secondary factors
2. **Best Algorithm**  
   - **XGBoost** was most effective

---

## 📌 Recommendations
**For Energy Managers:**
- Use predictions to optimize **HVAC & lighting schedules**
- Monitor **occupancy patterns** for demand forecasting

**For Smart Building Systems:**
- Automate device control based on predicted energy peaks
- Integrate **XGBoost model** into building management systems
