# Time Series Analysis and Forecasting with ARIMA

This project focuses on time series analysis and forecasting using the ARIMA (AutoRegressive Integrated Moving Average) model. The dataset includes hourly electricity **load** and **solar generation** for Italy in the year 2016.

---

## 📂 Dataset

- **Filename:** `TimeSeries_TotalSolarGen_and_Load_IT_2016.csv`
- **Columns:**
  - `utc_timestamp`: Timestamps in UTC
  - `IT_load_new`: Electricity load
  - `IT_solar_generation`: Solar power generation

---

## 📈 Workflow Overview

### 1. Data Loading & Preprocessing
- Loaded the dataset using `pandas`.
- Handled missing values using forward fill.
- Converted `utc_timestamp` to datetime format.

### 2. Data Visualization
- Plotted line graphs to visualize:
  - Overall trend in **load** and **solar generation**.
  - Seasonal and daily patterns.

### 3. Stationarity Check
- Used **Augmented Dickey-Fuller (ADF)** test to check for stationarity.
- Both time series were found to be stationary (`p-value < 0.05`).

### 4. Model Selection using ACF and PACF
- Used **ACF** and **PACF** plots to determine ARIMA parameters `(p, d, q)`.
  - Best-fit parameters found: `(2, 0, 2)`

---

## 🔍 Modeling and Evaluation

### Load Forecasting

- Split data: 80% training, 20% testing
- Trained ARIMA(2,0,2) model on `IT_load_new`
- RMSE ≈ **7715**
- Visualized predicted vs actual values

### Solar Generation Forecasting

- Trained ARIMA(2,0,2) model on `IT_solar_generation`
- RMSE ≈ **2486**
- Visualized predicted vs actual values

---

## 📊 Results

- **Both models capture the general pattern** in the data.
- Some differences between predicted and actual values due to:
  - Noise or randomness
  - Simplified assumptions of ARIMA

---

## 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn

---

## 📌 Future Improvements

- Explore **seasonal ARIMA (SARIMA)** models
- Incorporate **exogenous variables** (e.g., weather data)
- Try more advanced models like **LSTM** or **Prophet**

---

## 📁 File Structure

```bash
.
├── TimeSeries_TotalSolarGen_and_Load_IT_2016.csv
├── arima_forecasting.ipynb
└── README.md
