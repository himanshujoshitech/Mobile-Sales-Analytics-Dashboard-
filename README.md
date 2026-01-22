# 📱 Mobile Sales Dashboard | Power BI Project

🚀 An **end-to-end Power BI project** focused on analyzing mobile sales performance using **data modeling, DAX, time intelligence, and professional dashboard design**.

This project demonstrates how raw sales data can be transformed into a **clean, interactive, and business-ready dashboard**, following **real-world BI best practices**.

---

## 🧠 Overview of Learning

Through this project, I learned and implemented:

- ✔ Understanding & preparing raw datasets  
- ✔ Creating a **custom calendar using DAX**  
- ✔ Building relationships in **Data Model View**  
- ✔ Writing **essential & advanced DAX measures**  
- ✔ Designing a **professional dashboard UI**  
- ✔ Using **Edit Interactions**  
- ✔ Implementing **MTD, QTD, YTD** time intelligence  
- ✔ Implementing **Same Period Last Year (SPLY)** logic  
- ✔ Using the **DAX Query View**  
- ✔ Publishing reports to **Power BI Service**

---

## 🔗 Building Relationships in the Data Model View

After creating the custom calendar, the next crucial step was **data modeling**.

The project follows a **Star Schema**, where:
- A central **Fact table (Sales_Data)** contains transaction-level data
- Multiple **Dimension tables** provide descriptive attributes

### ⭐ Fact Table
- **Sales_Data**
  - Stores transaction rows
  - Contains numerical measures such as *Units Sold, Price per Unit, Sales Amount*
  - Acts as the core of analysis

### ⭐ Dimension Tables
- **Custom_Calendar**
  - Date, Month, Quarter, Year, Day Name
- **Brand / Mobile Model**
- **City**
- **Payment Method**

### 🔗 Relationship Setup
```text
Custom_Calendar[Date]  →  Sales_Data[Date]


## 🖼️ Dashboard Screenshots

### 🔹 Main Dashboard
![Main Dashboard](Dashboard.png)

### 🔹 MTD (Month-To-Date) Report
![MTD Report](MTD%20Report.png)

### 🔹 Same Period Last Year Analysis
![Same Period Last Year](Same%20Period%20Last%20Year.png)

---

### 📊 Key KPIs Used

- 💰 **Total Sales**
- 📦 **Total Quantity Sold**
- 🔁 **Total Transactions**
- 💵 **Average Price**
- 📈 **MTD / QTD / YTD Sales**
- ⏪ **Same Period Last Year Comparison**

These KPIs help stakeholders quickly understand **overall performance, trends, and growth**.

---

### 🗂️ Dataset Understanding & Preparation

- The dataset contains **mobile sales transaction data**
- Includes attributes such as:
  - Brand
  - Mobile Model
  - City
  - Payment Method
  - Units Sold
  - Price per Unit
  - Date
  - Customer Ratings

🔗 **Dataset Link:**  
👉 [Mobile Sales Dataset (Excel)](https://github.com/himanshujoshitech/Mobile-Sales-Analytics-Dashboard-/blob/main/Mobile%20Sales%20Data.xlsx)  


### 🔧 Data Preparation Steps
- Loaded data using **Power Query**
- Removed inconsistencies & null values
- Changed correct data types
- Prepared data for modeling and analysis

📌 *Power Query ensures automated and repeatable transformations on refresh.*

---

## 📅 Creating a Custom Calendar using DAX

A **Custom Calendar table** was created to enable:
- Time intelligence calculations
- Continuous date analysis
- Month / Quarter / Year-based reporting

```DAX
Custom_Calendar = 
ADDCOLUMNS(
    CALENDAR (DATE(2022,1,1), DATE(2024,12,31)),
    "Year", YEAR([Date]),
    "Month", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Day Name", FORMAT([Date], "dddd")
)
````

---

## 🔗 Building Relationships in the Data Model View

After creating the custom calendar, the next crucial step was **data modeling**.

The project follows a **Star Schema**, where:
- A central **Fact table (Sales_Data)** contains transaction-level data
- Multiple **Dimension tables** provide descriptive attributes

### ⭐ Fact Table
- **Sales_Data**
  - Stores transaction rows
  - Contains numerical measures such as *Units Sold, Price per Unit, Sales Amount*
  - Acts as the core of analysis

### ⭐ Dimension Tables
- **Custom_Calendar**
  - Date, Month, Quarter, Year, Day Name
- **Brand / Mobile Model**
- **City**
- **Payment Method**

### 🔗 Relationship Setup
```text
Custom_Calendar[Date]  →  Sales_Data[Date]

- **Relationship Type:** One-to-Many (1 → *)
- **Cross-filter Direction:** Single
- This relationship enables accurate **time-based filtering** and ensures all **DAX time intelligence functions** work correctly.

📌 A proper relationship between the fact table and calendar table is **mandatory** for MTD, QTD, YTD, and Year-over-Year calculations.

---

## 🧮 Writing Essential DAX Measures

DAX (Data Analysis Expressions) was used to create **measures** that power all KPIs and insights in the dashboard.

### 🔹 Total Sales
```DAX
Total Sales =
SUMX(
    Sales_Data,
    Sales_Data[Units Sold] * Sales_Data[Price Per Unit]
)



