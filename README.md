# AdventureWorks Data Warehouse Project

This repository contains an end-to-end Data Warehouse solution using the **AdventureWorks** database. The project demonstrates the full lifecycle of data warehousing, from ETL (Extract, Transform, Load) processes to business intelligence reporting using **SQL Server Integration Services (SSIS)**, **SQL Server Analysis Services (SSAS)**, and **Power BI**. This project showcases how data from multiple sources is transformed into meaningful insights for business decision-making.

## Project Overview

The goal of this project is to design, implement, and deploy a Data Warehouse for a fictional company, AdventureWorks, which manages an extensive range of bicycle products and services. The ETL pipelines extract data from two separate databases (ERP and HR), load it into a staging area, and then into a star schema-based Data Warehouse. From there, the data is analyzed using a **tabular cube** and visualized in **Power BI**.

### Source Databases:
- **ERP Database**: Contains order, customer, product, and sales data.
- **HR Database**: Holds employee and department information.

### Tools and Technologies Used:
- **SQL Server**: For database and Data Warehouse management.
- **SSIS (SQL Server Integration Services)**: To automate the ETL process.
- **SSAS (SQL Server Analysis Services)**: To create a tabular model for OLAP.
- **SQL Server Agent**: To schedule daily ETL jobs.
- **Power BI**: To build interactive reports and dashboards.

---

## Architecture Overview

Below is the architecture of the implemented solution:

1. **Source to Staging ETL**:
   - Extracted data from ERP and HR databases.
   - Loaded small tables with a **truncate-and-load** strategy.
   - Implemented **incremental loading** for large tables like `OrderHeader` and `OrderDetail` to optimize performance.

2. **Staging to Data Warehouse ETL**:
   - Loaded transformed data into the Data Warehouse using **stored procedures** to implement data transformations.
   - ETL jobs are scheduled to run daily using **SQL Server Agent**.

3. **SSAS Tabular Model**:
   - Created a tabular cube with measures, dimensions, and calculated fields.
   - Designed for optimized querying and analysis.

4. **Power BI Dashboard**:
   - Connected Power BI to the SSAS tabular cube.
   - Built a dashboard for business insights, visualizing key metrics like sales performance, customer demographics, and product trends.

---

## Project Workflow

### 1. **Data Warehouse Design**
   - Developed a **star schema** for the data warehouse, using **surrogate keys** for dimension tables (e.g., Customer, Product) and fact tables (e.g., FactSales).

### 2. **ETL Process (Source to Staging)**
   - Created SSIS packages to extract data from the ERP and HR databases into the staging area.
   - Implemented:
     - **Truncate and Load**: For small tables like Products, Categories, Employees.
     - **Incremental Loading**: For large tables like `OrderHeader` and `OrderDetail`.

### 3. **ETL Process (Staging to Data Warehouse)**
   - Transformed data in staging and loaded it into the star schema of the Data Warehouse.
   - Built stored procedures for incremental data transformation and loading.
   - Automated the process using SSIS packages.

### 4. **SSAS Tabular Cube**
   - Designed a **tabular cube** to allow fast analytical queries.
   - Built measures for total sales, sales by region, customer counts, and more.

### 5. **Power BI Dashboard**
   - Created a Power BI dashboard that connects to the SSAS cube, providing visual insights into:
     - Sales Performance (Total sales, Sales by product, Sales by geography).
     - Customer Analysis (Customer demographics, Customer segmentation).
     - Product Trends (Top products, Product sales performance).

---

## Repository Structure


