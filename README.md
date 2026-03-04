# E-COMMERCE SALES PERFORMANCE AND REVENUE ANALYSIS
##Brief Description of the Project
The primary objective of this analysis is to transform raw transactional and master data into meaningful business insights that support strategic decision-making. By leveraging customer demographics, product cost and pricing, discount structures, revenue, total sales amount, and profit or loss, this study assesses overall business performance and identifies opportunities for growth and optimization.
The project focuses on four core areas:
Customer Analysis: Loyalty levels and high-value customer identification.
Product Performance: Category performance, inventory status, and regional trends.
Sales and Revenue: Trend analysis, profit/loss measurement, and discount impact assessment.
Operational Insights: Payment preferences and store performance.

--
##Installation Instructions
This project is built using Microsoft Excel for data import, cleaning, transformation, and analysis. No additional software installation is required beyond Microsoft Excel.
Prerequisites:
Microsoft Excel (2016 or later recommended for Power Query/Get Data features).
The provided E-Commerce Sales Dataset (.xlsx or .csv files).
--
##Data Sources
The dataset represents an e-commerce sales environment and consists of four primary tables:
Customer Table: Contains customer demographics (Customer_ID, Name, Age, Gender, City, State, Loyalty_Level).
Product Table: Contains product details (Product_ID, Product_Name, Category, Sub_Category, Brand, Cost, Stock).
Store Table: Contains store information (Store_ID, Store_Name, Region, City, Store_Type).
Sales Table: Contains transactional records (Sales_ID, Order_Date, Customer_ID, Product_ID, Store_ID, Quantity, Unit_Price, Discount, Revenue, Payment_Type).
--
##Key Transformation Logic:
Standardization: Used CLEAN(), TRIM(), and PROPER() to fix formatting in IDs, Names, and Categories.
Imputation: Missing values in Cost, Stock, Quantity, and Discount were filled using category-level averages (AVERAGEIF).
Calculations:
Revenue = Quantity * Unit_Price
Total Amount = Revenue - (Revenue * Discount)
Profit = Total Amount - (Product Cost * Quantity)
Lookup: VLOOKUP used to merge Product Cost and Store Region into the Sales table.

--

##Results and Evaluation
The analysis processed 2,000 observations with the following key findings:
Statistical Summary:
Total Revenue: ₹10,27,977.36
Mean Revenue per Transaction: ₹513.99
Revenue Range: ₹20.09 (Min) to ₹999.89 (Max)
Distribution: Symmetrical (Skewness: -0.04), indicating stable revenue behavior.

--


##Key Insights:
Regional Performance: The North region records the highest sales volume, while the East region has the lowest, indicating a need for focused strategic improvement in the East.
##Product Categories:
Computers are the highest-selling products.
Appliances show high stock levels but incur losses (Unit Price < Product Cost).
Accessories have high inventory but low sales quantity (overstocking).
Customer Loyalty: Higher-tier loyalty groups contribute a substantial share of revenue.
Discount Impact: Excessive discounting on low-margin products reduces profitability.

--
##Forecast:
Time-series forecasting projects a gradual and consistent increase in revenue over the horizon, with manageable uncertainty.

--
##Future Work
To improve future business performance, the following strategies are recommended:
Pricing Optimization: Ensure Unit Price exceeds Product Cost, especially in the Appliances category.
Inventory Management: Align stock levels with demand to reduce carrying costs in the Accessories category.
Regional Strategy: Implement focused marketing efforts in the East region.
Discount Strategy: Apply differentiated discount policies; limit discounts on low-margin items and use promotions to clear high-stock inventory.
Demand Planning: Use forecasted trends to stabilize monthly earnings and reduce dependency on reactive discounting.
--

Results of the Project
• Identified top-performing and low-performing products based on sales and profit.
• Analyzed region-wise and time-based sales trends to understand market demand.
• Evaluated customer segments based on age group and loyalty level.
• Calculated key metrics including Total Sales, Total Revenue, Profit, and Profit Margin.
• Developed dynamic Pivot Tables and Pivot Charts for quick comparison and drill-down analysis.
• Created clear visual summaries and dashboards to help stakeholders understand business performance and improve pricing and product strategies.

Challenges Faced
• Data cleaning was difficult due to missing values, inconsistent formats, and calculation errors.
• Formula validation for profit, margin, and cost per unit required careful verification.
• Designing Pivot Tables with multiple filters (product, region, and date) required proper data structuring.
• Ensuring accuracy while handling large datasets and multiple KPIs was time-consuming.
• Presenting insights in a simple and understandable visual format was a key challenge.


##Acknowledgments/References
Dataset provided for E-Commerce Sales Performance and Revenue Analysis.
Analysis methodology based on standard data cleaning and statistical evaluation practices using Microsoft Excel.

--
##License
This project is open-source and available under the MIT License.




Skills
Advanced Excel · Pivot Tables · Pivot Charts · VLOOKUP · INDEX & MATCH · Excel Dashboards · Data Analysis · Data Cleaning
