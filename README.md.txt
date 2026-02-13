# Vendor Performance Analytics: SQL · Python · Power BI

This repository showcases an end-to-end vendor performance analytics project, starting from raw transactional data and ending with an interactive Power BI dashboard and business recommendations.[web:11][web:19]

---

## 1. Business Problem

Wholesale and retail businesses rely on hundreds of vendors, but not all vendors contribute equally to revenue, margin, and operational efficiency.[web:11][web:19]  
The goal of this project is to evaluate vendor performance across sales, purchasing, and inventory so that decision-makers can:

- Identify high- and low-performing vendors.
- Optimize pricing and discount strategies.
- Reduce capital locked in slow-moving or unsold inventory.
- Focus on vendors and brands that drive sustainable profitability.[web:11][web:19]

---

## 2. Tech Stack

- **Database:** SQL / SQLite  
- **Programming:** Python (Pandas, NumPy, Seaborn, Matplotlib, SciPy / Statsmodels)[web:11][web:17][web:20]  
- **Visualization:** Power BI Desktop  
- **Environment:** Jupyter Notebook, command line (for scripts)

---

## 3. Project Workflow

### 3.1 Data Loading & ETL

- Ingested multiple raw CSV files (purchases, purchase prices, sales, vendor invoices, etc.) into a SQLite database.  
- Built an ingestion script with basic logging to track file loads and catch data quality issues (e.g., missing values, invalid dates).[web:11][web:19]  
- Standardized column names, data types, and keys (vendor, brand, product) to ensure consistent joins across tables.

### 3.2 SQL Aggregation: `vendor_sales_summary`

- Wrote SQL queries to join large sales, purchase, pricing, and freight tables into a consolidated vendor-level summary.[web:11][web:19]  
- Created a `vendor_sales_summary` table containing metrics such as:
  - Total sales quantity and sales revenue  
  - Total purchase quantity and purchase cost  
  - Freight cost by vendor  
  - Product- and brand-level rollups for vendors[web:11][web:19]

### 3.3 EDA & Feature Engineering

- Performed exploratory data analysis in Python to understand distributions, outliers, and trends in vendor and brand performance.[web:11][web:19]  
- Engineered key business metrics, including:
  - Gross profit and profit margin  
  - Stock turnover and days on hand  
  - Unsold / slow-moving inventory  
  - Contribution of each vendor and brand to overall sales and margin[web:19]  
- Used visualizations (histograms, boxplots, bar charts, correlation heatmaps) to highlight performance differences across vendors and brands.

### 3.4 Statistical Analysis

- Applied confidence intervals and hypothesis tests to compare vendor profit margins and validate whether observed differences were statistically meaningful.[web:17][web:20]  
- Example analyses:
  - Tested whether average margin of top vendors is significantly higher than the portfolio average.  
  - Estimated confidence intervals for key KPIs (profit margin, stock turnover) to quantify uncertainty.[web:17][web:20]

### 3.5 Power BI Dashboard

- Built an interactive Power BI dashboard on top of the `vendor_sales_summary` output (and related tables) to support business users.[web:11][web:19]  
- Key pages / visuals:
  - High-level KPIs (revenue, gross profit, margin, number of vendors).  
  - Top vendors and brands by sales, margin, and volume.  
  - Purchase and sales contribution by vendor, brand, and segment.  
  - Low-turnover / high-inventory vendors and brands.  
  - Shortlist of “target brands” and vendors for growth or optimization actions.[web:19]

### 3.6 Final Report & Recommendations

- Summarized insights in a short report (and presentation-ready visuals) for stakeholders.  
- Example recommendations:
  - Increase focus on vendors with strong margins but moderate sales to unlock growth.  
  - Revisit pricing and discounting for vendors with high volume but weak profitability.  
  - Reduce exposure to vendors driving high inventory and low turnover, or renegotiate terms.[web:19][web:20]

---

## 4. How to Run the Project

### 4.1 Requirements

- Python 3.9+  
- Recommended packages:
  - `pandas`, `numpy`  
  - `matplotlib`, `seaborn`  
  - `scipy`, `statsmodels`  
  - `sqlite3` (standard library)  
  - `jupyter` (for notebooks)  
- Power BI Desktop (latest version) to open the `.pbix` file.[web:11]

You can install the Python dependencies via:

```bash
pip install -r requirements.txt
