# VendorIQ-Performance-Analytics

## 🚀 Project Overview

This project analyzes vendor performance to unlock insights for profitability, operational efficiency, and data-driven procurement decisions. It employs Python for data engineering and analysis, Jupyter Notebooks for exploratory data analysis (EDA), and Power BI for interactive dashboarding and reporting. The process encompasses data ingestion, transformation, aggregation, statistical analysis, and visualization.

## 🗂️ Directory Structure
<img width="434" height="358" alt="image" src="https://github.com/user-attachments/assets/95791e1e-9df2-4a8f-b72b-6dde517f0fca" />


## 🛠️ Tech Stack

- **Python**: pandas, numpy, sqlite3, matplotlib, seaborn, sqlalchemy, scipy
- **Jupyter Notebook**: Interactive data exploration and EDA
- **Power BI**: Dashboard creation and visualization
- **SQLite**: Local lightweight data warehouse for processing
- **Excel/PDF**: Final reporting and data export

## 📊 Problem Statement

Organizations manage purchases and sales with a network of vendors and need actionable insight to:
- Identify top/bottom performing vendors and brands
- Optimize purchase quantities and prices
- Increase inventory turnover
- Reduce locked capital in unsold inventory
- Enhance profitability using data

## 🔄 Solution Workflow

1. **Data Ingestion**
   - Automated loading of CSVs into SQLite using `ingestion_db.py`
   - Each CSV table is imported and mapped for downstream analysis

2. **Aggregation & Preprocessing**
   - SQL and pandas-based aggregation: vendor-wise sales, purchase, freight, price, and profitability calculations (performed in `get_vendor_summary.py` and notebooks)
   - Cleaning: removing whitespaces, filling missing values, type conversions, feature engineering (KPIs: GrossProfit, ProfitMargin, SalesToPurchaseRatio, etc.)

3. **Exploratory Data Analysis**
   - Statistical summaries, outlier detection, correlation analysis
   - Visualizations: histograms, boxplots, bar charts, scatterplots
   - Identification of inefficiencies and actionable opportunities

4. **Dashboarding & Reporting**
   - Results aggregated and loaded into Power BI (`vendor_performance.pbix`)
   - Executive-ready PDF report (`Vendor Performance Report.pdf`)

## 📝 Key Features

- Automated data pipeline from raw CSVs to aggregated report tables
- Comprehensive database overview and joining logic:
    - Sales, purchases, freight, and inventory integrated via SQL CTEs
- Deep data cleaning and transformation for robust analysis
- Custom KPIs and business-relevant metrics for procurement and sales
- Statistical tests for significance in vendor profitability
- Clear separation and visualization of high- and low-performing vendors/brands
- Dashboard for ongoing monitoring; PDF reporting for periodic review

## 📊 Main KPIs & Insights

- **Gross Profit & Profit Margin**: Identify loss-making products/vendors; optimize pricing
- **Stock Turnover**: Pinpoint slow-moving inventory and vendors
- **Bulk Purchasing Impact**: Quantify cost savings by order size (bulk vs. small orders)
- **Vendor Dependency**: Pareto analysis of spend and sales
- **Locked Capital**: Capital tied in unsold inventory per vendor
- **Statistical Testing**: Significant differences in profit margins across vendor segments

## 📈 Outputs

| Output                         | Location/Script                         | Description                                     |
|---------------------------------|-----------------------------------------|-------------------------------------------------|
| Vendor sales summary CSV        | `vendor_sales_summary.csv`              | Master analytics data for dashboard/reporting    |
| Automated summary script        | `get_vendor_summary.py`                 | Run to generate/update summary tables            |
| EDA & analytics notebooks       | `*.ipynb`                              | Insights, data cleaning, ad hoc analysis         |
| Power BI Dashboard             | `vendor_performance.pbix`               | Interactive executive dashboard                  |
| Final Report PDF               | `Vendor Performance Report.pdf`          | Ready-to-share insights                         |

## 💻 How To Run

1. **Clone the repository**
   ```sh
   git clone <repo_url>
   cd Vendor-Performance-Analysis-
   ```

2. **Install Python dependencies**
   - Ensure you have Python 3, pip, and the following modules: pandas, numpy, matplotlib, seaborn, sqlalchemy, scipy, sqlite3 (most are standard or via pip).

3. **Ingest raw .csv data to SQLite**
   ```
   python ingestion_db.py
   ```
   - Raw data should be present in the `/data` folder, if not, place them accordingly.

4. **Generate vendor summary tables**
   ```
   python get_vendor_summary.py
   ```

5. **Explore & analyze**
   - Open Jupyter Notebook and run the EDA and analytics notebooks for interactive exploration.

6. **Visualize in Power BI**
   - Open `vendor_performance.pbix` for dashboards.
   - [Power BI Desktop download](https://powerbi.microsoft.com/desktop/)

7. **Review insights**
   - Refer to `Vendor Performance Report.pdf` for final recommendations.

## 📚 Notebooks & Scripts Summary

- **Exploratory Data Analysis.ipynb**
  - Database overview, data profiling, need definition, column analysis, summary statistics, data cleaning, feature engineering.

- **Vendor Performance Analysis.ipynb**
  - KPI breakdown, EDA visualizations, vendor/brand performance, correlation, advanced analytics (Pareto, confidence intervals, statistical testing).

- **get_vendor_summary.py**
  - Automated SQL and pandas pipeline for extracting, merging, and cleaning vendor analytics tables.

- **ingestion_db.py**
  - Utility script for ingesting all relevant CSV files into SQLite, mapping filenames to tables.

## ⚡ Data Model

**Main Tables:**
- `purchases`, `purchase_prices`, `vendor_invoice`, `sales`, (and the derived `vendor_sales_summary`).

**Summary Table (vendor_sales_summary):**
- VendorNumber, VendorName, Brand, Description, PurchasePrice, ActualPrice, Volume, TotalPurchaseQuantity, TotalPurchaseDollars, TotalSalesQuantity, TotalSalesDollars, FreightCost, GrossProfit, ProfitMargin, StockTurnover, SalesToPurchaseRatio

## 📬 Contact

For any queries, feedback, or collaboration, connect via [LinkedIn](https://www.linkedin.com/in/hrishit-b-5188951b6/).

---

**Note:** The data and scripts are for demonstration and educational purposes, do not share or use sensitive corporate data publicly.
