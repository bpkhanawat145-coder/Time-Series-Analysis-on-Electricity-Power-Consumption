# ⚡ Electric Power Consumption Forecasting

## 📌 Project Overview

This project focuses on **Time Series Forecasting** to predict future household electric power consumption using historical energy usage data.

The project uses more than **2 million records** of household electricity consumption and compares traditional statistical forecasting models with modern Deep Learning models.

The main objective is to forecast **Global Active Power** and determine which model provides the most accurate predictions for effective **energy management and demand planning**.

---

## 📂 Dataset

* **Dataset:** Individual Household Electric Power Consumption
* **Source:** UCI Machine Learning Repository
* **Input File:** `ElectricityC.zip`
* **Records:** Approximately 2 million minute-level observations
* **Time Resolution:** 1 minute

### Important Features

| Feature                 | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| `Global_active_power`   | Household global minute-averaged active power (kilowatt) |
| `Global_reactive_power` | Household global minute-averaged reactive power          |
| `Voltage`               | Minute-averaged voltage                                  |
| `Sub_metering_1`        | Energy sub-metering No. 1                                |
| `Sub_metering_2`        | Energy sub-metering No. 2                                |
| `Sub_metering_3`        | Energy sub-metering No. 3                                |

---

## 🎯 Project Objectives

The main objectives of this project are:

* Analyze historical household electricity consumption.
* Clean and preprocess the time series data.
* Identify trends, seasonality, and patterns in electricity usage.
* Test whether the series is stationary.
* Build traditional statistical forecasting models.
* Build Deep Learning forecasting models.
* Compare the performance of all models using appropriate evaluation metrics.
* Select the best-performing model for electric power consumption forecasting.

---

## 🛠️ Technologies Used

### Programming Language

* Python 3.x

### Data Manipulation

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Statistical Modeling

* Statsmodels

  * ARIMA
  * SARIMA
  * Augmented Dickey-Fuller (ADF) Test
  * Seasonal Decomposition
  * ACF
  * PACF

### Deep Learning

* TensorFlow
* Keras

  * Simple RNN
  * LSTM
  * Bidirectional LSTM

### Model Evaluation

* Scikit-learn

  * MAPE
  * RMSE

---

# ⚙️ Project Workflow

## 1. Data Loading

The electricity consumption dataset is loaded using Pandas. The dataset contains minute-level measurements of household electricity usage collected over several years.

The main target variable used for forecasting is:

`Global_active_power`

---

## 2. Data Preprocessing & Cleaning

The raw dataset contains some non-numeric values represented by special characters such as `?`.

The `Global_active_power` column is converted into numeric format while invalid values are converted to missing values.

### Missing Values

Approximately **1.25% of the observations** contain missing values.

These missing observations are removed to obtain a clean time series for further analysis.

### Resampling

Since the original dataset contains more than 2 million minute-level observations, the data is resampled to reduce computational complexity.

* **Weekly data** → Used for statistical models such as ARIMA and SARIMA.
* **Hourly data** → Used for Deep Learning models such as RNN, LSTM, and Bi-LSTM.

This helps reduce noise and makes model training more efficient.

---

# 📊 3. Exploratory Data Analysis

Exploratory Data Analysis is performed to understand the behavior of electricity consumption over time.

### Time Series Visualization

The `Global_active_power` series is plotted to identify:

* Long-term trends
* Seasonal patterns
* Consumption fluctuations
* Unusual observations

### Seasonal Decomposition

The time series is decomposed into three major components:

* **Trend**
* **Seasonality**
* **Residual**

The decomposition helps identify a clear seasonal pattern in electricity consumption.

### Stationarity Test

The **Augmented Dickey-Fuller (ADF) Test** is used to check whether the time series is stationary.

The obtained **p-value is less than 0.05**, indicating that the null hypothesis can be rejected and the series is considered stationary for modeling.

### ACF and PACF

**Autocorrelation Function (ACF)** and **Partial Autocorrelation Function (PACF)** plots are analyzed to understand the relationship between current and previous observations.

These plots are also useful for selecting suitable parameters for ARIMA-based models.

---

# 🤖 4. Model Implementation

Two major approaches are used in this project.

## Phase A — Statistical Time Series Models

### ARIMA

**ARIMA (AutoRegressive Integrated Moving Average)** is implemented as the baseline statistical forecasting model.

It uses:

* Autoregression
* Differencing
* Moving averages

to model the relationship between past and future observations.

### SARIMA

