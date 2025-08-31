# AI-Powered Energy Consumption Forecasting with Anomaly Detection & Voice Assistant Integration for Smart Homes

## Project Overview

This project focuses on forecasting household energy consumption using AI/ML models while detecting unusual patterns such as faulty appliances, energy leakage, or theft. Additionally, it prepares outputs for **voice assistant integration**, allowing users to query energy predictions in real-time.

**Objectives:**

1. Predict hourly/daily energy consumption for smart homes.
2. Detect anomalies in energy usage.
3. Prepare outputs for future integration with voice assistants (Alexa/Google Assistant).
4. Enable automation using workflow tools like n8n in future phases.

---

## 1. Problem Definition

Energy forecasting helps households optimize electricity usage and reduce costs. Traditional forecasting methods often ignore anomaly detection or practical automation. This project aims to:

* Forecast energy usage accurately.
* Detect unusual consumption patterns.
* Integrate with voice assistants and automation platforms for real-time insights and actions.

---

## 2. Data Collection & Understanding

**Datasets Used:**

1. **Household Power Consumption (UCI)**

   * [Dataset Link](https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption)
   * Features: Global\_active\_power, Global\_reactive\_power, Voltage, Sub-meter readings.

2. **Optional Weather Data**

   * Sources: OpenWeatherMap API or NOAA
   * Features: Temperature, Humidity, Solar radiation

**Data Exploration:**

* Checked for missing values and handled them via forward fill.
* Visualized energy consumption trends and distributions.
* Identified patterns for anomaly detection and peak usage hours.

---

## 3. Data Preprocessing

**Steps:**

1. Convert relevant columns to numeric type.
2. Feature engineering: extract hour, day, weekday.
3. Scaling features using StandardScaler.
4. Prepare outputs for anomaly detection and voice assistant integration.

**Anomaly Detection:**

* Used **Isolation Forest** to detect unusual consumption patterns.
* Visualized anomalies in energy consumption time series.

---

## 4. Data Splitting

* Chronologically split dataset:

  * 70% Training
  * 15% Validation
  * 15% Testing
* Prepared training and testing sets for ML models.

---

## 5. Model Selection

* **Linear Regression:** Baseline model for simple linear relationships.
* **Random Forest Regressor:** Handles non-linear patterns and seasonal variations.

**Evaluation Metrics:**

* Mean Squared Error (MSE)
* R² Score

---

## 6. Voice Assistant Integration (Conceptual / Future Enhancement)

* ML model outputs prepared in JSON format to feed voice assistants:

```json
{
  "date": "2025-09-01",
  "predicted_energy_kWh": 12.5,
  "anomaly_detected": false
}
```

* Using n8n or similar workflow tools, users can query:

  * "How much energy will I consume tomorrow?"
  * "Is there any unusual energy usage detected?"
* Future integration can trigger smart devices or send alerts based on predictions.

---

## 7. Tools & Technologies

* Python, Jupyter Notebook
* Pandas, NumPy for data manipulation
* Matplotlib, Seaborn for visualization
* Scikit-learn for ML models and anomaly detection
* Joblib for saving trained models
* Future: n8n for workflow automation, Voice Assistants for user interaction

---

## 8. Conclusion & Future Scope

* **Week 1 Deliverable:** Data exploration, preprocessing, splitting, anomaly detection, and model training preparation.
* **Future Enhancements:**

  1. Real-time integration with smart home devices.
  2. Voice assistant responses and queries.
  3. Workflow automation using n8n.
  4. Multi-home energy optimization using advanced AI or quantum computing techniques.

---

**Repository Structure:**

```
AI-Energy-Forecasting/
├── README.md                 <-- This file
├── notebooks/
│    └── Week1_Energy_Forecasting.ipynb
├── data/
│    ├── household_power_consumption.csv
│    └── weather_data.csv
└── models/
     └── energy_forecasting_model.pkl
```

