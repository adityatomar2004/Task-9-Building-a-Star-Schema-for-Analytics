# Task 9: SQL Data Modeling - Build a Star Schema

## 📊 Project Overview
This project focuses on **Data Modeling** and **Warehousing**. The goal was to transform a raw, flat dataset (Global Superstore) into a structured **Star Schema** optimized for Business Intelligence (BI) reporting and high-performance analytics.

## 📂 Files Included
* **`task9_star_schema.sql`**: The SQL script containing table creation, ETL (Extraction, Transformation, Loading) logic, and analysis queries.
* **`task9_warehouse.db`**: The SQLite database file containing the fully populated Star Schema.
* **`Superstore.csv`**: The raw dataset used as the source.
* **`star_schema_diagram.png`**: (Optional) Visual representation of the data model.

## 🏗️ Database Design (Star Schema)
The database follows a standard Star Schema architecture consisting of **Dimension Tables** (descriptive data) and a **Fact Table** (transactional data).

### **Fact Table**
* **`fact_sales`**: Stores quantitative metrics like `Sales`, `Quantity`, `Discount`, and `Profit`, linked to dimensions via Foreign Keys.

### **Dimension Tables**
* **`dim_customer`**: Stores unique customer details (`Customer Name`, `Segment`).
* **`dim_product`**: Stores product attributes (`Category`, `Sub-Category`, `Product Name`).
* **`dim_location`**: Stores geographic data (`City`, `State`, `Region`) using a surrogate key (`location_id`).
* **`dim_date`**: Stores date attributes (`Year`, `Quarter`, `Month`, `Day`) to facilitate time-based analysis.

## ⚙️ Process & Methodology
1. **Data Import**: The raw `Superstore.csv` data was imported into a staging table in SQLite.
2. **Schema Creation**: SQL `CREATE TABLE` statements were used to define the Fact and Dimension tables with appropriate Primary and Foreign Keys.
3. **ETL (Extract, Transform, Load)**:
   * **Dimensions**: `INSERT INTO ... SELECT DISTINCT` queries were used to populate dimension tables with unique values.
   * **Fact Table**: Transactional data was inserted into the fact table, mapping `City/State` to `location_id` and other keys to their respective dimensions.
4. **Optimization**: Indexes were created on foreign keys (`customer_id`, `product_id`, `order_date`) to speed up join performance.

## 🚀 How to Run
1. **View Database**: Open the `task9_warehouse.db` file using **DB Browser for SQLite** or any SQL client.
2. **Run Analysis**: Execute the SQL queries provided in the script to generate insights (e.g., Total Sales by Region).

## 🛠️ Tools Used
* **SQLite**: For the relational database management system.
* **SQL**: For data definition (DDL) and manipulation (DML).
* **VS Code / Text Editor**: For writing and editing code.
