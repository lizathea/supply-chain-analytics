# supply-chain-analytics
Supply Chain Operations and Inventory Analytics using Power BI
# Supply Chain Operations & Inventory Analytics

**Tools:** Microsoft Power BI, Power Query, DAX  
**Reporting Period:** January–December 2024  
**Project Type:** Data Analytics and Business Intelligence

## 1. Project Overview

This project analyzes supply chain operations and inventory performance using Power BI. The goal is to transform operational data into business insights that support inventory planning, sales performance monitoring, and demand forecasting.

The dashboard provides an overview of sales performance, regional and warehouse comparisons, supplier-associated sales volume, inventory levels, reorder points, and demand forecasts.

The analysis focuses on identifying performance patterns, highlighting areas that require further investigation, and developing data-driven recommendations.

## 2. Business Problem

Businesses need to balance product availability, inventory investment, and demand planning. Poor inventory decisions can contribute to excess stock or insufficient stock, while inaccurate forecasts can make replenishment planning more difficult.

This project explores the available data to answer the following questions:

1. How do sales volumes change over time?
2. Which regions and warehouses contribute the most to total units sold?
3. Which suppliers are associated with the highest and lowest sales volumes?
4. How do recorded inventory levels compare with reorder points?
5. How closely do demand forecasts match actual units sold?
6. Which products and operational areas require further investigation?

## 3. Dataset Overview

The dataset contains 91,251 records covering the 2024 calendar year.

| Attribute | Reported coverage |
|---|---:|
| Records | 91,251 |
| Reporting period | January–December 2024 |
| SKUs | 50 |
| Warehouses | 5 |
| Suppliers | 10 |
| Regions | 4 |

### Main data fields

- `Date`: Reporting date.
- `SKU_ID`: Product identifier.
- `Warehouse_ID`: Warehouse identifier.
- `Supplier_ID`: Associated supplier identifier.
- `Region`: Region associated with the record.
- `Units_Sold`: Units sold.
- `Inventory_Level`: Recorded inventory level.
- `Supplier_Lead_Time_Days`: Supplier lead time in days.
- `Reorder_Point`: Recorded inventory reorder threshold.
- `Order_Quantity`: Recorded order quantity.
- `Unit_Cost`: Unit cost.
- `Unit_Price`: Unit price.
- `Promotion_Flag`: Promotion indicator.
- `Demand_Forecast`: Forecast demand.

The original `Stockout_Flag` column contained only zeros and was removed during data preparation. Consequently, this project does not calculate confirmed stockout rates from that field.

## 4. Tools and Technologies

### Microsoft Power BI
Used to create the report, develop KPI measures, compare business performance, and build interactive visualizations.

### Power Query
Used for data preparation and transformation.

### DAX
Used to calculate business metrics and analytical measures.

SQL and Python are not included as implemented tools unless they are subsequently used in the project.

## 5. Data Preparation and Validation

The preparation process should document the following checks:

1. Verify column names and data types.
2. Confirm the expected granularity of each record.
3. Validate that `Date + SKU_ID + Warehouse_ID` is unique.
4. Check missing values and unexpected values.
5. Confirm that units sold, inventory levels, costs, and prices are interpreted correctly.
6. Verify that revenue and gross profit calculations match their intended definitions.
7. Check the aggregation of daily inventory snapshots.
8. Validate the forecast accuracy calculation.
9. Document the removal of `Stockout_Flag` because it contained only zeros.

These checks help ensure that the dashboard presents meaningful results rather than misleading metrics.

## 6. Dashboard Overview

The Power BI dashboard includes the following analytical components.

### Executive KPIs
- Total Units Sold
- Total Revenue
- Gross Profit
- Profit Margin
- Forecast Accuracy

### Sales Performance
- Monthly units sold trend
- Units sold by region
- Units sold by warehouse
- Units sold associated with suppliers
- Top 10 SKUs by units sold

### Inventory Analysis
- Inventory levels compared with reorder points
- Average inventory by SKU
- Potential inventory risk based on reorder thresholds

### Demand Forecasting
- Actual units sold versus demand forecast
- Forecast error analysis
- Identification of products with larger forecast deviations

## 7. Key Findings

### 7.1 Overall Performance

The dashboard reports:

| KPI | Reported result |
|---|---:|
| Total units sold | 1,829,979 |
| Total revenue | 33,426,337 |
| Gross profit | 11,088,201 |
| Profit margin | 33.2% |
| Average supplier lead time | 8 days |
| Average inventory level | 471.52 |
| Forecast accuracy | 99.9% |

These values are dashboard-reported results and should be validated against the underlying DAX definitions before publication.

