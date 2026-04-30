# Ride-Demand-Forecasting-Data-Prep-Engine

#  Ride Demand Forecasting – Data Prep Engine

##  Project Overview

This project focuses on building a complete **data preprocessing and feature engineering pipeline** for ride-hailing data (similar to Ola/Uber use cases).

The goal is to transform raw datasets into a **clean, structured, and model-ready dataset** for downstream analytics such as:

* Ride demand forecasting
* Surge pricing prediction
* Customer behavior analysis

---

##  Objective

To preprocess and engineer features from multiple real-world datasets including:

* Rider demographics
* Trip booking logs
* City zone attributes

---

##  Datasets Used

| Dataset          | Format | Description                                       |
| ---------------- | ------ | ------------------------------------------------- |
| `riders.csv`     | CSV    | Rider demographic & account details               |
| `trips.json`     | JSON   | Trip booking & ride completion logs               |
| `city_zones.sql` | SQL    | Zone-level attributes (traffic, population, etc.) |

---

##  Tech Stack

* **Python**
* **Pandas, NumPy**
* **Scikit-learn**
* **SQLite**
* **Matplotlib, Seaborn**

---

##  Project Workflow

### 1️ Data Loading

* Loaded CSV, JSON, and SQL datasets
* Converted SQL script into SQLite database

### 2️ Data Cleaning

* Handled missing values:

  * Numeric → Mean Imputation
  * Categorical → Most Frequent
  * Multivariate → KNN Imputer
* Removed:

  * Negative fares
  * Zero-distance rides
* Standardized datetime formats

---

### 3️ Outlier Handling

* Z-score method (fare, distance)
* IQR method (trip duration)
* Winsorization for extreme values

---

### 4️ Data Transformation

* Extracted:

  * Hour
  * Day of week
  * Month
* Encoding:

  * Label Encoding → Gender
  * One-Hot Encoding → Payment mode, zone
  * Ordinal Encoding → Traffic level
* Skewness treatment:

  * Log transformation (fare, distance)
  * Square-root transformation (duration)

---

### 5️ Feature Scaling

* StandardScaler applied on numerical features
* Compared before vs after statistics

---

### 6️ Feature Engineering

Created new ML-ready features:

* `avg_ride_distance`
* `avg_ride_fare`
* `is_peak_hour`
* `ride_cancellation_rate`
* `surge_flag`

---

### 7️ Data Merging

* Combined:

  * Trips + Riders
  * Trips + City Zones

---

### 8️ Final Output

* Cleaned & enriched dataset exported as:

```
final_prepared_rides_dataset.csv
```

---

##  Bonus (EDA)

* Ride demand by hour visualization
* Surge vs Non-surge analysis

---

##  Project Structure

```
├── main.ipynb
├── riders.csv
├── trips.json
├── city_zones.sql
├── city_zones.db
├── final_prepared_rides_dataset.csv
└── README.md
```

---

##  How to Run

1. Clone the repository
2. Install dependencies:

```
pip install pandas numpy scikit-learn matplotlib seaborn
```

3. Open `main.ipynb`
4. Run all cells step-by-step

---

##  Deliverables

* ✔ Python Notebook (`main.ipynb`)
* ✔ Final Dataset (`.csv`)
* ✔ README File
* ✔ Summary Report

---

##  Key Learnings

* Real-world data preprocessing pipeline
* Handling missing & inconsistent data
* Feature engineering for ML models
* Working with multi-format datasets (CSV, JSON, SQL)


This project is created for academic purposes as part of a **Data Engineering / Data Science practical exam**.
