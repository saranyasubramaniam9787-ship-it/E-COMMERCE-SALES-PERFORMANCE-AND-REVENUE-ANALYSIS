**E-Commerce Sales Performance and Revenue Analysis**

📖 **Table of Contents**

- Project Overview
- Data Source
- Tools & Technologies
- Data Cleaning & Preparation
- Exploratory Data Analysis (EDA)
- Key Insights
- Recommendations
- How to Use


**Project Overview**

This project transforms raw transactional and master data into meaningful business insights to support strategic decision-making for an e-commerce business.

The analysis evaluates customer demographics, product pricing, discount structures, revenue, and profitability to assess overall business performance and identify opportunities for growth and optimization.

**Key Objectives**

- Analyze customer loyalty levels and their impact on revenue
- Identify high-value customers based on purchasing behavior
- Evaluate product performance by category and inventory status
- Conduct regional performance analysis
- Perform sales trend analysis based on order date and quantity sold
- Measure revenue and profit/loss by product category
- Assess the impact of discounts on profitability
- Evaluate payment type preferences
- Forecast future revenue for strategic planning

**Data Source**

Dataset: E-Commerce Sales Dataset

- **Records:** 2,000+ sales transactions
- **Tables:** Customer, Product, Store, Sales
- **File Format:** Excel (.xlsx)
- **Dataset Size:** ~2 MB
  **Source**-The dataset used in this project was provided as part of an academic exercise for learning data analysis.

**Description**

The dataset represents a comprehensive e-commerce sales environment consisting of four relational tables:

- Customer
- Product
- Store
- Sales

These tables capture customer demographics, product details, store information, and transactional sales records.

**Customer Table**

- Customer_ID – Unique identifier for each customer
- Name – Customer full name
- Age – Age of the customer
- Gender – Gender of the customer
- City – Customer city
- State – Customer state
- Loyalty_Level – Loyalty tier (Gold, Silver, Bronze, Platinum)


**Product Table**

- Product_ID – Unique product identifier
- Product_Name – Product name
- Category – Main product category
- Sub_Category – Detailed product classification
- Brand – Brand name
- Cost – Product cost price
- Stock – Inventory quantity


**Store Table**

- Store_ID – Unique store identifier
- Store_Name – Store name
- Region – Store geographic region
- City – Store city
- Store_Type – Type of store (flagship, outlet)


**Sales Table**

- Sales_ID – Unique sales transaction ID
- Order_Date – Date of order
- Customer_ID – Customer identifier
- Product_ID – Product identifier
- Store_ID – Store identifier
- Region – Sales region
- Quantity – Units sold
- Product_Cost – Cost per unit
- Unit_Price – Price per unit
- Discount – Discount applied
- Revenue – Total sales revenue
- Total_Amount – Final amount after discount
- Payment_Type – Payment method (Cash, Card, Online)


**Tools & Technologies**

- Excel – Data Cleaning & Analysis
- Excel Data Analysis ToolPak – Statistical Analysis

**Data Cleaning & Preparation**

**Data Import**

- Imported dataset using Excel **Get Data → From File → Excel Workbook**
- Loaded all worksheets: Customer, Product, Store, Sales

**Customer Table Cleaning**

- Standardized **Customer_ID**
- Removed duplicates
- Cleaned hidden characters using CLEAN and TRIM
- Standardized customer names
- Created **Age Group segmentation**

Example formula:

```excel
=IFS([@Age]>=50,"Senior",[@Age]>=30,"Adult",[@Age]>=18,"Young")
```

**Loyalty Level Imputation**

```excel
=IF(ISBLANK([@[Loyalty_Level]]),
IF(COUNTIF(Sales_Fact[Customer_ID],[@[Customer_ID]])>5,"Platinum",
IF(COUNTIF(Sales_Fact[Customer_ID],[@[Customer_ID]])>=3,"Gold",
IF(COUNTIF(Sales_Fact[Customer_ID],[@[Customer_ID]])>=2,"Silver",""))),
[@[Loyalty_Level]])
```

**Product Table Cleaning**

- Standardized product IDs
- Cleaned category fields
- Standardized brand capitalization
- Filled missing product costs using sub-category averages

```excel
=IF(ISBLANK([@Cost]),AVERAGEIF([Sub_Category],[@[Sub_Category]],[Cost]),[@Cost])
```

**Store Table Cleaning**

- Cleaned Store_ID, Store_Name, Region, City
- Standardized text formatting using PROPER


**Sales Table Cleaning**

Quantity Imputation

