# Blinkit Data Analysis using SQL

![Blinkit Banner]()

**Tools Used:** SQL, Excel, Power BI

- [Dataset Used](https://www.kaggle.com/datasets/arunkumaroraon/blinkit-grocery-dataset?select=BlinkIT-Grocery-Data.csv)
- [SQL Analysis Code](Blinkit_Data_Analysis.sql)
- [Power BI Dashboard](Blinkit-analysis.pbix)

---

## Business Problem

Conduct a comprehensive analysis of Blinkit's sales performance, customer satisfaction, and inventory distribution to identify key insights and opportunities for optimization, using KPIs and visualizations in Power BI. The goal is a scalable analytics solution that uncovers patterns and trends across the grocery catalog and outlet network.

---

## Data Cleaning

Standardized inconsistent category labels in `Item Fat Content` before analysis:

```sql
UPDATE blinkit_grocery_data SET `Item Fat Content` = 'Regular' WHERE `Item Fat Content` = 'reg';
UPDATE blinkit_grocery_data SET `Item Fat Content` = 'Low Fat' WHERE `Item Fat Content` IN ('LF', 'low Fat');
```

---

## KPI Requirements

| # | KPI | Description |
|---|---|---|
| 1 | Total Sales | Overall revenue generated from all items sold |
| 2 | Average Sales | Average revenue per sale |
| 3 | Number of Items | Total count of items sold |
| 4 | Average Rating | Average customer rating across items |

---

## Granular Analysis

The SQL script breaks KPIs down across multiple business dimensions:

1. **Total Sales by Fat Content** — impact of fat content on sales performance
2. **Total Sales by Item Type** — top-performing product categories
3. **Fat Content by Outlet Location** — regional consumption patterns
4. **Total Sales by Outlet Establishment Year** — how outlet age affects revenue
5. **Sales % by Outlet Size** — correlation between store size and sales contribution
6. **Sales by Outlet Location Type** — geographic distribution of revenue
7. **All Metrics by Outlet Type** — comparative performance across store formats

Full queries are in [`Blinkit_Data_Analysis.sql`](Blinkit_Data_Analysis.sql).

---

## Key Insights

- **Revenue scale:** Total revenue lands in the multi-million range, reflecting strong overall sales performance across the catalog.
- **Fat content:** Sales and ratings vary meaningfully between Low Fat and Regular items, useful for stocking and health-based marketing.
- **Item type:** A handful of categories (e.g., Dairy, Snacks, Beverages) drive a disproportionate share of revenue.
- **Outlet size & location:** Store size and location type both correlate with sales contribution, informing expansion and layout decisions.
- **Outlet type:** Comparing formats (grocery store vs. supermarket) shows clear differences in sales, ratings, and item count, guiding format-specific strategy.

---

## Power BI Dashboard

The dashboard consolidates all KPIs into an executive view covering revenue realization, customer satisfaction, and inventory distribution — enabling drill-down by outlet, item type, and fat content.

Open [`Blinkit-analysis.pbix`](Blinkit-analysis.pbix) in Power BI Desktop to explore interactively.

---

## Repository Structure

```
Blinkit_Data_Analysis.sql   → SQL data cleaning + KPI queries
Blinkit-analysis.pbix       → Power BI dashboard
image.png                   → Dashboard/banner preview
README.md                   → Project documentation
```
