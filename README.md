# Combined-Cycle-Power-Plant-Energy-Prediction-Machine-Learning-Project-

## Author: Akinfela Babatunde Bernard — Data Analyst, BI Developer and Data Scientist / ML Engineer

## Project Overview

This project focuses on developing a Machine Learning model to accurately predict the **net hourly electrical energy output (EP)** of a **Combined Cycle Power Plant (CCPP)** operating under full load conditions.

As a **physicist and data analyst**, I explored how ambient environmental variables influence real‑world power generation efficiency — a critical problem in modern energy optimization and sustainability.

## Problem Statement

A CCPP consists of **Gas Turbines (GT), Steam Turbines (ST), and Heat Recovery Steam Generators (HRSG)**. Its output fluctuates significantly based on ambient conditions. The goal of this project is to build a model that can **reliably predict energy output (EP)** based on the following hourly environmental inputs:

* **Temperature (T)** — affects GT efficiency
* **Ambient Pressure (AP)** — influences combustion process
* **Exhaust Vacuum (V)** — impacts steam turbine performance
* **Relative Humidity (RH)** — indirectly affects combustion & cooling efficiency

The dataset contains **9,568 real operational data points (2006–2011)**.

## Business / Engineering Value

* **Optimizes real-time energy dispatching**
* **Improves operational cost planning**
* Enables **proactive energy forecasting for grid stability**
* Supports **efficiency-enhancing decisions for plant tuning & maintenance**

## Methodology

1. **Data Understanding & Cleaning**

   * Checked for missing values (none found)
   * Identified and **capped outliers** (<1% of data → winsorization for safety)

2. **Feature Engineering & Splitting**

   ```python
   x = df.drop('PE', axis=1).values
   y = df['PE'].values
   from sklearn.model_selection import train_test_split
   X_train, X_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)
   ```

3. **Model Training**

   * Applied **Linear Regression** (baseline model)

4. **Model Evaluation**

   * **R² Score:** 0.93 → model explains **93% variance** in energy output
   * **MAE:** ≈ 3.6 MW → average prediction error
   * **RMSE:** ≈ 4.5 MW → worst‑case deviation reasonable for industry use

## Key Results

 **Highly accurate model for real-world prediction**
 
**Errors within acceptable engineering tolerance (±5 MW)**
 
**Performance suitable for deployment in energy forecasting systems**

## Summary Insight

This project validates that **environmental ambient variables are strongly predictive of CCPP performance**, and a properly tuned Machine Learning model can enable **data‑driven operational planning** with high confidence.

---

## Deployment Strategy

This model can be deployed as a RESTful API using Flask or FastAPI, allowing real-time energy predictions based on live sensor inputs from the power plant. For practical demonstration, it can also be wrapped in a Streamlit or Dash web interface for interactive forecasting by engineers. Further scalability can be achieved by containerizing with Docker and hosting on AWS / Azure / Render.

## Future Improvements

Integrate XGBoost / LightGBM for higher predictive performance.

Deploy as a real-time monitoring system connected to plant SCADA infrastructure.

Add feature importance + SHAP interpretation for explainability.

Build an interactive dashboard for plant operators.

Extend model to handle time-series forecasting and predictive maintenance.