### 7.2 Monthly Sales Performance

March recorded the highest monthly sales volume, with 231,596 units sold.

September recorded the lowest monthly sales volume, with 76,304 units sold.

This difference indicates a substantial variation in recorded monthly sales volume. Further investigation is needed to determine whether it reflects seasonality, promotions, product availability, or other factors.

### 7.3 Regional Performance

The dashboard shows a relatively even distribution of units sold across the four regions.

The displayed regional totals are approximately:
- East: 460,000 units
- North: 460,000 units
- South: 457,000 units
- West: 453,000 units

The small differences suggest that regional sales volumes are relatively close. The exact totals should be verified before presenting a definitive ranking.

### 7.4 Warehouse Performance

The reported warehouse sales volumes are:

| Warehouse | Units sold |
|---|---:|
| WH_1 | 366,902 |
| WH_3 | 366,110 |
| WH_5 | 365,114 |

These three warehouses have relatively similar sales volumes. WH_1 recorded the highest of the three figures reported, while WH_5 recorded the lowest.

Further investigation should compare inventory risk, demand forecasts, and sales trends before recommending operational changes.

### 7.5 Supplier-Associated Sales

The dashboard reports the following figures:

| Supplier | Units sold associated with supplier |
|---|---:|
| SUP_7 | 248,830 |
| SUP_8 | 205,407 |
| SUP_9 | 117,259 |

These figures describe sales associated with each supplier in the dataset. They do not establish the actual quantities supplied or supplier delivery performance.

### 7.6 Inventory and Reorder Points

The dashboard compares inventory levels with reorder points across warehouses.

The current visualization requires validation to confirm that both measures use appropriate aggregations. Since the dataset contains daily inventory records, summing inventory snapshots across multiple dates may overstate the inventory represented.

The next step is to calculate inventory risk using clearly defined date-level records and compare inventory levels against reorder points.

### 7.7 Demand Forecast Accuracy

The dashboard reports forecast accuracy of 99.9%.

Before drawing a conclusion about forecast quality, the calculation must be validated using the actual units sold and demand forecast fields. Forecast error should also be examined by SKU and date to identify where the largest differences occur.

## 8. Business Recommendations

### Recommendation 1: Investigate the September Sales Decline

Compare September sales with other months by SKU, region, warehouse, and promotion status.

The objective is to identify which products or locations contributed most to the decline. The available results do not yet establish the cause.

### Recommendation 2: Monitor Inventory Risk at WH_3

WH_3 recorded 366,110 units sold, making it one of the higher-volume warehouses in the reported results.

Review its inventory levels against reorder points and demand patterns. If the analysis confirms that inventory frequently approaches or falls below reorder thresholds, consider reviewing replenishment policies.

### Recommendation 3: Review Forecast Errors

Validate the reported forecast accuracy and calculate forecast errors by SKU and date.

Focus on products with the largest absolute errors and investigate whether the differences coincide with promotions or changes in sales patterns.

### Recommendation 4: Improve Inventory Reporting

Use an appropriate inventory snapshot for current inventory value and clearly defined date-level measures for historical analysis.

This will help avoid counting the same stock repeatedly across daily records.

### Recommendation 5: Separate Supplier Sales from Supplier Performance

Use the current dataset to compare sales associated with suppliers. To evaluate actual supplier performance, obtain appropriate procurement and delivery measures, if available, such as actual delivery dates and ordered versus received quantities.

## 9. Limitations

- The original stockout indicator contained only zeros, so confirmed stockout rates cannot be calculated from that field.
- Sales volume alone does not establish why sales changed.
- Sales associated with a supplier do not measure the quantity supplied or supplier reliability.
- Inventory measures must account for the daily snapshot structure.
- The reported forecast accuracy requires formula validation.
- The dataset's source and the definitions of all business fields should be documented before making stronger operational conclusions.

## 10. Conclusion

This project demonstrates how Power BI can be used to explore sales performance, inventory indicators, supplier-associated sales, and demand forecasting.

The dashboard provides a starting point for operational decision-making. Further validation of inventory calculations and forecast metrics will improve the reliability of the findings and support more specific business recommendations.

## 11. Repository Structure

- `powerbi/`: Power BI report file.
- `screenshots/`: Dashboard screenshots.
- `docs/`: Case study and supporting documentation.
- `data/`: Permitted sample data or dataset documentation.

## 12. How to Use

1. Download the Power BI report from this repository.
2. Open the `.pbix` file using Power BI Desktop.
3. Refresh the data if you have access to the required source files.
4. Explore the report using the available slicers and visualizations.

Only publish datasets and report content that you are authorized to share.
