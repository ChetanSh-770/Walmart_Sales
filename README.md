# 🛒 Walmart Sales Analytics – Power BI Report

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow?logo=powerbi)
![DAX](https://img.shields.io/badge/Language-DAX-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-Walmart%20Sales-orange)

---

## 📌 Project Overview

This Power BI report performs an end-to-end sales analytics study on Walmart's weekly sales data across **45 stores** spanning **2010 to 2012**. The report answers 30+ real business questions across executive summaries, trend analysis, store performance, holiday impact, external factor correlation, and sales forecasting.

---

## 📂 Dataset Description

| Column | Description |
|---|---|
| `Store` | Store ID (1–45) |
| `Date` | Week start date |
| `Weekly_Sales` | Sales revenue for that week |
| `Holiday_Flag` | 1 = Holiday week, 0 = Non-holiday week |
| `Temperature` | Average temperature (°F) in the region |
| `Fuel_Price` | Fuel price in the region (USD) |
| `CPI` | Consumer Price Index |
| `Unemployment` | Regional unemployment rate (%) |

- **Total Records:** 6,435
- **Stores:** 45
- **Time Period:** Feb 2010 – Oct 2012

---

## 📊 Key Business Insights

### Executive Summary
| Metric | Value |
|---|---|
| Total Sales Revenue | **$6.74 Billion** |
| Average Weekly Sales | **$1,046,965** |
| Number of Stores | **45** |
| Top Performing Store | **Store #20 ($301.4M)** |
| Lowest Performing Store | **Store #33** |

### Holiday Impact
- Holiday weeks generated **7.84% higher** average sales than non-holiday weeks
- Thanksgiving / Super Bowl periods showed the strongest holiday uplift

### Year-over-Year Sales
| Year | Total Sales |
|---|---|
| 2010 | $2.29 Billion |
| 2011 | $2.45 Billion |
| 2012 | $2.00 Billion (partial year) |

### External Factors
- **Temperature** — Mild weather correlated with higher footfall
- **Fuel Price** — Inverse relationship observed with sales in some stores
- **CPI & Unemployment** — Higher unemployment showed negative correlation with sales volumes

---

## 🗂️ Report Pages

| Page | Title | Content |
|---|---|---|
| 1 | Executive Dashboard | Total Sales KPIs, Top/Bottom 5 Stores, Summary Cards |
| 2 | Sales Trends | Monthly, Quarterly & YoY Line Charts |
| 3 | Store Performance | Store Rankings, Growth Rate, Fluctuation Analysis |
| 4 | Holiday Analysis | Holiday vs Non-Holiday Sales Comparison |
| 5 | External Factors | Scatter Plots for Temp, Fuel, CPI, Unemployment vs Sales |
| 6 | Forecasting & Insights | Trend Forecast, Expected Peaks, Recommendations |

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Report building & visualizations
- **DAX** — Custom measures, KPIs, Time Intelligence functions
- **Power Query (M)** — Data cleaning, date table, column transformations
- **Data Modeling** — Star schema with a Date dimension table

---

## 💡 DAX Measures Used (Sample)

```dax
-- Total Sales
Total Sales = SUM(Walmart[Weekly_Sales])

-- Average Weekly Sales
Avg Weekly Sales = AVERAGE(Walmart[Weekly_Sales])

-- Holiday vs Non-Holiday
Holiday Sales Avg = 
CALCULATE(AVERAGE(Walmart[Weekly_Sales]), Walmart[Holiday_Flag] = 1)

Non-Holiday Sales Avg = 
CALCULATE(AVERAGE(Walmart[Weekly_Sales]), Walmart[Holiday_Flag] = 0)

-- YoY Growth
YoY Growth % = 
DIVIDE(
    [Total Sales] - CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
)
```

---

## 📁 Repository Structure

```
walmart-powerbi-report/
│
├── Walmart.csv                          # Raw dataset
├── Walmart_Report.pbix                  # Power BI report file
├── Walmart_PowerBI_Business_Questions.pdf  # Business questions reference
└── README.md                            # This file
```

---

## 🚀 How to Use

1. Clone this repository
   ```bash
   git clone https://github.com/yourusername/walmart-powerbi-report.git
   ```
2. Open `Walmart_Report.pbix` in **Power BI Desktop**
3. If prompted, re-link the data source to `Walmart.csv` via **Transform Data → Data Source Settings**
4. Explore the 6 report pages

---

## 📬 Connect With Me

**Chetan** | Data Analyst | B.Tech CSE 2024
- 🔗 [LinkedIn](https://linkedin.com/in/yourprofile)
- 💼 Open to Data Analyst roles | Jaipur / Remote
- 📧 your.email@gmail.com

---

⭐ If you found this project helpful, please give it a **star**!
