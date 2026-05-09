# 🍔 Swiggy Food Orders – Data Analysis Project

A comprehensive dataset of Swiggy food delivery orders across India, covering **197,430 order records** from **28 cities** over an 8-month period (January–August 2025). This project is designed for exploratory data analysis, business intelligence, and dashboard reporting on food delivery trends.

---

## 📁 File Structure

```
Swiggy_Raw_Data_Excel.xlsx
│
├── Swiggy Data       → Raw order-level dataset (197,430 rows × 14 columns)
├── Analysis          → Pre-built KPI summary and pivot analysis
└── Dashboard         → Dashboard canvas (for visualization layer)
```

---

## 📊 Dataset Overview

| Attribute         | Details                              |
|-------------------|--------------------------------------|
| **Total Records** | 197,430 orders                       |
| **Cities**        | 28 cities across India               |
| **States**        | 28 states                            |
| **Restaurants**   | 993 unique restaurants               |
| **Unique Dishes** | 59,064 dishes                        |
| **Date Range**    | January 1, 2025 – August 31, 2025    |
| **Price Range**   | ₹0.95 – ₹8,000                       |
| **Avg Price**     | ₹268.51                              |
| **Avg Rating**    | 4.34 / 5.0                           |

---

## 🗂️ Column Reference

| Column           | Type     | Description                                         |
|------------------|----------|-----------------------------------------------------|
| `State`          | String   | Indian state where the order was placed             |
| `City`           | String   | City of the delivery                                |
| `Order Date`     | Date     | Date the order was placed (YYYY-MM-DD)              |
| `Day`            | String   | Day of the week (Monday–Sunday)                     |
| `Quarter`        | String   | Fiscal/calendar quarter (Q1–Q3)                     |
| `Week`           | Integer  | Week number of the year                             |
| `Restaurant Name`| String   | Name of the restaurant                              |
| `Location`       | String   | Locality/area of the restaurant                     |
| `Category`       | String   | Menu category of the dish (e.g., North Indian, Chinese) |
| `Dish Name`      | String   | Name of the ordered dish                            |
| `Food Type`      | String   | `Veg` or `Non-Veg`                                  |
| `Price (INR)`    | Float    | Price of the dish in Indian Rupees                  |
| `Rating`         | Float    | Restaurant rating (1.5 – 5.0)                       |
| `Rating Count`   | Integer  | Total number of user ratings for the restaurant     |

---

## 🌍 Geographic Coverage

**Top Cities by Order Volume:**

| City       | Orders |
|------------|--------|
| Bengaluru  | 20,077 |
| Mumbai     | 10,507 |
| Hyderabad  | 10,309 |
| Jaipur     | 10,286 |
| Lucknow    | 10,192 |

Covers all major metros and tier-2 cities including Delhi, Chennai, Kolkata, Ahmedabad, Chandigarh, and more.

---

## 🥗 Food Type Distribution

| Food Type  | Orders  | Share  |
|------------|---------|--------|
| Veg        | 140,582 | 71.2%  |
| Non-Veg    | 56,848  | 28.8%  |

---

## 📈 Key KPIs (from Analysis Sheet)

- **Total Revenue (Sum of Price):** ₹19,606,034.71
- **Average Rating:** 4.34
- Pre-calculated pivot tables for city-wise, category-wise, and time-based analysis are available in the **Analysis** sheet.

---

## 💡 Suggested Analysis Ideas

- **Sales Trends:** Track revenue and order volume by day, week, quarter
- **City Performance:** Compare top-performing cities and restaurants
- **Menu Insights:** Identify popular dish categories and cuisine types
- **Pricing Analysis:** Average price distribution by city or category
- **Rating Analysis:** Correlation between price, rating, and order volume
- **Veg vs Non-Veg:** Demand distribution across regions
- **Peak Days:** Identify busiest days of the week for orders

---

## 🛠️ Tools & Technologies

This dataset is compatible with:

- **Microsoft Excel / Google Sheets** – Pivot tables, charts, slicers
- **Power BI / Tableau** – Interactive dashboards
- **Python (pandas, matplotlib, seaborn, plotly)** – Data analysis & visualization
- **SQL** – Querying after import into a database

---

## 🚀 Getting Started (Python)

```python
import pandas as pd

# Load the raw data
df = pd.read_excel('Swiggy_Raw_Data_Excel.xlsx', sheet_name='Swiggy Data')

# Quick overview
print(df.shape)        # (197430, 14)
print(df.info())
print(df.describe())

# Example: Top 5 cities by total revenue
df.groupby('City')['Price (INR)'].sum().sort_values(ascending=False).head(5)

# Example: Average rating by food type
df.groupby('Food Type')['Rating'].mean()
```

---

## 📋 Data Quality Notes

- ✅ **No missing values** across all 14 columns
- ✅ Dates are properly formatted (`datetime`)
- ✅ Food Type is binary (`Veg` / `Non-Veg`) — clean for filtering
- ⚠️ `Rating Count` contains `0` values — these may indicate newly listed restaurants
- ⚠️ Price minimum is `₹0.95` — verify if these are complimentary/add-on items

---

## 📌 Notes

- Data represents a **simulated/sample dataset** modeled after real Swiggy order patterns
- The **Dashboard** sheet is empty and intended as a canvas for building visualizations
- The **Analysis** sheet contains pre-aggregated KPIs and pivot summaries

---


