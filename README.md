# 📊 E-Commerce Sales & Profit Analysis

This project focuses on analyzing an **E-Commerce dataset** to discover business insights related to **sales performance, profit trends, and customer segments**.
The analysis was performed using **Python in Google Colab / Jupyter Notebook** with libraries such as **Pandas, NumPy, Matplotlib, and Seaborn**.

The goal of this project is to practice **data cleaning, exploratory data analysis (EDA), and data visualization** to understand how different categories, segments, and months affect business performance.

---

# 🧰 Tools & Technologies Used

* Python
* Google Colab / Jupyter Notebook
* Pandas – Data cleaning & data manipulation
* NumPy – Numerical operations
* Matplotlib – Data visualization
* Seaborn – Statistical visualization

---

# 📂 Dataset

The dataset used in this project is the **Superstore E-Commerce Dataset**, which contains information about:

* Orders
* Sales
* Profit
* Product Categories
* Sub-Categories
* Customer Segments
* Order Date & Ship Date

This dataset helps analyze **business performance and customer purchasing patterns**.

---

# ⚙️ Project Workflow

## 1️⃣ Data Loading

The dataset was loaded using **Pandas**.

```python
import pandas as pd

df = pd.read_csv("Sample - Superstore.csv", encoding='latin1')
df.head()
```

---

# 🧹 Data Cleaning

Several data cleaning steps were performed:

* Checked dataset structure using `.info()`
* Checked missing values
* Checked duplicate records
* Removed duplicate **Customer IDs**
* Converted **Order Date** and **Ship Date** to datetime format

Example:

```python
df['Ship Date'] = pd.to_datetime(df['Ship Date'], format='%m/%d/%Y')
df['Order Date'] = pd.to_datetime(df['Order Date'], format='%m/%d/%Y')
```

These steps ensure the dataset is **clean and ready for analysis**.

---

# 🗓 Feature Engineering

New date-related columns were created from the **Order Date** column to perform time-based analysis.

Created columns:

* Order Year
* Order Month
* Order Weekday

Example:

```python
df['Order Year'] = df['Order Date'].dt.year
df['Order Month'] = df['Order Date'].dt.month_name().str[:3]
df['Order Week'] = df['Order Date'].dt.dayofweek
```

This helps analyze **sales trends over time**.

---

# 📊 Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand **patterns, trends, and relationships in the data**.

The analysis included:

* Monthly Sales Analysis
* Category-wise Sales
* Sub-category Sales
* Monthly Profit Analysis
* Segment Analysis
* Sales to Profit Ratio

---

# 📈 Monthly Sales Analysis

Sales were grouped by **Order Month** to analyze monthly sales performance.

```python
Sales_By_Month = df.groupby('Order Month')['Sales'].sum().reset_index()
```

Visualization:

* Line chart showing **monthly sales trends**

Insight:

* Helps identify **months with highest and lowest sales**.

---

# 🏷 Category Wise Sales Analysis

Sales were grouped by **product category**.

```python
Sales_by_Categorie = df.groupby('Category')['Sales'].sum().reset_index()
```

Visualization:

* Bar chart of **Sales by Category**

Insight:

* Shows which **product category generates the highest revenue**.

---

# 📦 Sub-Category Sales Analysis

```python
Sales_By_Sub_Categories = df.groupby('Sub-Category')['Sales'].sum().reset_index()
```

Visualization:

* Bar chart of **Sales by Sub-Category**

Insight:

* Identifies **best-selling product types**.

---

# 💰 Monthly Profit Analysis

Profit was analyzed on a **monthly basis**.

```python
Monhly_profit_Analysis = df.groupby('Order Month')['Profit'].sum().reset_index()
```

Visualization:

* Bar chart showing **monthly profit distribution**

Insight:

* Shows which months produce the **highest profit**.

---

# 🧾 Profit by Category

Profit contribution from each category was analyzed using a **pie chart**.

```python
Profit_by_Categorie.set_index('Category')['Profit'].plot.pie(autopct='%1.1f%%')
```

Insight:

* Helps identify **which category contributes the most to total profit**.

---

# ⚠ Negative Profit Detection

Rows with **negative profit** were identified to detect loss-making transactions.

```python
df[df['Profit'] < 0]
```

Insight:

* Helps find **products or transactions causing losses**.

---

# 👥 Segment Analysis

Sales and profit were analyzed based on **customer segments**.

```python
Sales_Profit_By_Segment = df.groupby('Segment')[['Sales','Profit']].sum().reset_index()
```

Customer segments include:

* Consumer
* Corporate
* Home Office

---

# 📉 Sales to Profit Ratio

To understand business efficiency, the **Sales to Profit Ratio** was calculated.

```python
Segment_Analysis['Sales_to_Profit_Ratio'] = Segment_Analysis['Sales'] / Segment_Analysis['Profit']
```

Insight:

* Shows how efficiently **sales convert into actual profit**.

---

# 📷 Visualizations Included

This project includes multiple visualizations such as:

* Monthly Sales Line Chart
* Category Sales Bar Chart
* Sub-Category Sales Bar Chart
* Monthly Profit Chart
* Profit Distribution Pie Chart
* Segment Analysis Charts

These visualizations help convert raw data into **clear and understandable business insights**.

---

# 📌 Key Insights

Some important insights discovered during the analysis:

* Sales performance varies across **different months and categories**.
* Some **sub-categories generate high sales but lower profit**.
* Certain transactions produce **negative profit**, indicating potential losses.
* Customer segments contribute differently to **sales and profit generation**.
* Sales to profit ratio helps measure **business efficiency**.

---

# 🎯 Project Purpose

The main goal of this project is to practice:

* Data Cleaning
* Exploratory Data Analysis (EDA)
* Data Visualization
* Business Insight Generation

This is a **beginner-friendly data analysis project** that demonstrates how Python can be used to analyze real-world business data.

---

# 🚀 Future Improvements

Possible improvements for this project:

* Build an **interactive dashboard using Power BI or Tableau**
* Perform **advanced statistical analysis**
* Apply **machine learning models for sales prediction**
* Create **automated reporting dashboards**

---

# 👨‍💻 Author

Aditya Gupta

Aspiring **Data Analyst / Data Scientist** interested in:

* Data Analysis
* Machine Learning
* Business Intelligence
* Data Visualization

---

# ⭐ Support

If you found this project helpful, please consider **starring the repository on GitHub**.
