# 🌬️ Wind Turbine SCADA Performance Analysis (T1)

## 📌 Project Overview
This project focuses on analyzing and modeling wind turbine performance using SCADA (Supervisory Control and Data Acquisition) data. The goal is to understand turbine behavior, predict power generation, detect anomalies, and build an AI-based performance scoring system.

---

## 📊 Dataset Description

The dataset contains time-series data recorded at regular intervals with the following features:

- **Date/Time** → Timestamp of observation  
- **LV ActivePower (kW)** → Actual power generated (Target variable)  
- **Wind Speed (m/s)** → Speed of wind  
- **Theoretical_Power_Curve (kWh)** → Expected power output  
- **Wind Direction (°)** → Direction of wind (0–360°)  

---

# 🔍 Task 1 — Exploratory Data Analysis (EDA)

## 1. Time-Series Trend Analysis
- Converted `Date/Time` into datetime format and set it as index.
- Plotted time-series graphs for:
  - Wind Speed  
  - Active Power  
  - Theoretical Power  
  - Wind Direction  

### 📈 Observations:
- Wind speed and power show correlated trends.
- Theoretical power curve is smoother compared to actual power.
- Some abnormal readings observed:
  - Negative power values  
  - Sudden spikes/drops (possible sensor errors)

---

## 2. Scatter Plot (Wind Speed vs Active Power)

- Visualized relationship between wind speed and power.

### ⚡ Key Insights:
- Non-linear relationship observed.
- Three regions:
  - Low wind → No power  
  - Medium wind → Rapid increase  
  - High wind → Saturation (max capacity)  

👉 Confirms turbine power curve behavior.

---

# 🤖 Task 2 — Supervised Learning (Time-Series Forecasting)

## 1. Time-Series Conversion & Windowing

- Sorted data by time and set index.
- Created **lag features** (windowed data) to capture temporal dependencies.
- Converted wind direction into:
  - sin(direction)
  - cos(direction)

---

## 2. Model Building

- Used **Random Forest Regressor** for multi-output forecasting.
- Predicted:
  - LV ActivePower  
  - Wind Speed  
  - Theoretical Power Curve  
  - Wind Direction (via transformed features)

---

## 3. Model Evaluation

- Used metrics:
  - MAE (Mean Absolute Error)
  - RMSE (Root Mean Squared Error)

### 📊 Results:
- Model captured trends effectively.
- Good performance due to non-linear learning capability.

---

## 4. Predicted vs Actual Plot

- Compared predicted values with actual values.
- Observed close alignment, validating model performance.

---

# 🚨 Task 3 — Unsupervised Learning (Anomaly Detection)

## 🎯 Objective:
Detect abnormal turbine behavior where:
> Actual Power ≠ Theoretical Power

---
## Approach:

### 1. Deviation Calculation



Deviation = Actual Power - Theoretical Power



### 2. Methods Used:
- Threshold-based detection
- Isolation Forest (advanced)

---

## 📈 Observations:
- Normal points follow smooth power curve.
- Anomalies detected:
  - Below curve → underperformance  
  - Above curve → possible sensor errors  

---

## 💡 Conclusion:
Anomaly detection helps in:
- Fault detection  
- Predictive maintenance  
- Efficiency monitoring  

---

# 🤖 Task 4 — AI Turbine Performance Score Generator

## 1. Performance Score Calculation



---

## 2. Score Scaling
- Values scaled between **0–100**
- Clipping applied to avoid invalid values

---

## 3. Classification

| Score Range | Category |
|------------|---------|
| ≥ 80 | Good |
| 50–80 | Moderate |
| < 50 | Poor |

---

## 4. Automated Suggestions

| Category | Suggestion |
|---------|-----------|
| Good | Turbine operating efficiently |
| Moderate | Check performance |
| Poor | Maintenance required |

---

## 💡 Insight:
This acts as a **simple AI-based decision system** for real-time monitoring.

---

# 🧠 Key Learnings

- Time-series data handling and feature engineering  
- Non-linear relationship modeling  
- Multi-output regression  
- Anomaly detection techniques  
- Real-world AI application in energy systems  

---

# 🚀 Applications

- Smart grid systems  
- Renewable energy optimization  
- Predictive maintenance  
- Industrial monitoring dashboards  

---

# 🛠️ Tech Stack

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  

---

# 📌 Conclusion

This project demonstrates how data-driven techniques can be used to:
- Predict power generation  
- Detect anomalies  
- Evaluate turbine performance  

It provides a strong foundation for applying AI in renewable energy systems.

---

# 👨‍💻 Author
**Aaditya Jha**  
Final Year AIML Student  
KPR Institute of Engineering and Technology (KPRIET)
