# ⚡ Electric Power Consumption Forecasting

A **Time Series Forecasting project** that predicts future household electricity consumption using historical energy usage data.

The project analyzes more than **2 million minute-level records** and compares statistical models such as **ARIMA and SARIMA** with Deep Learning models including **RNN, LSTM, and Bi-LSTM**.

---

## 📌 Project Overview

The goal is to forecast **Global Active Power** using historical electricity consumption data.

| Category                 | Details                                         |
| ------------------------ | ----------------------------------------------- |
| **Type**                 | Time Series Forecasting                         |
| **Domain**               | Energy / Power Consumption                      |
| **Dataset**              | Individual Household Electric Power Consumption |
| **Target**               | Global Active Power                             |
| **Statistical Models**   | ARIMA, SARIMA                                   |
| **Deep Learning Models** | RNN, LSTM, Bi-LSTM                              |
| **Evaluation**           | MAPE, RMSE                                      |

---

## 📊 Dataset

The project uses the **Individual Household Electric Power Consumption** dataset from the UCI Machine Learning Repository.

**Dataset:** [Individual Household Electric Power Consumption – UCI](https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption)

### Dataset Details

* **Input File:** `ElectricityC.zip`
* **Size:** Approximately 2 million records
* **Resolution:** Minute-level

### Key Features

* `Global_active_power` – Global minute-averaged active power
* `Global_reactive_power` – Global reactive power
* `Voltage` – Minute-averaged voltage
* `Sub_metering_1/2/3` – Energy sub-metering values

---

## 🛠️ Tech Stack

* **Python**
* **Pandas, NumPy** – Data processing
* **Matplotlib, Seaborn** – Visualization
* **Statsmodels** – ARIMA, SARIMA, ADF Test, Seasonal Decomposition
* **TensorFlow, Keras** – RNN, LSTM, Bi-LSTM
* **Scikit-Learn** – Model evaluation

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Converted `Global_active_power` to numeric format
* Handled missing and invalid values
* Removed approximately **1.25% missing observations**
* Resampled the data to reduce noise and computational requirements
* Used **weekly data** for statistical models
* Used **hourly data** for Deep Learning models

### 2. Exploratory Data Analysis

The analysis included:

* Seasonal decomposition
* Trend and seasonality analysis
* Augmented Dickey-Fuller (ADF) test
* ACF and PACF plots

The analysis identified a clear **yearly seasonal pattern** in electricity consumption.

---

## 🤖 Model Building

### Statistical Models

**ARIMA** was used as a baseline forecasting model.

**SARIMA** was implemented to capture the yearly seasonal pattern.

**Key Finding:** SARIMA performed better than ARIMA by incorporating seasonality.

### Deep Learning Models

The following recurrent neural network models were implemented:

* Simple RNN
* LSTM
* Bi-LSTM

LSTM was used to capture long-term dependencies, while Bi-LSTM was tested to determine whether bidirectional processing could improve forecasting performance.

---

## 📈 Model Comparison

| Category          | Models             |
| ----------------- | ------------------ |
| **Statistical**   | ARIMA, SARIMA      |
| **Deep Learning** | RNN, LSTM, Bi-LSTM |

Models were evaluated using **MAPE** and **RMSE**.

| Category          | Best Model  | Observation                                         |
| ----------------- | ----------- | --------------------------------------------------- |
| **Statistical**   | **SARIMA**  | Better than ARIMA due to seasonal modeling          |
| **Deep Learning** | **Bi-LSTM** | Strong performance in capturing non-linear patterns |

Residual analysis was also performed on the final models.

---

## 🚀 Key Features

* Household electricity consumption forecasting
* Analysis of 2+ million records
* Data cleaning and preprocessing
* Time series resampling
* Trend and seasonality analysis
* ADF stationarity testing
* ACF and PACF analysis
* ARIMA and SARIMA forecasting
* RNN, LSTM and Bi-LSTM forecasting
* MAPE and RMSE evaluation
* Residual analysis
* Statistical vs Deep Learning model comparison

---

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

* Time Series Analysis
* Data Cleaning
* Exploratory Data Analysis
* Stationarity Testing
* Seasonal Decomposition
* ARIMA and SARIMA
* Recurrent Neural Networks
* LSTM and Bi-LSTM
* Model Evaluation
* Statistical and Deep Learning Model Comparison

---

## 📁 Project Structure

```text
Electric-Power-Consumption-Forecasting/
│
├── Electric-Power-Consumption-Forecasting.ipynb
├── ElectricityC.zip
└── README.md
```

---

## 🔄 Forecasting Workflow

```text
Electricity Consumption Dataset
            ↓
       Data Cleaning
            ↓
      Data Resampling
            ↓
            EDA
            ↓
   Stationarity & Seasonality
            ↓
    ┌───────────────┐
    │               │
    ↓               ↓
 ARIMA/SARIMA    RNN/LSTM/Bi-LSTM
    │               │
    └───────┬───────┘
            ↓
      Model Evaluation
            ↓
        MAPE + RMSE
            ↓
      Model Comparison
```

