# 📊 Task 8: Simple Sales Dashboard Design – Data Analyst Internship

## 📁 Project Overview

This project involves creating a **simple, interactive dashboard** to analyze sales performance by **product category**, **region**, and **time** using the Superstore dataset.
Tools used: **Tableau** and **Python (for cleaning)**.

---

## 📌 Objective

* Visualize sales trends by month
* Compare sales by region and category
* Make the dashboard interactive using filters
* Derive actionable business insights

---

## 🧰 Tools & Technologies Used

* Tableau (Dashboard Creation)
* Python + Pandas (Data Cleaning)
* GitHub (Project Submission)

---

## 📊 Dataset Description

* File: `Superstore_Sales.csv`
* Columns used:

  * `Order Date`
  * `Region`
  * `Category`
  * `Sales`
  * `Profit`

---

## 🔧 Steps Performed

### 1. Data Cleaning using Python

```python
import pandas as pd

# Load dataset
df = pd.read_csv("Superstore_Sales.csv")

# Keep only required columns
required_columns = ['Order Date', 'Region', 'Category', 'Sales', 'Profit']
df = df[required_columns]

# Convert Order Date to datetime
df['Order Date'] = pd.to_datetime(df['Order Date'])

# Create Month-Year column
df['Month-Year'] = df['Order Date'].dt.to_period('M').astype(str)

# Save cleaned data
df.to_csv("Cleaned_Superstore_Sales.csv", index=False)
```

---

### 2. Import Data into Tableau

* Open Tableau → `Data > Connect to a file > Text File`
* Select `Cleaned_Superstore_Sales.csv`
* Drag sheet into workspace

---

### 3. Create Visualizations

#### ✅ Visual 1: **Line Chart** – Sales Over Time

* Columns: `Month-Year` (Discrete)
* Rows: `Sales`
* Sort chronologically

#### ✅ Visual 2: **Bar Chart** – Sales by Region

* Columns: `Region`
* Rows: `Sales`
* Sort by descending sales

#### ✅ Visual 3: **Donut Chart** – Sales by Category

* Use `Category` as dimension and `Sales` as measure
* Use pie chart and apply dual-axis technique for donut look

---

### 4. Add Filters

* `Region`
* `Category`
  
 Applied filters across all worksheets using `"Apply to worksheets > All using this data source"`

---

### 5. Highlight Top Performers

* Used color gradients to represent high and low sales
* Displayed data labels and used sorting for better clarity

---

### 6. Insights Generation

Created a separate text file `Insights.txt` with 4 key business insights from the dashboard.

---

## 📄 Files Included in Repository

* `Cleaned_Superstore_Sales.csv` – Cleaned dataset
* `Dashboard_Screenshot.png` – Screenshot of final dashboard
* `Insights.txt` – Key takeaways from data
* `task8.ipynb` – Cleaning of Raw Data

---

## ✅ Outcome

This task helped me learn:

* How to clean and structure sales data
* How to build an interactive dashboard
* How to extract meaningful business insights
