# E-Commerce Logistics & Commercial Analytics (Brazilian Olist)

An end-to-end exploratory analysis examining regional delivery performance, product category demand, and customer review drivers across 100k+ Brazilian e-commerce orders.

---

## 📌 Executive Summary & Key Findings

1. **Severe Geographic Volume Concentration:** 
   * São Paulo dominates total commercial throughput, generating more item volume (>17,000 items) than the next four largest metropolitan markets combined.
   * However, product category share is remarkably uniform across all top cities: core essentials (`bed_bath_table`, `health_beauty`, `sports_leisure`, `furniture_decor`) represent ~60–65% of demand, with a resilient ~35% "long tail" of miscellaneous categories.

2. **Regional Fulfillment Variance:**
   * Delivery lead times vary significantly by customer state. Metropolitan hubs close to logistics centers (e.g., São Paulo) show tight, predictable delivery distributions, whereas regional states experience higher variance and longer median lead times.

3. **Asymmetric Impact of Logistics on Customer Sentiment:**
   * Global rank correlation between delivery delay and review scores appears modest ($\rho = -0.176$) due to ceiling effects (on-time orders cap at 5 stars with diminishing returns for early delivery).
   * Conditional analysis reveals an operational drop-off cliff: once an order breaches its estimated delivery date, the rate of 1-star reviews spikes dramatically, proving delivery punctuality is a baseline expectation rather than an incremental value-add.

4. **Revenue & Seasonality Trends:**
   * Monthly Gross Merchandise Value (GMV) demonstrated aggressive growth across 2017, punctuated by a major Black Friday demand surge in November 2017, before stabilizing at ~R$ 800k–1M monthly through 2018.

---

## 🛠️ Tech Stack & Architecture

* **Analytical Engine / SQL:** [DuckDB](https://duckdb.org/) (direct multi-table relational joins, window functions, and timestamp transformations directly on raw CSV/Parquet files).
* **Data Processing & Manipulation:** Python, [Pandas](https://pandas.pydata.org/).
* **Data Visualization:** [Matplotlib](https://matplotlib.org/), [Seaborn](https://seaborn.pydata.org/) (normalized and raw stacked bar charts, dual-axis bar charts, time-series trends).
* **Environment & Version Control:** Jupyter Notebooks, VS Code, Git, GitHub Desktop.

---

## 📂 Project Structure

```text
ecommerce-analytics/
├── data/                                 # Raw relational CSV datasets (Olist)
│   ├── olist_orders_dataset.csv
│   ├── olist_customers_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   └── product_category_name_translation.csv
├── notebooks/
│   └── analysis.ipynb                    # Primary end-to-end analytical notebook
├── README.md                             # Project documentation & business insights
└── requirements.txt                      # Python dependencies
