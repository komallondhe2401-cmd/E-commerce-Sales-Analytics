# 🛒 E-commerce Sales Analytics

An end-to-end sales analytics project on online retail transaction data, using **Python**, **SQL**, and **Power BI** to uncover sales trends, top-performing products, customer behavior, and country-wise performance.

---

## 🎥 Demo Video

> **[▶️ Watch the dashboard walkthrough] (https://drive.google.com/file/d/1aR9uQfA53vlHrXUOvZpOXey-3tzfOCaH/view?usp=drive_link)**


---

## 📸 Dashboard Screenshots

### Sales Overview
![Sales Overview Dashboard](C:\Users\Isha\Desktop\AI_ML\E-Commerce Sales Analytics\Images\Overview.png)

### Product Performance Analysis
![Product Performance Analysis](C:\Users\Isha\Desktop\AI_ML\E-Commerce Sales Analytics\Images\Product Performance Analysis.png)

### Customer & Country Analysis
![Customer and Country Analysis](C:\Users\Isha\Desktop\AI_ML\E-Commerce Sales Analytics\Images\Customer & Country Analysis.png)

---

## 📌 Project Overview

Businesses generate large volumes of transaction data, but raw data alone doesn't drive decisions. This project cleans and analyzes about **1 million retail transactions** to answer questions such as:

- How do sales change over time? Are there seasonal peaks?
- Which products generate the most revenue?
- Which countries and customers contribute the most?
- How do returns and cancellations affect revenue?

---

## 🗂️ Dataset

| Detail | Value |
|--------|-------|
| Source | Online Retail transactions (UK-based gift retailer) |
| Period | December 2009 – December 2011 |
| Raw rows | 1,048,575 |
| Rows after cleaning | 1,014,420 |
| Countries | 43 |
| Unique products | 5,304 |
| Unique customers | 5,925 (including an "Unknown" group) |
| Invoices | 52,956 |

**Columns:** `Invoice`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `Price`, `Customer ID`, `Country`

---

## 🛠️ Tools & Technologies

- **Python** (pandas, NumPy, matplotlib) – data cleaning, feature engineering, EDA
- **SQL** – business queries on the cleaned data
- **Power BI** – interactive dashboard and KPI tracking
- **Jupyter Notebook** – analysis workflow

---

## 🧹 Data Cleaning Steps

1. **Checked data quality**: shape, types, missing values, duplicates, and summary statistics.
2. **Missing descriptions** (4,372 rows) filled with `Unknown Product`.
3. **Missing Customer IDs** (236,682 rows, 22.57%) labeled `Unknown`, so the sales stay in revenue totals.
4. **Removed 34,150 exact duplicate rows.**
5. **Converted `InvoiceDate`** to datetime format.
6. **Removed 5 invalid records** with negative prices (bad-debt adjustments).
7. **Created new features:** `Sales` (Quantity × Price), `Year`, `Month`, `YearMonth`.
8. **Reviewed returns/cancellations:** 18,872 rows with cancelled invoices (prefix "C") and 22,244 rows with negative quantity.

The cleaned dataset was exported as `online_retail_cleaned.csv`.

---

## 📊 Key Insights

- **Total net sales:** about **$18.7M** across **52,956 invoices**.
- **Strong seasonality:** sales rise from **September to November** and peak in **November** in both years (**~$1.46M in Nov 2011**, **~$1.42M in Nov 2010**).
- **Top products by revenue:** Regency Cakestand 3 Tier (~$309K) and White Hanging Heart T-Light Holder (~$250K) lead the list.
- **Non-product entries** such as *Postage* and *Dotcom Postage* also appear among top revenue lines and should be excluded from product rankings.
- **December 2011 looks low only because the data ends on 4 December**, so it is a partial month.

> 💡 Add your Power BI findings here (top countries, customer insights, KPI highlights).

---

## 📈 Power BI Dashboard

The dashboard (`Sales Dashboard.pbix`) includes:

- **Sales Overview:** KPI cards (total sales, orders, customers, average order value) and monthly sales trend
- **Product Performance Analysis:** top products and revenue contribution
- **Customer & Country Analysis:** customer behavior and country-wise sales
- Filters for year, month, product, and country

---

## 📁 Repository Structure

```
E-commerce-Sales-Analytics/
│
├── Dataset/                  # Raw and cleaned data
├── images/                   # Dashboard screenshots used in this README
├── Retail_file.ipynb         # Data cleaning and EDA (Python)
├── Sales Dashboard.pbix      # Power BI dashboard
└── README.md
```

---

## ⚠️ Limitations & Next Steps

- Returns (negative quantities) are included in net sales.
- 5,978 zero-price rows and 3,373 negative-quantity rows without a cancellation prefix were retained and could be investigated further.
- Customer-level metrics should exclude the `Unknown` group.
- **Future work:** RFM customer segmentation, sales forecasting, and a product-return analysis.

---
s