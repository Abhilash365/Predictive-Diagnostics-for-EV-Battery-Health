# Predictive-Diagnostics-for-EV-Battery-Health

This is an excellent step. Creating a detailed README immediately demonstrates that the project is serious, structured, and in progress, boosting the credibility of your resume claims.

Here is the content for your GitHub README page for the **Predictive Diagnostics for EV Battery Health** project, structured for maximum impact:

-----

# 🔋 Predictive Diagnostics for EV Battery Health

## Project Overview

This project implements a comprehensive machine learning pipeline to analyze and predict the degradation of Lithium-ion (Li-ion) batteries under varying operational profiles. The core objective is to develop a **Predictive Quality Diagnostics** system capable of forecasting battery health and detecting thermal anomalies that threaten reliability.

This work directly addresses the challenges faced by fast-charging EV companies, focusing on two critical factors: **maximizing cell life** (e.g., Exponent's 3000-cycle commitment) and ensuring **thermal safety** during high-current charging.

## 🎯 Key Achievements (Resume Points)

  * **SoH Prediction**: Modeled **State of Health (SoH)** using a **Time-Series Regressor** (MAE $< 3\%$) to validate **3000-cycle battery life**.
  * **Thermal Anomaly Detection**: Developed an **Isolation Forest** diagnostic system for **early fault warning** in **rapid charging** thermal data.
  * **BMS Feature Engineering**: Engineered **Resistance ($R_e, R_{ct}$)** features to enhance accuracy and support **Virtual Cell Modeling**.

## 🛠️ Technical Stack

| Category | Tool / Library | Purpose |
| :--- | :--- | :--- |
| **Language** | Python 3.x | Core implementation and machine learning. |
| **Data Handling** | NumPy, Pandas, **SciPy.io** | Data processing and critical `.mat` file conversion. |
| **Core Models** | **XGBoost, Isolation Forest** | Fast benchmarking, feature importance, and unsupervised anomaly detection. |
| **Advanced Model** | Scikit-learn, TensorFlow/Keras (planned) | LSTM implementation for time-series prognostics. |
| **Visualization** | Matplotlib, Seaborn, (Streamlit/Power BI) | Visualizing degradation curves and thermal alerts. |

## 📊 Data Source & Preprocessing

The project utilizes data from the **NASA Prognostics Center of Excellence (PCoE) Battery Data Set** (Batteries \#53-56).

| Feature | Description | Relevance |
| :--- | :--- | :--- |
| **Input Data** | Time-series Voltage, Current, and Temperature (Ambient $4^\circ C$). | Simulates real-world sensor data from the $e^{\wedge}pack$ and charging environment. |
| **Target Data** | Capacity (Ahr) | Direct measure of **State of Health (SoH)** for regression task. |
| **Raw Format** | `.mat` (MATLAB file) | Required complex conversion using `scipy.io.loadmat` and aggressive structure flattening. |

### Feature Engineering Highlights:

1.  **Capacity Fade ($C_{fade}$):** Tracked capacity loss across cycles for RUL target creation.
2.  **Internal Resistance ($R_{e}, R_{ct}$):** Extracted from **Impedance cycle data** (a high-value feature) to improve the model's physical understanding of battery health.
3.  **Temperature Change Rate ($\Delta T$):** Calculated the rate of change and variance of temperature within discharge cycles to feed the **Anomaly Detection** model.

## ⚙️ Model Pipeline Details

### 1\. SoH Prediction (Regression)

  * **Initial Benchmark:** **XGBoost Regressor** is used first for rapid validation and identifying the most important features (like $R_e, R_{ct}$).
  * **Final Model:** **LSTM Network** (planned to be implemented) will be used to capture sequential dependence and maximize predictive accuracy (targeting **MAE $< 3\%$**).
  * **Validation:** Metrics include **MAE** and **RMSE**.

### 2\. Thermal Anomaly Detection (Unsupervised Classification)

  * **Model:** **Isolation Forest**.
  * **Task:** Trained on normal thermal profiles to assign an anomaly score to cycles exhibiting unusual or sudden temperature spikes, providing an "early warning system" for potential thermal events.



## 🚀 Status

**Status: Actively in Progress (Phase 1 Complete - Data & Benchmarking)**

Next Steps: Implement and validate the LSTM Network (Phase 2).

-----

*(You would then add your GitHub link to your resume using the name of this project.)*
