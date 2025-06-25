# 🌦️ Weather Data Analysis Project
![Image](https://github.com/user-attachments/assets/c6afd099-e928-4079-9970-89ed7eb77397)
## 📖 Project Overview

This project conducts an **exploratory data analysis (EDA)** on a weather dataset to uncover patterns, relationships, and key statistics about various meteorological conditions. The analysis is performed using **Python** with libraries such as **Pandas**, **Seaborn**, and **Matplotlib** to answer specific questions and visualize trends in the data.

---

## 📚 Table of Contents

- [💾 Dataset](#-dataset)
- [⚙️ Setup and Installation](#️-setup-and-installation)
- [🚀 How to Use](#-how-to-use)
- [📊 Data Exploration Summary](#-data-exploration-summary)
- [📈 Key Analysis and Findings](#-key-analysis-and-findings)
  - [1. Temperature Analysis](#1-temperature-analysis)
  - [2. Weather Condition Frequency](#2-weather-condition-frequency)
  - [3. Wind Speed and Visibility Correlation](#3-wind-speed-and-visibility-correlation)
  - [4. Pressure vs. Temperature Relationship](#4-pressure-vs-temperature-relationship)
  - [5. Dew Point Analysis](#5-dew-point-analysis)
  - [6. Seasonal Variations](#6-seasonal-variations)
  - [7. Extreme Weather Events](#7-extreme-weather-events)

---

## 💾 Dataset

The dataset used is `weather_dataset.csv`, which contains **hourly weather records** for a full year for a specific location.

| Column              | Description                                 | Data Type  |
|---------------------|---------------------------------------------|------------|
| Date/Time           | The date and hour of the observation        | datetime64 |
| Temp_C              | Temperature in degrees Celsius              | float64    |
| Dew Point Temp_C    | Dew point temperature in degrees Celsius    | float64    |
| Rel Hum_%           | Relative humidity (%)                       | int64      |
| Wind Speed_km/h     | Wind speed in kilometers per hour           | int64      |
| Visibility_km       | Visibility in kilometers                    | float64    |
| Press_kPa           | Atmospheric pressure in kilopascals         | float64    |
| Weather             | Weather description (text)                  | object     |

---

## ⚙️ Setup and Installation

To run this project, make sure you have Python 3 installed. Then install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly
```

## 🚀 How to Use

1. Clone this repository:
```bash
git clone https://github.com/your-username/weather-data-analysis.git
```
2. Ensure the `weather_dataset.csv` file is in the project directory.

3. Open Weather Analysis.ipynb using Jupyter Notebook or JupyterLab.

4. Run the cells in order to perform the analysis.

## 📊 Data Exploration Summary

- **Shape:** 8,784 rows × 8 columns (hourly data for 1 year).
- **Data Types:** All columns are correctly typed; `Date/Time` was converted to `datetime`.
- **Missing Values:** None — the dataset is clean.
- **Unique Weather Conditions:** 50 distinct descriptions like *Clear*, *Cloudy*, *Freezing Drizzle, Fog*, etc.

---

## 📈 Key Analysis and Findings

### 1. 🌡️ Temperature Analysis

- **Warmest Time:** 3 PM (15:00)
- **Coolest Time:** 5 AM
- **Seasonal Pattern:** 
  - **Hottest:** Summer (June–August)
  - **Coldest:** Winter (December–February)

---

### 2. 🌤️ Weather Condition Frequency

**Most Common Conditions:**

- Mainly Clear: **24.0%**
- Mostly Cloudy: **23.6%**
- Cloudy: **19.7%**
- Clear: **15.1%**

**Precipitation Insights:**

- **Snow:** 4.4% (More frequent)
- **Rain:** 3.5%

---

### 3. 🌬️ Wind Speed and Visibility Correlation

- **Correlation Coefficient:** 0.00
- **Conclusion:** No linear relationship between wind speed and visibility.

---

### 4. ⬇️ Pressure vs Temperature Relationship

- **Trend:** Weak **negative correlation**
- **Interpretation:** As atmospheric pressure increases, temperature slightly decreases. However, the relationship is not strong enough for prediction.

---

### 5. 💧 Dew Point Analysis

- **Humidity Indicator:** When **Temperature - Dew Point ≤ 2°C**, fog is likely.
- **Findings:** 
  - **1,222 instances** favorable for fog.
  - Primarily occurs in **Fall and Winter**.

---

### 6. 🌡️ Seasonal Variations

- **Temperature:** Warmest in **Summer**, coldest in **Winter**.
- **Humidity:** Highest in **Fall & Winter**.
- **Wind Speed:** Strongest during **Winter**.

---

### 7. 🌪️ Extreme Weather Events

- **High Wind (>30 km/h):** ~440 instances
- **Low Visibility (<1 km):** ~35 instances

**Time-Based Patterns:**

| Event Type           | Peak Times        |
|----------------------|-------------------|
| High Wind Events     | 9 AM to 1 PM      |
| Low Visibility Events| 6 AM (Radiation Fog) |

---

## 🤖 Machine Learning Model — *Coming Soon*

> We are currently working on building a machine learning model to **predict weather conditions** and **temperature patterns** using this dataset.  
> Stay tuned for model implementation using **regression**, **classification**, and **time-series forecasting** techniques!

---

## 🖼️ Screenshots — ML Model & Flask Web App (In Progress)

### 🔧 Model Development Snapshot
![Image](https://github.com/user-attachments/assets/5df781cc-e8d9-48e3-872c-f9d7ac400c02)
![Image](https://github.com/user-attachments/assets/5df781cc-e8d9-48e3-872c-f9d7ac400c02)

![Image](https://github.com/user-attachments/assets/b347c2eb-14b5-4e73-8eb7-509a1a6aeafb)
![Image](https://github.com/user-attachments/assets/f677a3ef-bfb9-460c-90a7-1d52270150ab)

### 🌐 Flask App Interface Preview
![Image](https://github.com/user-attachments/assets/b38d188f-21f8-4f8d-9fed-a52fd1e364e0)




---
