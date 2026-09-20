# Ecommerce_Rough_Data_Analysis_python_sql
This project analyzes the Brazilian Olist E-Commerce dataset using Python and MySQL.

# Olist E-Commerce Data Analysis

## 📌 Project Overview

This project analyzes the **Brazilian Olist E-Commerce dataset** using **Python and MySQL**.

The main objective is to answer business questions related to **customers, orders, products, payments, sellers, reviews, and sales** using SQL queries and Python for analysis and visualization.

---

## 🛠️ Technologies Used

* Python
* MySQL
* Pandas
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 📂 Dataset Tables

The project uses the following tables:

* `customers`
* `geolocation`
* `order_items`
* `order_payments`
* `order_reviews`
* `orders`
* `product_category_name_translation`
* `products`
* `sellers`

---

## 🔗 Project Workflow

```text
Olist Dataset
      ↓
   MySQL
      ↓
 SQL Queries
      ↓
 Python + Pandas
      ↓
 Analysis & Visualization
      ↓
 Business Insights
```

---

## 📊 Analysis Performed

The project answers business questions such as:

1. What are the top-selling product categories?
2. What is the total sales amount?
3. What percentage of total sales comes from each product category?
4. Which states have the highest number of customers?
5. Which product categories generate the most revenue?
6. What are the most common payment methods?
7. What is the average order value?
8. Which sellers generate the highest sales?
9. What is the average customer review score?
10. Which product categories receive the highest ratings?
11. How many orders are delivered, canceled, or unavailable?
12. What is the monthly sales trend?
13. Which payment installments are most commonly used?
14. Which states generate the highest sales?
15. Which products have the highest sales?

---

## 🗄️ MySQL Analysis

Example SQL query:

```sql
SELECT 
    UPPER(products.product_category_name) AS category,
    ROUND(
        (SUM(order_payments.payment_value) /
        (SELECT SUM(payment_value) FROM order_payments)) * 100,
        2
    ) AS sales_percentage
FROM products
JOIN order_items
    ON products.product_id = order_items.product_id
JOIN order_payments
    ON order_payments.order_id = order_items.order_id
GROUP BY category
ORDER BY sales_percentage DESC;
```

This query calculates the **percentage contribution of each product category to total sales**.

---

## 🐍 Python Analysis

Python is used to execute SQL queries and analyze the results.

```python
import pandas as pd
import matplotlib.pyplot as plt

cur.execute(query)
data = cur.fetchall()

df = pd.DataFrame(
    data,
    columns=["Category", "Sales Percentage"]
)

df.head()
```

Example visualization:

```python
plt.figure(figsize=(10, 6))

plt.bar(
    df["Category"],
    df["Sales Percentage"]
)

plt.xticks(rotation=90)
plt.xlabel("Product Category")
plt.ylabel("Sales Percentage")
plt.title("Sales Percentage by Product Category")

plt.show()
```

---

## 📈 Key Skills Demonstrated

* SQL Joins
* GROUP BY
* Aggregate Functions
* Subqueries
* ORDER BY
* Percentage Calculations
* MySQL-Python Connection
* Pandas DataFrames
* Data Visualization
* Business Data Analysis

---

## 🎯 Project Objective

The objective of this project is to use **SQL and Python to transform e-commerce data into meaningful business insights** that can help understand sales, customers, products, payments, sellers, and order performance.

---

## 👨‍💻 Tools

**Database:** MySQL
**Programming:** Python
**Analysis:** Pandas
**Visualization:** Matplotlib, Seaborn
**Environment:** Jupyter Notebook


# 👨‍💻 Author
**Satyanarayan Mohanty**
**| Data Scientist | Data Analyst | Python | SQL | MySQL**

---

## 📁 Project Structure

```text
Olist-Ecommerce-Analysis/
│
├── README.md
├── python+sql_Olist_Ecommerce.ipynb
├── csv_to_sql.ipynb
├── csv_to_sql.py
├── Questions.txt

```

---

## ⭐ Conclusion

This project demonstrates how **MySQL and Python can be combined for real-world e-commerce data analysis**, from writing SQL queries to generating business insights and visualizations.

