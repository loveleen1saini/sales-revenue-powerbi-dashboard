# 📊 Sales & Revenue Dashboard – Power BI Project

This project demonstrates how Power BI can be used to analyze and visualize sales data for insights across time, product categories, and regions.

---

## 🛠 Tools Used
- **Power BI** (Data Modeling, DAX, Visualization)
- **Excel** (Source Data)

---

## 📁 Data Tables Used
- **Sales_Data**: Date, Product, Region, Quantity, Unit Price, Cost
- **Product_Master**: Product ID, Product Name, Category
- **Region_Master**: Region ID, Region Name

---

## 🧪 Data Processing (Power Query)
- Merged lookup tables (Product, Region) into sales data
- Calculated Total Sales, Cost, Profit columns
- Cleaned nulls, errors, and fixed data types

---

## 📐 DAX Measures Created
```dax
Total Sales = SUM(Sales_Data[Total Sales])
Total Cost = SUM(Sales_Data[Total Cost])
Total Profit = SUM(Sales_Data[Profit])
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
Sales Growth % = 
    VAR PrevSales = CALCULATE([Total Sales], DATEADD(Sales_Data[Date], -1, MONTH))
    RETURN DIVIDE([Total Sales] - PrevSales, PrevSales, 0)
