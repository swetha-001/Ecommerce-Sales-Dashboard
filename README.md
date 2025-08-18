# Ecommerce-Sales-Analysis-Dashboard (Power BI)

 ## Project Overview

The objective of this project was to analyze an E-commerce store’s sales performance and measure target achievements across categories, states and time periods. The challenge was to handle different granularity levels in the dataset (daily sales vs. monthly targets), build a reliable data model and create an interactive Power BI dashboard to derive actionable insights.

## Data Overview

The dataset consists of three tables:
1. List of Orders
     * Columns: Order ID, Order Date, Customer Name, State, City
2. Order Details
     * Columns: Order ID, Amount, Profit, Quantity, Category, Sub-Category
3. Sales Target
     * Columns: Month of Order Date, Category, Target

## Data Cleaning & Data Model Creation

- Established a 1-to-many relationship between List of Orders[Order ID] and Order Details[Order ID].
- Faced a many-to-many issue between Order Date (daily) and Sales Target (monthly).
- Solution Implemented using DAX :
    * Created a Calendar Table using DAX with one row per date.
    * Added a [Month Start] column in the Sales Target table for exact match with Calendar.
    * Built a Month Bridge Table with unique rows per month, enabling a proper one-to-many relationship.
    * Ensured all tables connect through this bridge for accurate time-based reporting.
<img width="1240" height="609" alt="image" src="https://github.com/user-attachments/assets/59d4a0b5-8e6a-4a1f-b1bc-fba547210e17" />
 
## Analysis & Dashboard Features

The dashboard was designed with 3 interactive pages containing:

- KPI Cards: Total Sales, Total Profit, Total Orders, Sales vs Target, Avg Profit per Order
- Category Analysis: Sales by Category, Profit by Category, Profit Margin by Category
- Time Analysis: Sales by Month, Sales vs Target by Month
- Customer Analysis: Top 10 Customers by Sales, Profit, and Purchase Frequency
- Geographical Analysis: Average Profit by State
- Interactivity:
    * Slicers for Date, Category, Region
    * Navigation bar with buttons for page switching
    * Bookmarks to toggle views (e.g show/hide filters panel)
<img width="1188" height="666" alt="image" src="https://github.com/user-attachments/assets/b8d3df27-ab29-4a21-b152-0ce058367bc3" />
<img width="1188" height="662" alt="image" src="https://github.com/user-attachments/assets/60948366-06f6-431a-9a86-f5d7b1982394" />
<img width="1178" height="661" alt="image" src="https://github.com/user-attachments/assets/15e8284b-b04f-4f80-99fa-3a08c52dc838" />


## Insights Generated

- `Clothing` emerged as the `most profitable` category with a profit margin of `8.03`, while `Furniture` underperformed with just `1.81`.
- `Punjab` ranked among the top five states in order volume but showed a negative average profit (-10 Loss), highlighting a region for immediate improvement.
- In July 2018, sales reached 12,966 against a target of 33,800, with the lowest Target Achievement % of `38.36%`, revealing major target-setting/achievement gaps.
- `Electronics` recorded the highest `sales volume`, though `Clothing` remained the most `profitable`.

# Business Impact

The dashboard can help the store identify underperforming regions and categories, uncovering a profitability gap of 6.22 points between Clothing and Furniture.
By tracking target achievement rates and highlighting loss-making states like Punjab, the store can reallocate resources and optimize strategies, potentially improving overall profitability by 10-15%.
