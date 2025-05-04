# E-commerce Funnel Drop-Off Analysis

This repository contains a complete end-to-end **PySpark pipeline and Plotly visualizations** for analyzing user behavior through an e-commerce funnel (`view → cart → purchase`).  
We use large-scale clickstream data to identify user drop-offs, evaluate product/category performance, and provide actionable insights.

📦 **Dataset Source**:  
[Kaggle – E-Commerce Funnel Analysis](https://www.kaggle.com/code/malyshevartem/e-commerce-funnel-analysis/input)

---

## 📁 Data Storage & Structure

The dataset is provided as a single ZIP archive (`ecommercefunnel.zip`) that contains **five nested monthly ZIP files**, each with one CSV:

- `2019-Oct.zip` → `2019-Oct.csv`  
- `2019-Nov.zip` → `2019-Nov.csv`  
- `2019-Dec.zip` → `2019-Dec.csv`  
- `2020-Jan.zip` → `2020-Jan.csv`  
- `2020-Feb.zip` → `2020-Feb.csv`

These are programmatically extracted into a flat folder: `unzipped_csvs/`

### 🔑 CSV Schema

| Column            | Description                                           |
|-------------------|-------------------------------------------------------|
| `event_time`      | Timestamp of user action                              |
| `event_type`      | One of `view`, `cart`, `remove_from_cart`, `purchase` |
| `product_id`      | Unique product identifier                             |
| `category_id`     | Product category ID                                   |
| `category_code`   | Hierarchical product category                         |
| `brand`           | Brand name                                            |
| `price`           | Product price                                         |
| `user_id`         | Unique user identifier                                |
| `user_session`    | Session-level identifier                              |

---
## 📊 Visuals

## Distribution of Session Conversion Times
![Distribution of Session Conversion Times](dist_session_conv.png)

---

## Funnel Drop-off Analysis
![Funnel Drop-off Analysis](funnel_dropoff.png)

---

## Monthly Cart Abandonments
![Monthly Cart Abandonments](monthly_cart_abandonments.png)

---

## Monthly Funnel Progression
![Monthly Funnel Progression](monthly_funnel_prog.png)

---

## Top Brands by Conversion Rate
![Top Brands by Conversion Rate](top_brands_by_conv_rate.png)

---

## Top Categories by Conversion Rate
![Top Categories by Conversion Rate](top_cat_by_conv_rate.png)

## 📂 Repository Structure



![image](https://github.com/user-attachments/assets/72a2d6f3-7c12-4319-b2da-1b9c6c93892b)


---

## Prerequisites

- **Python 3.7+**  
- **Java 8+** (for PySpark)  
- **PySpark**  
- **Plotly**  

Install dependencies:

```bash
pip install -r requirements.txt

