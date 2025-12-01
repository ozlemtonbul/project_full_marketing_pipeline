# Full Marketing ETL Pipeline — Google Ads, GA4, Python & Power BI

This project is a full end-to-end **Marketing Analytics ETL Pipeline** built with real-world structure and modular scripts.

It uses:

- **Python** (Pandas, NumPy, Scikit-learn, XGBoost, PuLP)
- **Google Ads** (simulated via Kaggle marketing dataset)
- **Google Analytics 4 (GA4)** sample ecommerce events
- **Power BI** for dashboards

The goal is to demonstrate how a modern marketing team can:

1. Collect data from Ads + Analytics sources  
2. Clean and unify the datasets  
3. Calculate core marketing KPIs  
4. Train ML models (ROAS & CPA prediction)  
5. Optimize marketing budgets using Linear Programming  
6. Export datasets for BI dashboards  

---

## 1. Project Overview

This pipeline automatically:

- Loads **Ads / marketing data**  
- Loads **GA4 raw analytics events**  
- Aggregates GA4 → Sessions, Transactions, Revenue  
- Merges Ads + GA4 on **Date + Country**  
- Cleans missing / incorrect values  
- Calculates KPIs:
  - Profit  
  - ROAS  
  - CPA  
  - CTR  
  - CPC  
  - Conversion Rate  
- Trains ML models for:
  - ROAS prediction  
  - CPA prediction  
- Runs **budget simulations (-20%, +20%)**  
- Creates **Linear Programming** budget optimization  
- Saves final datasets for Power BI

---

## 2. Repository Structure

project_full_marketing_pipeline/
│
├── data/
│ ├── assets/ # Diagrams, dashboard previews
│ ├── notebooks/ # Jupyter/Colab notebooks
│ ├── powerbi/ # .pbix dashboard file
│ ├── reports/ # Exported analytical reports
│ ├── scripts/ # Python ETL scripts
│ │ ├── ads_etl.py
│ │ ├── ga4_etl.py
│ │ ├── merge_etl.py
│ │ ├── kpi_engine.py
│ │ └── main_etl.py # Runs full pipeline
│ │
│ ├── raw/ # Input CSV files
│ │ ├── Brand_Sales_AdSpend_Data.csv
│ │ └── ga4_obfuscated_sample_ecommerce.csv
│ │
│ ├── interim/ # Intermediate files
│ └── processed/ # Final cleaned datasets
│ ├── marketing_ga4_merged_with_kpis.csv
│ ├── product_country_performance.csv
│ ├── what_if_budget_simulation.csv
│ └── lp_budget_recommendations.csv
│
└── README.md


---

## 3. Script Breakdown

### **ads_etl.py**
- Loads Ads dataset  
- Cleans column names and numeric formats  

### **ga4_etl.py**
- Loads GA4 events  
- Converts timestamps  
- Extracts Sessions, Transactions, Revenue  

### **merge_etl.py**
- Merges Ads + GA4 on Date & Country  
- Handles missing values  
- Removes duplicates  

### **kpi_engine.py**
- Calculates all core KPIs  
- Builds ML models (ROAS, CPA)  
- Runs budget simulation  
- Runs Linear Programming optimizer  

### **main_etl.py**
- Full pipeline runner  
- Calls all ETL scripts  
- Saves final processed files  

---

## 4. How to Run the Project

### 1. Install required libraries
```bash
pip install -r requirements.txt


Run the full ETL pipeline
cd data/scripts
python main_etl.py


 Output files (auto-generated)
data/processed/
    marketing_ga4_merged_with_kpis.csv
    product_country_performance.csv
    what_if_budget_simulation.csv
    lp_budget_recommendations.csv


Power BI Dashboard
data/processed/marketing_ga4_merged_with_kpis.csv


Recommended visuals:

ROAS vs Ad Spend

CPA by Country

Revenue vs Sessions

Transactions vs Clicks

Predicted ROAS (ML Model)

LP Budget Optimization Results

Marketing ETL Pipeline Diagram

![Marketing ETL Pipeline](data/assets/marketing_etl_pipeline.png.png)


ETL Pipeline Architecture

![ETL Pipeline Architecture](data/assets/etl_pipeline_architecture.png.png)


Contact

Özlem Tonbul
Digital Marketing & Data Analyst

GitHub: https://github.com/ozlemtonbul

Email: ozlemtonbul34@gmail.com
