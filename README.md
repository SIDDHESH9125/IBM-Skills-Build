# Delivery Performance and Customer Retention at a Brazilian Marketplace

A data analytics project (Python) that measures how late deliveries affect customer satisfaction and repeat purchases on the Olist e-commerce marketplace, and recommends what to fix first.

## Business question
How much revenue and customer loyalty is the business losing to delivery delays, and where should it act first (regions, categories, sellers)?

## Dataset
**Brazilian E-Commerce Public Dataset by Olist** (about 100k orders, 2016-2018, 9 linked tables)

Download: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Files used: `olist_orders_dataset.csv`, `olist_order_items_dataset.csv`, `olist_order_reviews_dataset.csv`, `olist_customers_dataset.csv`, `olist_sellers_dataset.csv`, `olist_products_dataset.csv`, `product_category_name_translation.csv`, `olist_geolocation_dataset.csv`.

The data is not included in this repository. A free Kaggle account is needed to download it.

## Project structure
```
.
├── README.md
├── requirements.txt
├── olist_delivery_retention_analysis.ipynb   # full analysis
├── Project_Report.docx                        # written report
└── olist_data/                                # put the downloaded CSV files here
```

## How to run
1. Install Python 3.9 or newer.
2. (Optional) create a virtual environment:
   ```
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # macOS / Linux
   ```
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
4. Download the dataset from the link above and unzip the CSV files into `olist_data/`.
5. Start Jupyter and open the notebook:
   ```
   jupyter notebook olist_delivery_retention_analysis.ipynb
   ```
6. Run all cells (Kernel > Restart & Run All). Summary tables are saved to an `outputs/` folder.

## What the notebook does
| Section | Content |
|---|---|
| 1-3 | Problem statement, data loading, data quality checks |
| 4-5 | Joining tables, feature engineering (delay days, on-time flag, delay buckets) |
| 6 | KPIs: revenue, AOV, on-time rate, delivery time, review score, cancellation and repeat rate |
| 7 | Monthly trends |
| 8 | Drivers: delay vs reviews, state, distance, product category |
| 9 | Customer retention after on-time vs late first orders |
| 10-11 | Risks (state concentration, worst sellers) and opportunities |
| 12-13 | Cost of late delivery and recommendations |

## Key KPIs
On-time delivery rate, average delivery delay, average review score, repeat purchase rate, cancellation rate, revenue and average order value.

## Notes
- Delivery metrics use only orders with status `delivered`.
- Delay is measured against the platform's own estimated delivery date.
- Findings show association, not proof of causation.

## Data credit
Dataset provided by Olist on Kaggle. Please follow the dataset's license terms on the Kaggle page.