**SARIMA (Seasonal ARIMA)** is then implemented to capture seasonal patterns in electricity consumption.

Unlike standard ARIMA, SARIMA incorporates additional seasonal parameters, allowing it to model repeating patterns more effectively.

### Key Observation

SARIMA performs better than standard ARIMA because it is able to capture the seasonal behavior present in the electricity consumption data.

---

# 🧠 Phase B — Deep Learning Models

## Simple RNN

A **Recurrent Neural Network (RNN)** is implemented as the basic Deep Learning forecasting model.

RNNs are designed for sequential data and use information from previous time steps to predict future values.

---

## LSTM

**Long Short-Term Memory (LSTM)** is used to improve upon the limitations of traditional RNNs.

LSTM networks contain specialized gates that allow them to retain important information for longer periods and reduce the vanishing gradient problem.

The LSTM model is trained using historical electricity consumption sequences to predict future power consumption.

---

## Bi-LSTM

A **Bidirectional LSTM (Bi-LSTM)** is also implemented.

Unlike a standard LSTM, Bi-LSTM processes the sequence in both directions:

* Forward direction
* Backward direction

The model is evaluated to determine whether bidirectional processing improves forecasting performance.

---

# 📏 5. Model Evaluation

The models are evaluated using two main metrics:

### Mean Absolute Percentage Error (MAPE)

MAPE measures the average percentage difference between the actual and predicted values.

Lower MAPE indicates better forecasting performance.

### Root Mean Squared Error (RMSE)

RMSE measures the square root of the average squared difference between actual and predicted values.

Lower RMSE indicates that the predictions are closer to the actual observations.

---

# 📊 6. Results

The models are compared based on their forecasting performance.

| Model Category | Model       | Key Observation                                     |
| -------------- | ----------- | --------------------------------------------------- |
| Statistical    | ARIMA       | Used as the baseline forecasting model              |
| Statistical    | **SARIMA**  | Improved performance by capturing seasonal patterns |
| Deep Learning  | RNN         | Basic recurrent model used for comparison           |
| Deep Learning  | LSTM        | Achieved strong forecasting performance             |
| Deep Learning  | **Bi-LSTM** | Best overall performance in the comparison          |

### 🏆 Best Model

Among the tested models, **Bi-LSTM achieved the best overall forecasting performance**, obtaining the lowest error compared with the other models.

The model was able to capture complex and non-linear patterns in household electricity consumption effectively.

---

# 🔍 7. Model Comparison

The project demonstrates the difference between traditional statistical forecasting and Deep Learning approaches.

* **ARIMA** provides a strong statistical baseline.
* **SARIMA** improves upon ARIMA by incorporating seasonality.
* **RNN** provides a basic Deep Learning approach for sequential data.
* **LSTM** handles long-term dependencies more effectively than a standard RNN.
* **Bi-LSTM** provides the best overall performance among the tested models.

---

# 📈 8. Key Findings

* Electricity consumption contains significant temporal patterns.
* Data preprocessing is important because the original dataset contains missing and non-numeric observations.
* Resampling significantly reduces the computational requirements of the project.
* Seasonal patterns have an important influence on electricity consumption.
* SARIMA performs better than standard ARIMA when seasonal behavior is considered.
* Deep Learning models are capable of learning complex non-linear relationships.
* **Bi-LSTM achieved the best overall forecasting performance** among the tested models.

---

# 🚀 9. Conclusion

This project demonstrates the application of both **traditional Time Series Forecasting** and **Deep Learning** techniques for predicting household electricity consumption.

The comparison shows that statistical models such as ARIMA and SARIMA can effectively model temporal and seasonal patterns, while Deep Learning models can capture more complex sequential relationships.

Among all the implemented models, **Bi-LSTM provided the best overall forecasting accuracy**, making it the most suitable model among those tested for predicting future electric power consumption.

The project can be further extended by incorporating additional variables such as voltage, reactive power, and sub-metering information to improve forecasting performance.

---

## 📁 Project Structure

```text
Electric-Power-Consumption-Forecasting/
│
├── data/
│   └── ElectricityC.zip
│
├── notebooks/
│   └── Electric_Power_Consumption_Forecasting.ipynb
│
├── images/
│   ├── consumption_trend.png
│   ├── decomposition.png
│   ├── acf_pacf.png
│   ├── arima_prediction.png
│   ├── sarima_prediction.png
│   ├── rnn_prediction.png
│   ├── lstm_prediction.png
│   └── bilstm_prediction.png
│
├── README.md
└── requirements.txt

