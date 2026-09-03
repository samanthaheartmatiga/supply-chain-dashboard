You don't strictly *need* to record a video if your documentation is clear enough for them to spin it up and explore independently, but including a 60-second Loom or OBS recording acts as an instant hook for recruiters or reviewers who might not want to download and open Power BI Desktop right away.

Below is a complete, professional project documentation template tailored for your GitHub repository. You can copy and paste this directly into your repo's `README.md` file.

---

# Supply Chain & Procurement Control-Room Dashboard

A high-density, two-page Power BI analytics suite built to monitor executive financial health and deep-dive into operational fulfillment, vendor reliability, and supply chain bottlenecks.

## Architectural Overview & Data Model

* **Star Schema Architecture:** Built around a central fact structure connecting transactional tables (`sales_orders`, `procurement_orders`) to dimension tables (`customer_master`, `supplier_master`, `product_master`, and a custom `Dim_Date` calendar).
* **Cross-Filtering & Relationships:** Resolved procurement-to-vendor relationships to segment supplier performance accurately across custom time-intelligence and delivery measures.

## Dashboard Pages & Key Visualizations

### Page 1: Executive Overview

* **Top KPI Banner:** Real-time summary cards for `Total Revenue`, `Total Orders`, `Gross Profit`, and `On-Time Delivery Rate` paired with micro trendlines.
* **Financial & Regional Breakdown:** Clustered column charts mapping profit by country, profit vs. COGS distribution, and average order value trends over time.
* **Operational Flow:** Donut and stacked bar distributions tracking order volume by market segment and fulfillment status across shipping modes.

### Page 2: Operations & Vendor Deep-Dive

* **Vendor Reliability Matrix:** Dynamic matrix tracking custom `Supplier On-Time Rate` alongside multi-variable filters for Category, Shipping Mode, and Region.
* **Category & Volume Analysis:** Weighted Treemaps and bottleneck bar charts highlighting product categories experiencing the highest shipping lags.
* **Procurement Pipeline & Timeline:** Area charts and comparative stacked bars monitoring purchasing volume and delivery delay trends across vendors.

## Custom DAX Measures

Key metrics engineered for this dashboard include:

* `Late Orders = CALCULATE(COUNTROWS(sales_orders), sales_orders[Delivery_Status] = "Late")`
* `Supplier On-Time Rate = DIVIDE(CALCULATE(COUNTROWS(procurement_orders), procurement_orders[Delivery_Date_Actual] <= procurement_orders[Delivery_Date_Planned]), COUNTROWS(procurement_orders), 0)`
* `Average Delivery Delay (Days) = AVERAGEX(procurement_orders, INT(procurement_orders[Delivery_Date_Actual] - procurement_orders[Delivery_Date_Planned]))`

## How to Run Locally

1. Clone this repository or download the `.pbix` file.
2. Open the file using **Power BI Desktop**.
3. If necessary, update the data source file paths via **Transform Data** > **Data Source Settings** to match your local directory.
4. Explore the interactive control-room interface using the cross-filtering slicers and page navigator.
