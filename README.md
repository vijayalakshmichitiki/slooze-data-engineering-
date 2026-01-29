Slooze Take-Home Challenge – Data Engineering & EDA
📌 Overview

This project is an end-to-end data engineering + exploratory data analysis (EDA) pipeline built as part of the Slooze take-home challenge.

The goal is to:

Collect product and supplier data from a B2B marketplace (IndiaMART)

Perform data cleaning and transformation (ETL)

Generate exploratory insights on products, pricing, and supplier locations

The implementation is Jupyter Notebook–based for ease of execution and clarity

slooze-data-engineering/
│
├── notebooks/
│   ├── 01_crawler.ipynb        # Web scraping / data collection
│   ├── 02_etl_cleaning.ipynb   # Data cleaning and transformation
│   ├── 03_eda.ipynb            # Exploratory Data Analysis
│
├── data/
│   ├── raw/                    # Raw scraped data (unmodified)
│   │   └── products_raw.csv
│   ├── processed/              # Cleaned and transformed data
│   │   └── products_clean.csv
│
├── requirements.txt
└── README.md
📂 Data Directory Explanation
data/raw/

Contains raw, unprocessed data collected directly from the source.

No cleaning or transformations applied.

Used as the single source of truth for reproducibility.

Example:

data/raw/products_raw.csv

data/processed/

Contains cleaned and transformed datasets.

Includes normalized prices, removed duplicates, and standardized formats.

Used for EDA and downstream analysis.

Example:

data/processed/products_clean.csv
🛠️ Tech Stack

Python 3

Jupyter Notebook

requests

beautifulsoup4

pandas

matplotlib

seaborn

▶️ How to Run the Project
1️⃣ Install Dependencies
pip install -r requirements.txt

2️⃣ Create Required Data Folders (If Not Present)

Run this once in any Jupyter notebook:

import os

os.makedirs("data/raw", exist_ok=True)
os.makedirs("data/processed", exist_ok=True)

3️⃣ Execute Notebooks in Order

Run notebooks sequentially:

Data Collection

notebooks/01_crawler.ipynb


Scrapes product and supplier data

Saves output to data/raw/products_raw.csv

ETL / Data Cleaning

notebooks/02_etl_cleaning.ipynb


Cleans prices

Removes duplicates

Saves output to data/processed/products_clean.csv

Exploratory Data Analysis

notebooks/03_eda.ipynb


Summary statistics

Price distributions

Supplier location analysis

📊 Exploratory Analysis Highlights

Distribution of product prices by category

Top supplier locations by listing volume

Identification of missing prices and data quality gaps

Category-level pricing trends

⚠️ Limitations & Assumptions

IndiaMART uses dynamic content and bot detection; scraping is limited to publicly accessible HTML

Data volume is intentionally constrained to avoid rate-limiting

Prices are normalized only when explicitly listed





