# Maven Toy Store Project Analysis Report

## **Executive Summary**
Maven Toy is a U.S.-based toy company operating for the past two years, with 50 stores across 29 cities. This project aims to analyze sales and operational data, build data models using Power BI, and provide actionable insights. The analysis utilizes a star schema data model comprising five tables: Stores, Sales, Products, Inventory, and Calendar. Key insights and metrics derived from the analysis are detailed below.

---

## **Dataset Overview**

### **Table Descriptions**
1. **Products Table**
   - Contains details of product IDs, names, categories, costs, and retail prices.

2. **Inventory Table**
   - Tracks store-level stock availability for each product.

3. **Stores Table**
   - Provides store-specific information, including store IDs, names, locations, and opening dates.

4. **Sales Table**
   - Includes transactional data, such as sale IDs, dates, store IDs, product IDs, and units sold.

5. **Calendar Table**
   - Offers a comprehensive date reference for time-based analysis.

---

## **Data Preparation**

### **Steps Undertaken**
1. **Data Loading**:
   - Imported the dataset into Power BI.

2. **Data Cleaning**:
   - Identified and resolved issues such as null values, duplicate records, incorrect data types, and misaligned column names.

3. **Data Transformation**:
   - Created additional time-based columns in the Calendar table (e.g., Year, Month, Quarter, Week).
   - Linked data tables using a star schema with the Sales table as the fact table and others as dimension tables.

4. **Data Enrichment**:
   - Added columns for cost and price in the Sales table using the DAX **RELATED** function.
   - Created calculated columns for:
     - **Total Cost** = Units Sold × Product Cost
     - **Total Revenue** = Units Sold × Product Price
     - **Profit** = Total Revenue - Total Cost

---

## **Key Metrics and Insights**

### **Summary Metrics**
- **Total Categories**: 5
- **Total Cities**: 29
- **Total Stores**: 50
- **Total Products**: 35
- **Total Revenue**: $14.44M
- **Total Units Sold**: 1.091M
- **Total Profit**: $4M

### **Top and Bottom Performers**
- **Top-Performing Product**: LegoBricks
- **Lowest-Performing Product**: PlaydohCan
- **Best-Performing Store**: Maven Toys Ciudad de Mexico 2
- **Worst-Performing Store**: Maven Toys Campeche 2

### **Revenue Distribution by Location**
- **Downtown**: 56.9%
- **Commercial Areas**: 22.7%
- **Residential Areas**: 11.47%
- **Airports**: Remaining percentage

---

## **Visualizations and Analysis**

### **1. Bar Chart: Total Orders by Category (Year-wise)**
- **Observation**:
   - Toys and Art & Craft categories have the highest total orders (0.44M).
   - 2023 lags behind 2022 in overall performance.

### **2. Line Chart: Total Revenue by Category**
- **Observation**:
   - The Toy category leads with $5.1M in revenue.
   - Sports and Outdoor categories are the lowest contributors with $2.2M.
   - 2022 dominates over 2023 in revenue generation.

### **3. Pie Chart: Revenue Distribution by Location**
- **Observation**:
   - Downtown locations generate the highest revenue (56.9%), followed by Commercial areas (22.7%).
   - Residential and Airport locations account for smaller shares of revenue.

---

## **Interactive Features**

### **Slicers**
1. **Category**: Allows stakeholders to filter results by product categories.
2. **Month**: Enables monthly trend analysis.
3. **Year**: Facilitates year-over-year comparison.

---

## **Recommendations**

1. **Product Strategy**:
   - Focus on promoting high-performing products like LegoBricks through targeted marketing.
   - Revise pricing or promotional strategies for low-performing products such as PlaydohCan.

2. **Store Optimization**:
   - Investigate underperformance at Maven Toys Campeche 2 and develop strategies to boost sales.
   - Leverage the success of Maven Toys Ciudad de Mexico 2 by replicating best practices across other stores.

3. **Category Trends**:
   - Increase inventory and marketing for high-demand categories like Toys and Art & Craft.
   - Explore reasons for lower performance in the Sports and Outdoor categories and address gaps.

4. **Location Insights**:
   - Enhance offerings and customer engagement in Downtown locations to maintain leadership.
   - Develop strategies to increase revenue in Residential and Airport locations.

5. **Future Analysis**:
   - Perform monthly and seasonal trend analysis to align inventory and marketing efforts.
   - Introduce advanced customer segmentation for personalized campaigns.

---

## **Conclusion**
This analysis highlights key drivers of success and areas for improvement in Maven Toy’s operations. Leveraging these insights can help optimize performance, enhance customer satisfaction, and achieve long-term growth. Continuous monitoring and iterative improvements will ensure sustained success in a competitive market.

---

**Prepared By:**
Raj Kishore Agrawal
Business Analyst
