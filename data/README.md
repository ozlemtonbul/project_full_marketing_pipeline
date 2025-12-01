Full Marketing ETL Pipeline
Google Ads API | GA4 API | Python | Power BI

This project is an end-to-end Marketing Analytics Pipeline built using Python, Google Ads API, GA4 Data API, Pandas, and Power BI.
It automates data extraction, transformation, KPI generation, and dashboard reporting — providing a unified marketing analytics workflow.

This simulation uses sample Kaggle datasets but follows a real enterprise pipeline architecture.

 Project Overview

This pipeline automatically:

Connects to Google Ads API

Connects to Google Analytics 4 (GA4) API

Extracts raw marketing data daily (cron job / automation ready)

Cleans and transforms marketing + analytics data

Generates marketing KPIs:

ROAS

CPA

CTR

CPC

Conversion Rate

Revenue

Sessions

Bounce Rate

Saves cleaned datasets into structured folders

Pushes final outputs to Power BI

Builds automated dashboards for business stakeholders

 Repository Structure
project_full_marketing_pipeline/
│
├── assets/                # Visuals, architecture diagrams, etc.
│
├── notebooks/             # Jupyter notebooks for development
│
├── powerbi/               # Power BI (.pbix) dashboard files
│
├── reports/               # Auto-generated reports (weekly/monthly)
│
├── scripts/               # Python ETL scripts
│   ├── ads_etl.py
│   ├── ga4_etl.py
│   ├── merge_etl.py
│   ├── kpi_engine.py
│   └── scheduler_cron.sh (optional for automation)
│
├── data/
│   ├── raw/               # Raw API responses
│   ├── interim/           # Intermediate cleaned data
│   └── processed/         # Final datasets for BI
│
└── README.md              # Project documentation

Technologies Used

Python 3.10+

Google Ads API

Google Analytics 4 Data API (GA4 Data API)

Pandas, NumPy, Requests

Power BI Desktop

Cron / Task Scheduler for automation

Kaggle sample datasets (simulation)

 Pipeline Architecture (High-Level)
1. Data Extraction

Fetch data from Google Ads API

Fetch data from GA4 API

Save results into /data/raw/

2. Data Cleaning & Transformation

Convert schemas

Normalize column names

Merge Ads + GA4 datasets

Save to /data/interim/

3. KPI Engine

Calculate:

ROAS

CPC

CPA

CTR

Conversion Rate

Revenue per Session

Save to /data/processed/

4. Reporting & Dashboarding

Load processed datasets into Power BI

Build:

Marketing Performance Dashboard

Campaign-level insights

Device/Country segmentation

Auto-refresh supported via scheduled Python script

Power BI Dashboard Features

Daily marketing KPIs

Spend, Clicks, Impressions

Revenue & Conversion metrics

Campaign-level performance

GA4 behavior metrics (Sessions, Bounce Rate, etc.)

Trend analysis

Filters for:

Country

Device

Campaign

Date range

Project Goals

This project demonstrates:

End-to-end data engineering workflow

Python ETL development

API integrations

Marketing analytics expertise

Clean and scalable project structure

Dashboard building for decision-makers

Realistic simulation of an enterprise data pipeline

How to Reproduce

Clone the repository

Install dependencies:

pip install -r requirements.txt


Add API credentials (Google Ads / GA4) as environment variables

Run ETL scripts:

python ads_etl.py
python ga4_etl.py
python merge_etl.py
python kpi_engine.py


Open Power BI → Load dataset from /data/processed/

Refresh dashboard → Done 

Contact

Özlem Tonbul
Digital Marketing & Data Analyst

GitHub: https://github.com/ozlemtonbul

Email: ozlemtonbul34@gmail.com
