Maven Pizza Sales Analysis Report

Introduction

The Maven Pizza Sales Analysis report provides a detailed examination of sales performance, order trends, and customer behavior insights derived from the dataset. The objective is to analyze revenue, orders, and pizza-specific metrics to identify trends, improve decision-making, and optimize operations.



Data Preparation Steps

Uploading the TablesAll four tables (‘Orders,’ ‘Order_Details,’ ‘Pizzas,’ and ‘Pizza_Types’) were uploaded into Power BI.

Adjusting HeadersThe header for the ‘Pizza_Types’ table was not set correctly. The option ‘Set First Row as Header’ was used to correct it.

Column ExtractionFrom the ‘Orders’ table, the columns for month, quarter, and day were extracted to enable time-based analysis.

Key Identification

Orders Table: Primary Key (‘Order_ID’)

Pizza_Types Table: Primary Key (‘Pizza_Type_ID’)

Order_Details Table: Primary Key (‘Order_Details_ID’), Foreign Keys (‘Order_ID,’ ‘Pizza_ID’)

Pizzas Table: Primary Key (‘Pizza_ID’), Foreign Key (‘Pizza_Type_ID’)

Data Modeling

Relationship 1: Orders (Order_ID) ↔ Order_Details (Order_ID) [One-to-Many]

Relationship 2: Pizzas (Pizza_Type_ID) ↔ Pizza_Types (Pizza_Type_ID) [One-to-Many]

Relationship 3: Pizzas (Pizza_ID) ↔ Order_Details (Pizza_ID) [One-to-Many]

Measures and Calculations

Measures

Total OrdersFormula: Total_Orders = COUNT(Orders[Order_ID])Result: 21,000 unique orders

Total Revenue

A calculated column was created using the RELATED function to fetch the ‘Price’ column from the ‘Pizzas’ table.

Total Price = Quantity × Price

Formula: Total_Revenue = SUM(Order_Details[Total_Price])Result: $817.86K

Average Order Metrics

Average Order per Month: Total Orders / DISTINCTCOUNT(Month) = 1.8K

Average Order per Quarter: Total Orders / DISTINCTCOUNT(Quarter) = 5.3K

Average Order per Day: Total Orders / DISTINCTCOUNT(Day) = 59.6

Average Order Value (AOV): Total Revenue / Total Orders = $38.3

Revenue Metrics

Average Revenue per Day: Total Revenue / DISTINCTCOUNT(Day) = $2.3K

Average Revenue per Month: Total Revenue / DISTINCTCOUNT(Month) = $68.2K

Average Revenue per Quarter: Total Revenue / DISTINCTCOUNT(Quarter) = $204.5K

Visualizations

Sales Dashboard

Cards Created

Total Orders: 21,000

Total Revenue: $817.86K

Average Order Value (AOV): $38.3

Average Revenue per Day: $2.3K

Average Revenue per Month: $68.2K

Average Revenue per Quarter: $204.5K

Visuals Created

Total Orders by Time

By Month: July is the highest.

By Quarter: Q2 is the highest.

By Day: Friday is the highest.

Total Revenue by Time

By Month: July is the highest.

By Quarter: Q2 is the highest.

By Day: Friday is the highest.

Pizzas Table Analysis

Cards Created

Top Pizza by Revenue: Thai Chicken

Bottom Pizza by Revenue: Brie Carre

Top Pizza by Orders: Classic Deluxe

Bottom Pizza by Orders: Brie Carre

Visuals Created

Pizza Category Revenue Distribution (Bar Chart):

Highest: Classic

Lowest: Veggie

Pizza Category Order Distribution (Pie Chart):

Highest: Classic

Lowest: Chicken

Top 7 Pizzas by Revenue (Bar Chart)

Top 7 Pizzas by Orders (Bar Chart)

Insights and Recommendations

Top Performers

Thai Chicken is the most profitable pizza, while Classic Deluxe is the most ordered.

Focus marketing campaigns around these top-performing pizzas.

Low Performers

Brie Carre consistently underperforms in both revenue and orders. Consider revisiting pricing, marketing, or recipe improvements.

Time-Based Trends

Q2 and July exhibit peak sales. Promotions during these periods can amplify revenue.

Fridays are the busiest days; staffing and inventory should be optimized accordingly.

Category Insights

Classic pizzas dominate both revenue and orders. Expanding this category with new options could further boost sales.

Conclusion

The analysis provides actionable insights to enhance revenue, order volume, and customer satisfaction. By leveraging the identified trends, the pizza business can make informed decisions to optimize operations and drive growth.