```excel
=IF(ISBLANK([@Quantity]),AVERAGE([Quantity]),[@Quantity])
```

Revenue Calculation

```excel
=[@Quantity]*[@[Unit_Price]]
```

Total Amount

```excel
=[@Revenue]-([@Revenue]*[@Discount])
```

Profit Calculation

```excel
=[@[Total Amount]]-([@[Product_cost]]*[@Quantity])
```

Additional cleaning steps

- Integrated region data using VLOOKUP
- Standardized date formats
- Ensured proper data types for analysis


**Exploratory Data Analysis (EDA)**

**Revenue Statistics**

- Mean: ₹513.99
- Median: ₹522.43
- Mode: ₹516.59
- Standard Deviation: ₹282.09
- Minimum: ₹20.09
- Maximum: ₹999.89
- Total Revenue: ₹10,27,977.36
- Transactions: 2,000
- Skewness: -0.04
- Kurtosis: -1.19


**Key Analysis Questions**

**Customer Analysis**

- Impact of loyalty levels on revenue
- High-value customer identification
- Demographic purchasing behavior

**Product Performance**

- Revenue and profit by category
- Inventory vs sales performance
- Overstocked and underperforming products

**Regional Analysis**

- Regional sales performance
- Store type impact on revenue
- Expansion opportunities

**Profitability Analysis**

- Discount impact on margins
- Loss-making products

**Trend Analysis**

- Sales trends from 2023–2025
- Seasonal demand patterns
- 6-month revenue forecast


**Visualization Highlights**

- Category-wise revenue vs profit charts
- Product sales vs inventory charts
- Regional sales distribution
- Discount vs profit analysis
- Time series forecast charts


**Key Insights**

- Revenue distribution is balanced with minimal skewness.
- Computers and Electronics generate the highest revenue.
- Appliances category shows losses due to pricing below cost.
- North region dominates sales performance.
- East region significantly underperforms.
- Aggressive discounting negatively impacts profitability.
- Accessories category shows overstocking.
- Platinum and Gold customers generate the highest revenue.
- Revenue forecast shows moderate growth.


**Recommendations**

**Pricing Optimization**

- Ensure unit price exceeds product cost
- Implement dynamic pricing strategies
- Control excessive discounting

**Inventory Management**

- Reduce overstock in Accessories
- Implement demand-driven restocking
- Monitor stock turnover ratios

**Regional Expansion**

- Target marketing for East region
- Replicate North region strategies
- Optimize store formats

**Customer Retention**

- Strengthen loyalty programs
- Create personalized promotions
- Run win-back campaigns

**Discount Optimization**

- Apply targeted discounts
- Avoid blanket discount strategies
- Monitor profit impact of promotions

**Payment Optimization**

- Improve preferred payment experiences
- Promote cost-effective payment methods

**Forecast Planning**

- Use forecasts for procurement planning
- Prepare for high-demand seasons
  
**Key Metrics Calculated**

```excel
Total Sold Quantity: =SUM(G2:G2001)
Total Revenue: =SUM(K2:K2001)
Total Profit: =SUMIF(M2:M2001,">0")
Total Loss: =SUMIF(M2:M2001,"<0")
Profit Margin %: =([@[Profit/Loss]]/[@Revenue])*100
```
**How to Use**

**Prerequisites**

- Microsoft Excel (2016 or later)

**Steps to Run**

**Clone the Repository**

```bash
git clone https://github.com/saranyasubramaniam9787-ship-it/E-COMMERCE-SALES-PERFORMANCE-AND-REVENUE-ANALYSIS.git
cd ecommerce-sales-analysis
```

**Data Files Setup**

- Place the **E-Commerce_Sales_Dataset.xlsx** file in the `/data` folder.
- Ensure all worksheets (Customer, Product, Store, Sales) are available.

**Excel Analysis**

- Open **Ecommerce_Analysis_Workbook.xlsx**
- Enable macros if prompted
- Navigate through the following sheets:
  - Raw Data
  - Cleaned Data
  - Analysis
  - Visualizations

**Output**

- Cleaned dataset in `/output`
- Statistical summary reports
- Excel charts and visual analysis
- Dashboard insights

  **Dashboard Preview**

**Category-wise Revenue & Profit**

- Computers and Electronics lead in revenue
- Appliances show negative profit

**Regional Performance**

- North region: Highest sales
- East region: Lowest performance

**Discount vs Profit Analysis**

- Higher discounts reduce profit margins
- Strategic discounting recommended

**Revenue Forecast (Next 6 Months)**

- Gradual growth expected
- Seasonal fluctuations present
- December projected as peak revenue month
