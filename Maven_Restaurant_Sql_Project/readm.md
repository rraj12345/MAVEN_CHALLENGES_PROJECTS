# SQL Project: Restaurant Menu and Order Analysis

This project involves working with two tables, `menu_items` and `order_details`, to analyze data related to a restaurant's menu and customer orders. The project demonstrates proficiency in SQL by performing various data manipulations, aggregations, and insights extraction. Below is a detailed explanation of the project structure and SQL queries used.

---

## Project Overview

### Tables Description
1. **menu_items**:
   - Stores information about the restaurant's menu items.
   - Columns:
     - `menu_item_id`: Unique identifier for each menu item.
     - `item_name`: Name of the menu item.
     - `category`: Category of the menu item (e.g., Italian, Desserts).
     - `price`: Price of the menu item.

2. **order_details**:
   - Contains details of orders placed by customers.
   - Columns:
     - `order_details_id`: Unique identifier for each order detail.
     - `order_id`: Identifier for the order.
     - `order_date`: Date when the order was placed.
     - `order_time`: Time when the order was placed.
     - `item_id`: Identifier for the ordered menu item.

---

### Objectives

- Understand the structure of the menu and order details.
- Extract insights such as the most and least expensive items, total items ordered, and order summaries.
- Perform advanced SQL operations such as joins, aggregations, and creating views.

---

## SQL Queries

### Menu Insights
1. View all menu items:
   ```sql
   SELECT * FROM menu_items;
   ```

2. Count the number of items on the menu:
   ```sql
   SELECT COUNT(item_name) FROM menu_items;
   ```

3. Find the least and most expensive items on the menu:
   ```sql
   SELECT item_name, price FROM menu_items ORDER BY price DESC LIMIT 1;
   SELECT item_name, price FROM menu_items ORDER BY price LIMIT 1;
   ```

4. Count the number of Italian dishes on the menu:
   ```sql
   SELECT COUNT(category) FROM menu_items WHERE category = 'Italian';
   ```

5. Find the least and most expensive Italian dishes:
   ```sql
   SELECT category, price FROM menu_items WHERE category = 'Italian' ORDER BY price DESC LIMIT 1;
   SELECT category, price FROM menu_items WHERE category = 'Italian' ORDER BY price LIMIT 1;
   ```

6. Count the number of dishes in each category:
   ```sql
   SELECT category, COUNT(*) AS 'Total' FROM menu_items GROUP BY category ORDER BY Total;
   ```

7. Calculate the average dish price within each category:
   ```sql
   SELECT category, AVG(price) AS 'Avg Price' FROM menu_items GROUP BY category ORDER BY AVG(price) DESC;
   ```

### Order Details Analysis
1. View the `order_details` table:
   ```sql
   SELECT * FROM order_details;
   ```

2. Determine the date range of the orders:
   ```sql
   SELECT MIN(order_date) AS earliest_date, MAX(order_date) AS latest_date FROM order_details;
   ```

3. Count the total number of items ordered:
   ```sql
   SELECT COUNT(item_id) FROM order_details;
   ```

4. Count the total number of orders:
   ```sql
   SELECT COUNT(order_id) FROM order_details;
   ```

5. Identify the orders with the most items:
   ```sql
   SELECT order_id, COUNT(item_id) FROM order_details GROUP BY order_id ORDER BY COUNT(item_id) DESC LIMIT 10;
   ```

6. Find orders with more than 12 items:
   ```sql
   SELECT order_id, COUNT(item_id) AS 'Total' FROM order_details GROUP BY order_id HAVING COUNT(item_id) > 12 ORDER BY Total DESC LIMIT 10;
   ```

### Combining Data
1. Join `menu_items` and `order_details`:
   ```sql
   SELECT * FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id;
   ```

2. Identify the least and most ordered items:
   ```sql
   SELECT category, item_name, COUNT(order_details_id) AS T FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id GROUP BY category, item_name ORDER BY T DESC;
   ```

3. Find the top 5 highest-spending orders:
   ```sql
   SELECT order_id, SUM(price) AS T FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id GROUP BY order_id ORDER BY T DESC LIMIT 5;
   ```

4. View details of the highest-spend order:
   ```sql
   SELECT category, COUNT(item_id) AS T FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id WHERE order_id = 440 GROUP BY category ORDER BY T DESC;
   ```

5. Calculate the most expensive order:
   ```sql
   SELECT order_id, SUM(price) AS Max FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id GROUP BY order_id ORDER BY Max DESC;
   ```

### Advanced Querying
1. Use a Common Table Expression (CTE) to find the highest order total:
   ```sql
   WITH cte AS (
     SELECT order_id, SUM(price) AS Max FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id GROUP BY order_id
   )
   SELECT MAX(Max) FROM cte;
   ```

2. Create a view to store order totals:
   ```sql
   CREATE VIEW OrderTables AS (
     SELECT order_id, SUM(price) AS Max1 FROM menu_items AS m JOIN order_details AS o ON m.menu_item_id = o.item_id GROUP BY order_id
   );
   SELECT MAX(Max1) FROM OrderTables;
   ```

---

## Technologies Used
- **SQL**: Structured Query Language for data analysis.
- **Database Management System (DBMS)**: A relational database to store and manage the data.

---

## How to Use
1. Clone the repository to your local machine.
2. Create a database named `restaurant_db`.
3. Import the provided SQL scripts to create and populate the `menu_items` and `order_details` tables.
4. Run the queries in your preferred SQL client to analyze the data.

---

## Insights and Learnings
- Gained hands-on experience with SQL query writing, including joins, aggregations, and groupings.
- Developed a deeper understanding of relational databases and data analysis workflows.
- Extracted meaningful business insights, such as identifying popular dishes, high-spending customers, and category-based trends.

---

## Future Enhancements
- Integrate visualization tools (e.g., Tableau, Power BI) to display the results graphically.
- Expand the dataset to include customer and employee details for more comprehensive analysis.
- Optimize query performance for large datasets.

---

## Author
Raj Kishore Agrawal
