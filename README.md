# Urban Heat Island Estimation System

An end-to-end Machine Learning pipeline for estimating **Urban Heat Island (UHI) intensity** using real satellite and weather data from 25 global cities.

---

# Features

- Automated weather + satellite data collection
- Dynamic UHI target generation using MODIS LST
- Feature engineering and outlier handling
- Multiple ML model training and evaluation
- Hyperparameter tuning with GroupKFold CV
- Interactive Streamlit dashboard
- Real-time UHI prediction and visualization

---

# Quick Start

## 1. Authenticate Google Earth Engine

```bash
earthengine authenticate
```

## 2. Install Dependencies

```bash
pip install -r requirements.txt
```

## 3. Run the Project

```bash
python main.py
```

---

# Project Structure

```text
Urban_Heat_Island/
│
├── main.py                # Main pipeline runner
├── config.py              # Configuration and API keys
├── logger.py              # Logging utility
├── data_collector.py      # Weather + satellite data collection
├── preprocessor.py        # Data cleaning and feature engineering
├── model_trainer.py       # ML model training and evaluation
├── dashboard.py           # Streamlit dashboard
├── requirements.txt
│
├── data/
│   ├── raw_data.csv
│   └── processed_data.csv
│
├── models/
│   ├── best_model.pkl
│   ├── scaler.pkl
│   ├── metrics.json
│   ├── feature_names.json
│   └── outlier_stats.json
│
├── cache/
├── logs/
└── .env
```

---

# Pipeline Overview

| Step | Description |
|---|---|
| Data Collection | Fetches weather and satellite data |
| Preprocessing | Cleans data and engineers features |
| Model Training | Trains and evaluates ML models |
| Dashboard | Launches interactive Streamlit app |

---

# Data Sources

| Source | Data |
|---|---|
| Open-Meteo | Temperature, humidity, pressure, wind speed, cloud cover |
| Google Earth Engine | NDVI and Land Surface Temperature |
| OpenWeatherMap | Backup weather API |

---

# UHI Formula

```text
UHI Intensity = max(0, Urban LST − Rural LST)
```

Where:
- **Urban LST** = Land Surface Temperature at city center
- **Rural LST** = Median temperature of surrounding rural regions

---

# Features Used

## Weather Features
- Temperature
- Humidity
- Wind Speed
- Pressure
- Cloud Cover

## Satellite Features
- NDVI
- Urban Fraction
- Vegetation Class

## Geographic Features
- Latitude / Longitude
- Distance from Equator

## Temporal Features
- Month
- Hour
- Day/Night indicators

## Engineered Features
- Heat Index
- Heat Retention
- Wind Cooling Effect
- Temperature Anomaly
- Temperature-Humidity Interaction

---

# Models Trained

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost
- LightGBM
- K-Nearest Neighbors

Hyperparameter tuning performed using:
- GridSearchCV
- GroupKFold Cross Validation

---

# Evaluation Metrics

| Metric | Purpose |
|---|---|
| RMSE | Prediction error magnitude |
| MAE | Mean absolute error |
| R² Score | Variance explained |
| CV-RMSE | Cross-validation stability |
| Skill Score | Improvement over baseline |

---

# Dashboard Features

## Overview
- KPI cards
- UHI distribution plots
- Global heatmap

## Data Explorer
- Raw and processed datasets
- Correlation heatmaps
- Seasonal trends

## Preprocessing
- Missing value analysis
- Outlier handling visualization
- Feature engineering analysis

## Models
- Model leaderboard
- Residual analysis
- Feature importance
- Predicted vs Actual comparison

## Heatmap
- Interactive city-wise UHI visualization

## Prediction
- Real-time UHI prediction
- Gauge charts
- Sensitivity analysis
- 3D response visualization

---

# Re-run Any Step

## Windows

```bash
del data\raw_data.csv
del data\processed_data.csv
del models\best_model.pkl
del models\metrics.json
```

## Clear Cache

```bash
del cache\cache_*.json
```

---

# Main Dependencies

| Package | Purpose |
|---|---|
| Streamlit | Dashboard framework |
| Plotly | Interactive visualizations |
| Scikit-learn | ML models and evaluation |
| XGBoost / LightGBM | Gradient boosting models |
| Pandas / NumPy | Data processing |
| Earth Engine API | Satellite data access |
| Requests | API calls |

---

# Tech Stack

- Python
- Streamlit
- Scikit-learn
- Plotly
- Google Earth Engine
- XGBoost
- LightGBM

---

# Author

Akshita Bhardwaj
