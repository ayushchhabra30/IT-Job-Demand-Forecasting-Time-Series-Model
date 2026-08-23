# 💻 IT Job Demand Forecasting Using Time Series Models

<p align="center">
  <b>Forecasting IT Hiring Trends using ARIMA, SARIMA & Box-Jenkins Methodology</b>
</p>

---

## 📌 Overview

IT Job Demand Forecasting is a time series analysis project that studies historical IT job posting data to identify hiring patterns and forecast future job demand.

The project applies classical time series models including **AR, MA, ARMA, ARIMA, and SARIMA**, following the **Box-Jenkins methodology** for systematic model identification, estimation, diagnostic verification, and forecasting.

The system focuses on identifying **weekly seasonality in IT hiring activity** and uses the final SARIMA model to generate short-term job demand forecasts with confidence intervals.

---

## ✨ Key Features

- 📅 Time-based analysis of IT job postings
- 📊 Historical demand visualization
- 📉 Stationarity testing using the ADF test
- 🔗 ACF and PACF analysis
- 🧮 AR, MA, ARMA and ARIMA modelling
- 🌐 Seasonal ARIMA (SARIMA) forecasting
- 📏 AIC-based model comparison
- 🔬 Residual and white-noise analysis
- 🧪 Ljung-Box diagnostic testing
- 🔮 Future demand forecasting with confidence intervals

---

## 📂 Dataset

The project uses the **LinkedIn Job Posts Insights Dataset**, containing job posting information such as:

| Feature | Description |
|---------|-------------|
| `job_title` | Title of the job |
| `location` | Job location |
| `company_name` | Hiring company |
| `date` | Job posting date |
| `hiring_status` | Current hiring status |
| `seniority_level` | Required seniority level |
| `job_function` | Functional area |
| `employment_type` | Type of employment |
| `industry` | Industry sector |

The dataset is filtered to focus on **IT-related job postings** and aggregated by posting date to construct the time series.

---

## 🧠 Methodology

The project follows the classical **Box-Jenkins forecasting framework**.

### 1️⃣ Identification

- Visualize the original time series
- Perform the **Augmented Dickey-Fuller (ADF) test**
- Apply differencing when required
- Analyze **ACF and PACF** plots
- Identify suitable AR and MA orders

### 2️⃣ Estimation

Candidate models are fitted and compared:

- **AR(p)** — Autoregressive model
- **MA(q)** — Moving Average model
- **ARMA(p,q)** — Combination of AR and MA
- **ARIMA(p,d,q)** — Handles non-stationary series
- **SARIMA(p,d,q)(P,D,Q,s)** — Handles seasonal patterns

### 3️⃣ Diagnostic Verification

The selected model is evaluated using:

- Residual time-series analysis
- Residual ACF
- **Ljung-Box test**
- White-noise verification

A suitable model should leave residuals that behave approximately like white noise.

### 4️⃣ Forecasting

The validated model is used to:

- Forecast future IT job demand
- Generate confidence intervals
- Analyze expected hiring trends

---

## 📈 Model Selection

The project compares non-seasonal and seasonal models using **Akaike Information Criterion (AIC)**.

The model with the lower AIC is preferred when comparing models with comparable objectives.

The final forecasting model is:

### `SARIMA(1,0,1)(1,1,1,7)`

Here, `7` represents the **weekly seasonal period**.

The seasonal component allows the model to capture recurring weekly variations in IT job posting activity.

---

## 📊 Analysis & Results

The analysis focuses on:

- 📈 Overall IT hiring trends
- 📅 Weekly seasonal patterns
- 🔍 Stationarity characteristics
- 📊 ACF and PACF behaviour
- ⚖️ ARIMA vs SARIMA performance
- 🧪 Residual behaviour
- 🔮 Future job demand

The model produces a forecast of future IT job postings along with **confidence intervals**, allowing uncertainty in the predictions to be visualized.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
|  Python | Core development |
|  Pandas | Data manipulation & preprocessing |
|  NumPy | Numerical computation |
|  Matplotlib | Data visualization |
|  Seaborn | Statistical visualization |
|  Statsmodels | ARIMA, SARIMA, ADF, ACF/PACF & diagnostics |
|  SciPy | Statistical analysis |
|  Jupyter Notebook | Development & experimentation |

---
## 📌 Project Workflow

```text
              📂 Raw Job Posting Data
                       │
                       ▼
              🔍 IT Job Filtering
                       │
                       ▼
              🧹 Data Preprocessing
                       │
                       ▼
             📊 Exploratory Analysis
                       │
                       ▼
             📉 Stationarity Testing
                    (ADF Test)
                       │
                       ▼
                ACF / PACF Analysis
                       │
                       ▼
          ┌──────────────────────────┐
          │   AR / MA / ARMA / ARIMA │
          └──────────────────────────┘
                       │
                       ▼
              🌐 SARIMA Modelling
                       │
                       ▼
                ⚖️ AIC Comparison
                       │
                       ▼
              🔬 Residual Analysis
                       │
                       ▼
              🧪 Ljung-Box Test
                       │
                       ▼
                 🔮 Forecasting
                       │
                       ▼
             📈 Future Job Demand
