# Online Retail Exploratory Data Analysis with Python

## Overview
In this project, we step into the role of an entry-level data analyst at an online retail company to help interpret real-world data and support key business decisions. Using transactional data from an online retail store, we conduct exploratory data analysis to uncover insights into sales trends, customer behavior, and popular products.

By identifying patterns, outliers, and correlations, we can generate actionable insights that optimize store operations, improve customer satisfaction, and enhance the store’s overall performance in a competitive online retail market.

## Project Objectives
1. Describe data to answer key questions and uncover insights.
2. Gain valuable insights that will help improve online retail performance.
3. Provide analytic insights and data-driven recommendations.

## Dataset
The dataset used is the **"Online Retail"** dataset containing transactional data from an online retail store from **2010 to 2011**.

### Columns in the dataset:
- **InvoiceNo**: Invoice number of the transaction.
- **StockCode**: Unique code of the product.
- **Description**: Description of the product.
- **Quantity**: Quantity of the product in the transaction.
- **InvoiceDate**: Date and time of the transaction.
- **UnitPrice**: Unit price of the product.
- **CustomerID**: Unique identifier of the customer.
- **Country**: Country where the transaction occurred.

## Tools and Libraries Used
- **Python**
- **pandas**
- **numpy**
- **matplotlib**
- **seaborn**

## Steps Performed

### 1. Loading the Data
The dataset was loaded into a pandas DataFrame for analysis, and the first few rows were displayed to get an overview.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_excel("Online Retail.xlsx")
print(df.head())
```

### 2. Data Cleaning
- **Handling Missing Values**: Missing values in the `Description` and `CustomerID` columns were handled.
- **Removing Duplicates**: Duplicate entries were removed to ensure data accuracy.

```python
print(df.isnull().sum())
df.dropna(inplace=True)
df.drop_duplicates(inplace=True)
```

### 3. Basic Statistics
We explored basic statistics of the dataset, including measures of central tendency and dispersion.

```python
print(df.describe().T)
```

### 4. Data Visualization
We used various visualizations to better understand the data:
- **Histogram of Quantity**
- **Scatter plot of UnitPrice vs Quantity**
- **Sales trends over time**
- **Total sales by day of the week**

```python
# Histogram of Quantity
plt.hist(df['Quantity'], bins=30, color='skyblue', edgecolor='black')
plt.title('Histogram of Quantity')
plt.xlabel('Quantity')
plt.ylabel('Frequency')
plt.show()
```

### 5. Analyzing Sales Trends
We analyzed sales trends over time to identify the busiest months and days of the week.

```python
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'])
df['Month'] = df['InvoiceDate'].dt.month
df['DayOfWeek'] = df['InvoiceDate'].dt.day_name()

monthly_sales = df.groupby('Month')['Quantity'].sum()
weekday_sales = df.groupby('DayOfWeek')['Quantity'].sum()
```

### 6. Busiest Months and Days
The busiest month and day of the week were identified as:
- **Busiest Month**: November 2011
- **Busiest Day of the Week**: Thursday

### 7. Top-Selling Products and Countries
We identified the top-selling products and countries based on the quantity sold.

```python
top_products = df.groupby('Description')['Quantity'].sum().sort_values(ascending=False).head(10)
top_countries = df.groupby('Country')['Quantity'].sum().sort_values(ascending=False).head(10)
```

**Top-Selling Products**:
1. WORLD WAR 2 GLIDERS ASSTD DESIGNS
2. JUMBO BAG RED RETROSPOT
3. ASSORTED COLOUR BIRD ORNAMENT

**Top Countries Based on Quantity Sold**:
1. United Kingdom
2. Netherlands
3. EIRE

### 8. Outlier Detection
Outliers in the `Quantity` and `UnitPrice` columns were detected using box plots.

```python
sns.boxplot(df['Quantity'], color='skyblue')
plt.title('Boxplot of Quantity')
plt.xlabel('Quantity')
plt.show()
```

## Conclusion and Summary
1. The dataset provided transactional data from an online retail store between 2010 and 2011.
2. Data cleaning involved handling missing values and removing duplicate records.
3. Exploratory Data Analysis revealed:
   - November 2011 was the busiest month in terms of sales.
   - Thursday was the busiest day of the week.
   - The top-selling product was "WORLD WAR 2 GLIDERS ASSTD DESIGNS."
   - The United Kingdom had the highest sales quantity.
4. Outliers were identified in the `Quantity` and `UnitPrice` columns, which could impact future analysis.

## Recommendations
1. **Inventory Management**: Increase stock of top-selling products during peak months to meet demand.
2. **Marketing Strategy**: Focus marketing campaigns on Thursdays to maximize sales.
3. **Geographic Expansion**: Consider expanding operations in high-performing countries such as the Netherlands and EIRE.
4. **Outlier Handling**: Investigate the identified outliers further to ensure data integrity and accuracy.

## How to Run the Project
1. Clone the repository:
   ```bash
   git clone <https://github.com/Rk-ahmed/Statistical-analysis/blob/main/online_retail.ipynb>
   ```
2. Open the Jupyter Notebook and run the cells in sequence.
3. Ensure the following libraries are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
4. Load the dataset and follow the analysis steps as outlined.

## License
This project is licensed under the MIT License.

## Acknowledgments
Special thanks to Coursera for providing the dataset and the Jupyter Notebook environment for this project.
