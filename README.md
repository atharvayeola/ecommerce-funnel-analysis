# E-commerce Funnel Drop-Off Analysis

This repository contains a complete end-to-end PySpark pipeline and Plotly visualizations for analyzing user behavior through an e-commerce funnel (`view → cart → purchase`). 
Dataset : https://www.kaggle.com/code/malyshevartem/e-commerce-funnel-analysis/input
The dataset is provided as a single ZIP archive containing five nested ZIP files (one per month), each of which holds a single CSV of raw clickstream events from October 2019 through February 2020.

---

## Why Nested ZIP Extraction?

Our raw data arrived in a single `ecommercefunnel.zip` file, which itself contains five monthly ZIP archives (`2019-Oct.zip`, …, `2020-Feb.zip`). This structure helps:

1. **Organize monthly data** without name collisions  
2. **Enable efficient downloads** and versioning  
3. **Allow incremental updates** by month  

The first step in our pipeline is to programmatically unzip all nested archives into a flat folder (`unzipped_csvs/`) so PySpark can read every CSV at once.

---

## Data Storage & Structure

- **Primary archive**: `ecommercefunnel.zip`  
- **Nested archives**:  
  - `2019-Oct.zip` → `2019-Oct.csv`  
  - `2019-Nov.zip` → `2019-Nov.csv`  
  - `2019-Dec.zip` → `2019-Dec.csv`  
  - `2020-Jan.zip` → `2020-Jan.csv`  
  - `2020-Feb.zip` → `2020-Feb.csv`  
- **Extracted folder**: `unzipped_csvs/` (contains the five CSVs)  
- **Columns in each CSV**:  
  - `event_time` (timestamp of action)  
  - `event_type` (one of `view`, `cart`, `remove_from_cart`, `purchase`)  
  - `product_id`, `category_id`, `category_code`, `brand`, `price`  
  - `user_id`, `user_session`

---

## Repository Structure

ecommerce-funnel-analysis/
├── ecommercefunnel.zip # Main ZIP containing nested monthly ZIPs
├── unzipped_csvs/ # (Generated) CSVs extracted from nested ZIPs
├── ecommerce_funnel_analysis.ipynb # PySpark pipeline + Plotly visualizations
├── requirements.txt # Python dependencies
└── README.md # Project overview and instructions
