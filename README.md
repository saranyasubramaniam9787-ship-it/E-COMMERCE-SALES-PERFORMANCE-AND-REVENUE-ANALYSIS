# E-COMMERCE SALES PERFORMANCE AND REVENUE ANALYSIS
## Brief Description of the Project

  The objective of this project is to transform raw transactional and master data into meaningful business insights for strategic decision-making.The analysis uses customer demographics, product cost and pricing, discount structures, revenue, total sales amount, and profit or loss.This study evaluates business performance and identifies growth and optimization opportunities.

## Project Focus Areas

- Customer Analysis: Loyalty levels and high-value customer identification
- Product Performance: Category performance, inventory status, and regional trends
- Sales and Revenue: Trend analysis, profit/loss measurement, and discount impact assessment
- Operational Insights: Payment preferences and store performance


## Installation Instructions
- Install Microsoft Excel (2016 or later recommended)
- Download or clone this repository
- Open the Excel file containing the cleaned dataset and dashboard
- Enable editing and formulas if prompted
- Refresh pivot tables and charts to view updated results

## Data Sources

- Customer Table: Customer_ID, Name, Age, Gender, City, State, Loyalty_Level
- Product Table: Product_ID, Product_Name, Category, Sub_Category, Brand, Cost, Stock
- Store Table: Store_ID, Store_Name, Region, City, Store_Type
- Sales Table: Sales_ID, Order_Date, Customer_ID, Product_ID, Store_ID, Quantity, Unit_Price, Discount, Revenue, Payment_Type

## Code Structure
The project is organized within an Excel Workbook structure, utilizing formulas and data transformation logic rather than traditional scripting. The logic flow is as follows:
/README.md
/data
    ├── Customer_Raw.xlsx
    ├── Product_Raw.xlsx
    ├── Store_Raw.xlsx
    └── Sales_Raw.xlsx
/src (or /sheets)
    ├── 1_Data_Cleaning       # Standardization of IDs, Names, Dates
    ├── 2_Data_Transformation # Imputation of missing values, Calculated Columns
    ├── 3_Analysis            # Pivot Tables, Statistical Summaries
    └── 4_Dashboard           # Visualizations and Key Metrics
    
## Key Transformation Logic
### Data Cleaning

- Used CLEAN(), TRIM(), and PROPER() to standardize IDs, Names, and Categories

### Imputation

- Missing values in Cost, Stock, Quantity, and Discount filled using category-level averages (AVERAGEIF)

### Calculations

- Revenue = Quantity * Unit_Price
- Total Amount = Revenue - (Revenue * Discount)
- Profit = Total Amount - (Product Cost * Quantity)

### Lookup

- Used VLOOKUP to merge Product Cost and Store Region into the Sales table

### Results and Evaluation

- Total observations processed: 2,000

### Statistical Summary

- Total Revenue: ₹10,27,977.36
- Mean Revenue per Transaction: ₹513.99
- Revenue Range: ₹20.09 (Min) to ₹999.89 (Max)
- Distribution: Symmetrical (Skewness = -0.04)

## Key Insights
### Regional Performance

- North region records the highest sales volume
- East region has the lowest sales and needs focused strategy

### Product Categories

- Computers are the highest-selling products
- Appliances have high stock but incur losses (Unit Price < Product Cost)
- Accessories have high inventory but low sales quantity

### Customer Loyalty

- Higher-tier loyalty groups contribute a major share of revenue

### Discount Impact

- Excessive discounting on low-margin products reduces profitability

## Forecast

-- Time-series forecasting indicates a gradual and consistent increase in revenue

## Future Work

- Pricing Optimization: Ensure Unit Price exceeds Product Cost in Appliances
- Inventory Management: Align stock levels with demand in Accessories
- Regional Strategy: Focus marketing efforts in the East region
- Discount Strategy: Limit discounts on low-margin items and clear high-stock inventory
- Demand Planning: Use forecast trends to stabilize monthly earnings

## Results of the Project

- Identified top and low-performing products based on sales and profit
- Analyzed region-wise and time-based sales trends
- Evaluated customer segments based on age and loyalty level
- Calculated Total Sales, Total Revenue, Profit, and Profit Margin
- Built Pivot Tables and Pivot Charts
- Designed dashboards for decision-making

## Challenges Faced

- Data cleaning due to missing values and inconsistent formats
- Formula validation for profit and margin
- Designing Pivot Tables with multiple filters
- Ensuring KPI accuracy with large datasets
- Creating simple and clear visual presentations

## Acknowledgments / References

- Dataset provided for E-Commerce Sales Performance and Revenue Analysis
- Analysis based on standard Excel data cleaning and statistical practices

## License

- This project is open-source and available under the MIT License
