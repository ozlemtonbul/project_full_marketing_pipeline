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
6. Send final datasets to Power BI  

---

# ## 1. Project Structure

```
project_full_marketing_pipeline/

├── data/
│   ├── assets/                     # Images, diagrams
│   │   ├── marketing_etl_pipeline.png
│   │   ├── etl_pipeline_architecture.png
│   │   └── .keep
│   ├── notebooks/                 # Jupyter Notebooks (optional)
│   ├── powerbi/                   # Power BI dashboard (.pbix)
│   ├── reports/                   # Exported reports
│   ├── scripts/                   # Python ETL pipeline scripts
│   │   ├── ads_etl.py
│   │   ├── ga4_etl.py
│   │   ├── merge_etl.py
│   │   ├── kpi_engine.py
│   │   └── main_etl.py            # Master pipeline runner
│   ├── raw/                       # Input CSVs (Ads + GA4)
│   │   ├── Brand_Sales_AdSpend_Data.csv
│   │   └── ga4_obfuscated_sample_ecommerce.csv
│   ├── interim/                   # Intermediate datasets
│   └── processed/                 # Final outputs for Power BI
│       ├── marketing_ga4_merged_with_kpis.csv
│       ├── product_country_performance.csv
│       ├── what_if_budget_simulation.csv
│       └── lp_budget_recommendations.csv
│
└── README.md
```

---

# ## 2. Pipeline Flow – High Level Diagram

![Marketing ETL Pipeline](data/assets/marketing_etl_pipeline.png)

---

# ## 3. ETL Pipeline Architecture (Technical)

![ETL Pipeline Architecture](data/assets/etl_pipeline_architecture.png)

---

# ## 4. Features Included

### Data Cleaning & Normalization
- Handles missing values  
- Standardizes naming conventions  
- Merges Ads + GA4 datasets  

### KPI Engine
Automatically calculates:
- ROAS
- ROI
- CPA
- CTR
- Conversion Rate
- Profit
- Country & Product level performance

###  Machine Learning Models
- Predict future ROAS  
- Predict CPA  
- Scikit-learn + XGBoost  

###  Budget Optimization
Linear Programming model using **PuLP**:
- Allocates budget across channels  
- Maximizes revenue or conversions  

### Final Output
Delivered as **Power BI dashboard** (.pbix)

---

# ## 5. How to Run the Project

### **1. Install required libraries**
```bash
pip install -r requirements.txt
```

### **2. Set environment variables**
You should export your API keys if using real APIs:

```bash
export GA4_API_KEY=your_ga4_key
export ADS_CLIENT_ID=your_client_id
export ADS_CLIENT_SECRET=your_secret
```

### **3. Run the full ETL pipeline**
```bash
cd data/scripts
python main_etl.py
```

### **4. Outputs will be generated here:**
```
data/processed/
```

Main output file for Power BI:
```
data/processed/marketing_ga4_merged_with_kpis.csv
```

---

# ## 6. Power BI Dashboard

After running the pipeline, open the dashboard:

```
data/powerbi/marketing_dashboard.pbix
```

This Power BI file automatically reads:

- **Merged marketing dataset**
- **KPI-enriched tables**
- **Product & Country performance**
- **Budget simulation results**

---

# ## 7. Outputs Included

### **Processed datasets**
- marketing_ga4_merged_with_kpis.csv  
- product_country_performance.csv  
- what_if_budget_simulation.csv  
- lp_budget_recommendations.csv  

### **Visuals**
- Marketing ETL Pipeline Diagram  
- ETL Architecture Diagram  

---

# ## 8. Contact

**Özlem Tonbul**  
Digital Marketing & Data Analyst  

GitHub: https://github.com/ozlemtonbul  
Email: ozlemtonbul34@gmail.com  

---
