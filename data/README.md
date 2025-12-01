# Full Marketing ETL Pipeline — Google Ads, GA4, Python & Power BI

This project is a full end-to-end **Marketing Analytics ETL Pipeline**.

It uses:

- **Python** (Pandas, NumPy, Scikit-learn, XGBoost, PuLP)
- **Google Ads** (simulated via Kaggle marketing dataset)
- **Google Analytics 4 (GA4)** sample ecommerce events
- **Power BI** for dashboards

The goal is to demonstrate how a modern marketing team can:

1. Collect data from Ads + Analytics sources  
2. Clean and unify the data  
3. Calculate core marketing KPIs  
4. Train ML models (ROAS & CPA prediction)  
5. Optimize marketing budget using Linear Programming  
6. Export datasets for Power BI  

---

## 1. Project Overview

This pipeline automatically:

- Loads **Ads / marketing data** (`Brand_Sales_AdSpend_Data.csv`)
- Loads **GA4 raw event data** (`ga4_obfuscated_sample_ecommerce.csv`)
- Aggregates GA4 events → Sessions, Transactions, Revenue
- Merges Ads + GA4 on **Date + Country**
- Cleans numeric fields & handles missing values
- Calculates KPIs:
  - Profit  
  - ROAS  
  - CPA  
  - CTR  
  - CPC  
  - Conversion Rate  
- Trains machine learning models:
  - ROAS → RandomForest, Linear Regression, optional XGBoost
  - CPA → RandomForest
- Runs simple **what-if budget simulations**
- Builds **Linear Programming (PuLP)** budget optimizer
- Saves final datasets ready for BI dashboards

---

## 2. Repository Structure

project_full_marketing_pipeline/
│
├── data/
│ ├── assets/ # Images, diagrams (optional)
│ ├── notebooks/ # Jupyter/Colab notebooks
│ ├── powerbi/ # Power BI (.pbix) dashboard files
│ ├── reports/ # Exported reports
│ ├── scripts/ # Python ETL scripts
│ │ ├── ads_etl.py
│ │ ├── ga4_etl.py
│ │ ├── merge_etl.py
│ │ ├── kpi_engine.py
│ │ └── main_etl.py # Runs the full pipeline
│ │
│ ├── raw/ # Input CSV files (Ads + GA4)
│ │ ├── Brand_Sales_AdSpend_Data.csv
│ │ └── ga4_obfuscated_sample_ecommerce.csv
│ │
│ ├── interim/ # Intermediate datasets
│ └── processed/ # Final cleaned + enriched datasets
│ ├── marketing_ga4_merged_with_kpis.csv
│ ├── product_country_performance.csv
│ ├── what_if_budget_simulation.csv
│ └── lp_budget_recommendations.csv
│
└── README.md # Documentation

---

## 3. Script Breakdown

### **ads_etl.py**
- Loads the Ads/Marketing CSV  
- Cleans column names  
- Ensures numeric formatting  

### **ga4_etl.py**
- Loads GA4 raw events  
- Converts timestamps  
- Builds Sessions, Transactions, Revenue (country-level)  

### **merge_etl.py**
- Joins Ads + GA4  
- Handles NaNs  
- Removes duplicates  

### **kpi_engine.py**
- Calculates KPIs  
- Builds ML models  
- Runs what-if simulations  
- Runs Linear Programming optimizer  

### **main_etl.py**
- Full pipeline runner  
- Calls all ETL steps in correct order  
- Saves all output CSVs under `/processed/`  

---

## 4. How to Run

### Install required packages:
```bash
pip install pandas numpy scikit-learn xgboost pulp

Run the full ETL pipeline:
cd data/scripts
python main_etl.py

Output files are saved here:
data/processed/
   marketing_ga4_merged_with_kpis.csv
   product_country_performance.csv
   what_if_budget_simulation.csv
   lp_budget_recommendations.csv

5. Power BI
data/processed/marketing_ga4_merged_with_kpis.csv
Recommended visuals:

ROAS vs Spend

CPA by Country / Brand

Revenue vs Sessions

Linear Programming budget recommendations

6. Notes

XGBoost & PuLP optional—pipeline still works without them

Project uses simulated / sample datasets

Designed for portfolio demonstration

---

##  Pipeline Architecture (Optional)
Below is the architecture of the full Marketing ETL pipeline, including Ads + GA4 + KPIs:

![Pipeline Architecture](data/assets/pipeline_diagram.png)

---

## Power BI Dashboard Preview (Optional)
A preview of the final Marketing Performance Dashboard:

![Power BI Dashboard](data/assets/dashboard_preview.png)

---

## How to Run the Project

### 1. Install required libraries
```bash
pip install -r requirements.txt

Set your environment variables
GA4_API_KEY=your_ga4_key
ADS_CLIENT_ID=your_client_id
ADS_CLIENT_SECRET=your_secret

 Run the full pipeline
python data/scripts/main_etl.py


 Open Power BI dashboard
data/processed/marketing_ga4_merged_with_kpis.csv


7. Contact

Özlem Tonbul
Digital Marketing & Data Analyst

GitHub: https://github.com/ozlemtonbul

Email: ozlemtonbul34@gmail.com
