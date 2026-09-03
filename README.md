## Overview
A two-page Power BI executive analytics suite built on a star schema architecture to monitor enterprise financial performance, operational fulfillment, and vendor reliability.

## Data Source
* **Origin:** [Supply Chain Datasets on Kaggle](https://www.kaggle.com/datasets/ayodejiibrahimlateef/supply-chain-datasets?resource=download)

## Architecture & Key Metrics
* **Data Model:** Transaction fact tables (`sales_orders`, `procurement_orders`) joined to core dimensions (`customer_master`, `supplier_master`, `product_master`, `Dim_Date`).
* **Core Measures:** `Total Purchase Orders`, `Supplier On-Time Rate`, and `Average Delivery Delay (Days)`.

## Repository Files
* `Supply_Chain_Dashboard.pbix`: Master Power BI desktop file containing relationships, DAX measures, and dashboard layouts.
* `data/`: Normalized CSV tables powering the relational model.

## Local Setup
1. Clone or download the repository.
2. Open `Supply_Chain_Dashboard.pbix` in Power BI Desktop.
3. Update source file paths in **Transform Data** > **Data Source Settings** if needed, then click **Close & Apply**.
