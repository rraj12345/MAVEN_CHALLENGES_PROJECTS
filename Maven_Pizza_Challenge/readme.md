# Maven Pizza Sales Analysis  

## Introduction  
The Maven Pizza Sales Analysis project provides a comprehensive examination of sales performance, order trends, and customer behavior. The objective is to analyze revenue, orders, and pizza-specific metrics to identify trends, improve decision-making, and optimize operations for a pizzeria.  

---

## Pre-Analysis Documentation  

### Goals, Metrics, and Level of Detail  

| **Business Goal**                  | **Metrics**                      | **Level of Detail**                                   |  
|------------------------------------|-----------------------------------|------------------------------------------------------|  
| **Increase Revenue**               | Total Revenue, MOM Revenue change | Date (Quarter, Month, Day), Pizza type, category, size |  
| **Increase Orders**                | Total Orders, MOM Sales change   | Date (Quarter, Month, Day, Time), Pizza type, category, size |  
| **Improve Productivity**           | Total Orders                     | Date (Quarter, Month, Day) - Peak Periods            |  
| **Understand Customers' Behavior** | Average Order Value (AOV)        | Date (Quarter, Month)                                |  
| **Best/Worst Selling Pizzas**      | Total Orders, Total Revenue      | Pizza type, category, size                           |  

---

## Data Preparation Steps  

1. **Uploading Tables**: Datasets (‘Orders,’ ‘Order_Details,’ ‘Pizzas,’ and ‘Pizza_Types’) uploaded to Power BI.  
2. **Adjusting Headers**: Corrected headers for the ‘Pizza_Types’ table.  
3. **Column Extraction**: Extracted Month, Quarter, and Day columns from the ‘Orders’ table for time-based analysis.  

### Key Identification  

- **Orders Table**: Primary Key (`Order_ID`)  
- **Pizza_Types Table**: Primary Key (`Pizza_Type_ID`)  
- **Order_Details Table**: Primary Key (`Order_Details_ID`), Foreign Keys (`Order_ID`, `Pizza_ID`)  
- **Pizzas Table**: Primary Key (`Pizza_ID`), Foreign Key (`Pizza_Type_ID`)  

---

## Data Modeling  

- Relationship 1: `Orders[Order_ID] ↔ Order_Details[Order_ID]` (One-to-Many)  
- Relationship 2: `Pizzas[Pizza_Type_ID] ↔ Pizza_Types[Pizza_Type_ID]` (One-to-Many)  
- Relationship 3: `Pizzas[Pizza_ID] ↔ Order_Details[Pizza_ID]` (One-to-Many)  

---

## Measures and Calculations  

### Key Measures  

1. **Total Orders**:  
   - `Total_Orders = COUNT(Orders[Order_ID])`  
   - **Result**: 21,000 unique orders  

2. **Total Revenue**:  
   - Created a calculated column using the RELATED function:  
     - `Total_Price = Quantity × Price`  
   - `Total_Revenue = SUM(Order_Details[Total_Price])`  
   - **Result**: $817.86K  

3. **Average Metrics**:  
   - **Average Order per Month**: 1.8K  
   - **Average Order per Quarter**: 5.3K  
   - **Average Order per Day**: 59.6  
   - **Average Order Value (AOV)**: $38.3  
   - **Average Revenue per Day**: $2.3K  
   - **Average Revenue per Month**: $68.2K  
   - **Average Revenue per Quarter**: $204.5K  

---

## Visualizations  

### Sales Dashboard  

#### Cards Created  

1. Total Orders: 21,000  
2. Total Revenue: $817.86K  
3. Average Order Value (AOV): $38.3  
4. Average Revenue per Day: $2.3K  
5. Average Revenue per Month: $68.2K  
6. Average Revenue per Quarter: $204.5K  

#### Visuals Created  

1. **Total Orders by Time**:  
   - **By Month**: July is the highest.  
   - **By Quarter**: Q2 is the highest.  
   - **By Day**: Friday is the highest.  

2. **Total Revenue by Time**:  
   - **By Month**: July is the highest.  
   - **By Quarter**: Q2 is the highest.  
   - **By Day**: Friday is the highest.  

---

### Pizza Table Analysis  

#### Cards Created  

1. **Top Pizza by Revenue**: Thai Chicken  
2. **Bottom Pizza by Revenue**: Brie Carre  
3. **Top Pizza by Orders**: Classic Deluxe  
4. **Bottom Pizza by Orders**: Brie Carre  

#### Visuals Created  

1. **Pizza Category Revenue Distribution (Bar Chart)**:  
   - **Highest**: Classic  
   - **Lowest**: Veggie  

2. **Pizza Category Order Distribution (Pie Chart)**:  
   - **Highest**: Classic  
   - **Lowest**: Chicken  

3. **Top 7 Pizzas by Revenue (Bar Chart)**  
4. **Top 7 Pizzas by Orders (Bar Chart)**  

---

## Insights and Recommendations  

1. **Top Performers**:  
   - Thai Chicken is the most profitable pizza, while Classic Deluxe is the most ordered.  
   - Focus marketing campaigns around these top-performing pizzas.  

2. **Low Performers**:  
   - Brie Carre consistently underperforms in both revenue and orders.  
   - Consider revisiting pricing, marketing, or recipe improvements.  

3. **Time-Based Trends**:  
   - Q2 and July exhibit peak sales. Promotions during these periods can amplify revenue.  
   - Fridays are the busiest days; staffing and inventory should be optimized accordingly.  

4. **Category Insights**:  
   - Classic pizzas dominate both revenue and orders. Expanding this category with new options could further boost sales.  

---

## Conclusion  

The Maven Pizza Sales Analysis provides actionable insights to enhance revenue, order volume, and customer satisfaction. By leveraging identified trends, the pizza business can optimize operations, improve product offerings, and maximize profitability.  

