# Interactive Sales & Financial Power BI Dashboard

A professional, interactive Business Intelligence dashboard designed to analyze and present performance trends from a **Sales Financial Dataset** (Kaggle). This project features a polished corporate blue/white design, robust KPI tracking, and multidimensional slicers.

## Project Structure

```
Task-3-Dashboard-Design/
│
├── Dataset/
│   └── Sales_Financial.csv          # Generated Kaggle-equivalent sales dataset (1500 records)
│
├── Dashboard/
│   ├── Sales_Dashboard.pbix         # Power BI project file (with import/data model schema)
│   └── Dashboard.pdf                # Multi-page export of the dashboard sheets
│
├── PPT/
│   └── Dashboard_Summary.pptx       # 5-Slide Executive Summary Presentation
│
├── Screenshots/
│   ├── Dashboard_Home.png           # Unfiltered homepage view of the dashboard
│   ├── Sales_Trend.png              # Detailed line chart showing sales over time
│   ├── Profit_Analysis.png          # Side-by-side category profit and top products analysis
│   └── Filters.png                  # Filtered view illustrating interactive state
│
└── README.md                        # Documentation and project guide
```

---

## Dataset Information

The dashboard is built on a realistic **Sales Financial Dataset** containing **1,500 records** of transaction logs with the following columns:
* **Order Details**: Order ID, Order Date, Ship Date, Ship Mode
* **Customer Info**: Customer ID, Segment (Consumer, Corporate, Home Office)
* **Geography**: Country (USA), State, City, Region (East, West, Central, South)
* **Product Details**: Product ID, Category (Furniture, Office Supplies, Technology), Sub-Category, Product Name
* **Financials**: Sales, Quantity, Discount, Profit, Year, Month

---

## Tools Used

* **Power BI Desktop**: Dashboard design, modeling, and DAX implementation.
* **Python (Pandas, Matplotlib, Seaborn)**: Realistic data synthesis, high-resolution dashboard mock rendering, and visual quality assurance.
* **python-pptx**: Automated PowerPoint slide generation matching corporate styles.
* **Pillow**: PDF report compiling.

---

## Dashboard KPIs

The dashboard calculates the following key business metrics dynamically (re-calculating instantly when slicers are applied):
1. **Total Sales**: **$1,134,212.70** — Total gross revenue generated.
2. **Total Profit**: **$219,339.05** — Combined net profit across all lines.
3. **Total Orders**: **1,500** — Distinct number of orders processed.
4. **Average Profit**: **$146.23** — Net profit per item ordered.
5. **Profit Margin**: **19.3%** — Overall conversion efficiency of sales to profit.

### DAX Measures Used
```dax
Total Sales = SUM(Sales_Financial[Sales])
Total Profit = SUM(Sales_Financial[Profit])
Total Orders = DISTINCTCOUNT(Sales_Financial[Order ID])
Average Profit = AVERAGE(Sales_Financial[Profit])
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
```

---

## Visualizations Included

* **Sales Trend (Line Chart)**: Tracks sales fluctuations month-over-month and year-over-year.
* **Profit by Category (Bar Chart)**: Compares net profit contributions across *Technology*, *Office Supplies*, and *Furniture*.
* **Sales by Region (Donut Chart)**: Visualizes regional market share across *East*, *West*, *Central*, and *South*.
* **Top 10 Products (Horizontal Bar)**: Displays the bestselling inventory lines by total sales volume.

---

## Interactivity Features

The dashboard includes a dedicated **Slicer Panel** to filter the entire visual report on the fly:
* **Year**: Drill down into specific fiscal years (2023, 2024, 2025, 2026).
* **Region**: Focus on specific market territories.
* **Category**: Filter by product categories.
* **Segment**: Focus on Consumer, Corporate, or Home Office demographics.

*Note: All visuals are fully cross-filtered, meaning clicking a specific region in the donut chart updates the sales trends, category profit, and top products visuals instantly for that region.*

---

## Key Business Insights & Outcomes

1. **High Margin Drivers**: *Technology* products carry the highest average profit margins (approx 35%), making them prime candidates for upselling.
2. **Geographical Performance**: The *East* and *West* regions account for more than 60% of total sales. Targeted marketing campaigns are recommended to address the lower-volume *South* region.
3. **Furniture Margin Contraction**: *Furniture* experiences significant margin erosion due to high distribution overhead and frequent discounting. Recommending a discount cap of 15% on furniture tables and chairs.
