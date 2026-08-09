# ⚡ Electric Power Consumption Forecasting

A **Time Series Forecasting project** that predicts future household electricity consumption using historical energy usage data.

The project analyzes over **2 million minute-level records** and compares traditional statistical models (**ARIMA, SARIMA**) with Deep Learning models (**RNN, LSTM, Bi-LSTM**).

---

## 📌 Project Overview

The main objective is to forecast **Global Active Power** for efficient energy management and demand planning.

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

## 📂 Dataset

The project uses the **Individual Household Electric Power Consumption** dataset from the UCI Machine Learning Repository.

**Dataset:** [Individual Household Electric Power Consumption – UCI](https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption)

* **Input File:** `ElectricityC.zip`
* **Size:** Approximately 2 million rows
* **Resolution:** Minute-level

### Key Features

* `Global_active_power` – Global minute-averaged active power
* `Global_reactive_power` – Global reactive power
* `Voltage` – Minute-averaged voltage
* `Sub_metering_1/2/3` – Energy sub-metering values

---

## 🛠️ Technologies Used

* **Python 3.x**
* **Pandas, NumPy** – Data manipulation
* **Matplotlib, Seaborn** – Data visualization
* **Statsmodels** – ARIMA, SARIMA, ADF Test, Seasonal Decomposition
* **TensorFlow, Keras** – RNN, LSTM, Bi-LSTM
* **Scikit-Learn** – Evaluation metrics

---

## ⚙️ Project Workflow

### 1. Data Preprocessing

* Converted `Global_active_power` to numeric format
* Handled special characters such as `?`
* Identified and removed approximately **1.25% missing data**
* Resampled the data to reduce noise and computational requirements
* Used **weekly data** for statistical models
* Used **hourly data** for Deep Learning models

### 2. Exploratory Data Analysis

The analysis included:

* Seasonal decomposition
* Trend and seasonality analysis
* Augmented Dickey-Fuller (ADF) test
* ACF and PACF analysis

A clear **yearly seasonal pattern** was identified in electricity consumption.

---

## 🤖 Model Building

### Statistical Models

**ARIMA** was used as the baseline forecasting model.

**SARIMA** was implemented to capture the yearly seasonal pattern.

**Key Finding:** SARIMA outperformed ARIMA by effectively handling seasonality.

### Deep Learning Models

The project implemented:

* Simple RNN
* LSTM
* Bi-LSTM

LSTM was used to capture long-term dependencies, while Bi-LSTM was tested for bidirectional sequence processing.

---

## 📊 Results & Evaluation

The models were evaluated using:

* **MAPE (Mean Absolute Percentage Error)**
* **RMSE (Root Mean Squared Error)**

| Model Category    | Best Model  | Key Observation                                        |
| ----------------- | ----------- | ------------------------------------------------------ |
| **Statistical**   | **SARIMA**  | Outperformed ARIMA by capturing yearly seasonality     |
| **Deep Learning** | **Bi-LSTM** | Best overall accuracy and captured non-linear patterns |

Residual analysis was also performed on the final models to examine the behavior of prediction errors.

---

## 🔍 Key Findings

* Electricity consumption shows strong seasonal patterns.
* SARIMA performed better than ARIMA due to its ability to model seasonality.
* Deep Learning models captured complex temporal patterns.
* LSTM effectively captured long-term dependencies.
* Bi-LSTM achieved the best overall accuracy among the tested Deep Learning models.
* Model performance was compared using MAPE and RMSE.

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
* ACF and PACF Analysis
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

---

## ⭐ Conclusion

This project demonstrates the application of **Time Series Forecasting and Deep Learning** to household electricity consumption.

By comparing **ARIMA, SARIMA, RNN, LSTM, and Bi-LSTM**, the project evaluates both traditional statistical and modern Deep Learning approaches for forecasting energy consumption.

The results highlight the importance of **seasonality in statistical forecasting** and the ability of recurrent neural networks to capture complex temporal patterns.
