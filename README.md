# 📱 Mobile Sales Dashboard | Power BI Project

🚀 An **end-to-end Power BI project** focused on analyzing mobile sales performance using **data modeling, DAX, time intelligence, and professional dashboard design**.

This project demonstrates how raw sales data can be transformed into a **clean, interactive, and business-ready dashboard**, following **real-world BI best practices**.

---

## 🧠 Overview of Learning

Through this project, I learned and implemented:

- ✔ How to understand and prepare a dataset  
- ✔ Creating a **Custom Calendar using DAX**  
- ✔ Building relationships in **Data Model View**  
- ✔ Writing **essential and advanced DAX measures**  
- ✔ Designing a **professional Power BI dashboard**  
- ✔ Using **Edit Interactions** for better UX  
- ✔ Implementing **MTD, QTD, YTD**  
- ✔ Implementing **Same Period Last Year (SPLY)** logic  
- ✔ Using the **DAX Query View**  
- ✔ Publishing reports to **Power BI Service**

---

## 🖼️ Dashboard Screenshots

### 🔹 Main Dashboard
![Main Dashboard](Dashboard.png)

### 🔹 MTD (Month-To-Date) Report
![MTD Report](MTD%20Report.png)

### 🔹 Same Period Last Year Analysis
![Same Period Last Year](Same%20Period%20Last%20Year.png)

---

## 📊 Key KPIs Used

- 💰 **Total Sales**
- 📦 **Total Quantity Sold**
- 🔁 **Total Transactions**
- 💵 **Average Price**
- 📈 **MTD / QTD / YTD Sales**
- ⏪ **Same Period Last Year Comparison**

These KPIs help stakeholders quickly understand **overall performance, trends, and growth**.

---

## 🗂️ Dataset Understanding & Preparation

The dataset represents **mobile sales transactions** and includes the following attributes:

- Brand  
- Mobile Model  
- City  
- Payment Method  
- Units Sold  
- Price per Unit  
- Transaction Date  
- Customer Ratings  

🔗 **Dataset Link:**  
👉 [Mobile Sales Dataset (Excel)](https://github.com/himanshujoshitech/Mobile-Sales-Analytics-Dashboard-/blob/main/Mobile%20Sales%20Data.xlsx)  


### 🔧 Data Preparation Steps
- Loaded the dataset using **Power Query**
- Cleaned and transformed raw data
- Removed inconsistencies and null values
- Corrected data types
- Prepared data for modeling and analysis

📌 *Power Query ensures automated, repeatable transformations on refresh.*

---

## 📅 Creating a Custom Calendar using DAX

A **Custom Calendar (Date Table)** was created to enable **time intelligence analysis** and to ensure accurate reporting across different time periods.

### Why a Custom Calendar?
- Enables MTD, QTD, YTD, and YoY calculations
- Provides continuous dates (no missing days)
- Allows proper sorting of months and quarters
- Supports advanced time-based analysis

### DAX Used to Create Calendar
```DAX
Custom_Calendar = 
ADDCOLUMNS(
    CALENDAR (DATE(2022,1,1), DATE(2024,12,31)),
    "Year", YEAR([Date]),
    "Month", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Day Name", FORMAT([Date], "dddd")
)````

---

