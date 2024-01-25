# Awesome-chocolate-portfolio-project

## Project Overview

This data analysis project aims to provide insights into the sales performance of Awesome Chocolate Company. By analyzing various aspect of sales data.

### Data Source

I came across this dataset online and admired how reach the data is. I downloaded it "awesome-chocolate-data.sql" it cointain detailed information about the company.

### Tools

- SQL Server - Data Analysis
- Power BI - Creating report

### Data Cleaning and Preparation

In the initial data preparation, i performed the following tasks;
1. Data loading and inspection
2. Data cleaning and formality

### Exploratory Data Analysis(EDA)

EDA involved exploring the data to answer key questions below;
1. What is the total sales?
2. What is the total boxes?
3. Which 10 product sells more boxes? 
4. what is the sales trend?
5. What is the sales by geo?
6. How much sales/total boxes for each sales person?

### Data analysis and visual

Code/features worked with;
```sql
--Total sales
  SELECT SUM(amount) AS Total_revenue
  FROM sales
```
```sql
--Total boxes
SELECT SUM(boxes)
FROM sales
```
``` sql 
--10 product sells more boxes
SELECT p.product, SUM(s.boxes) total_boxes
FROM sales s
JOIN products p
ON s.PID = p.PID
GROUP BY p. product
ORDER BY 2 DESC
LIMIT 10;
```
```sql
--sales/total boxes for each sales person
SELECT p.salesperson, SUM(s.amount)Total_sales
FROM sales s
JOIN people p
ON s.SPID = p.SPID
GROUP BY p. salesperson
ORDER BY Total_sales DESC;
```
   
