# 📱 Mobile Sales Dashboard | Power BI Project

🚀 A complete **end-to-end Power BI project** focused on analyzing mobile sales performance using **advanced data modeling, DAX, and time intelligence techniques**.

This project demonstrates how raw sales data can be transformed into a **professional, interactive, and insight-driven dashboard** suitable for real-world business use.

---

## 🧠 Project Overview

The **Mobile Sales Dashboard** provides deep insights into:
- 📊 Sales performance
- 📦 Quantity sold
- 💳 Payment methods
- 🏙️ City-wise sales
- ⭐ Customer ratings
- 📆 Time-based analysis (MTD, QTD, YTD, Same Period Last Year)

It follows **industry best practices** such as:
- Star Schema data modeling
- Custom Calendar creation
- Advanced DAX measures
- Clean and professional UI design

---

## 🖼️ Dashboard Snapshots

### 🔹 Main Dashboard
![Main Dashboard](Dashboard.png)

### 🔹 MTD (Month-To-Date) Report
![MTD Report](MTD%20Report.png)

### 🔹 Same Period Last Year Analysis
![Same Period Last Year](Same%20Period%20Last%20Year.png)

---

## 📌 Key KPIs Used

- 💰 **Total Sales**
- 📦 **Total Quantity Sold**
- 🔁 **Total Transactions**
- 💵 **Average Price**
- 📈 **MTD / QTD / YTD Sales**
- 📊 **Same Period Last Year Comparison**

---

## 🗂️ Dataset Understanding & Preparation

- Imported raw sales data from Excel
- Cleaned and transformed data using **Power Query**
- Ensured correct data types and removed inconsistencies
- Prepared data for analytical modeling

📌 *Why Power Query?*  
✔ Automated transformations  
✔ Reusable steps  
✔ Error-free refresh  

---

## 📅 Custom Calendar Creation (DAX)

A **Custom Calendar table** was created using DAX to enable:
- Time intelligence calculations
- Continuous date analysis
- Month, Quarter, Year level reporting

```DAX
Calendar = 
ADDCOLUMNS(
    CALENDAR(DATE(2022,1,1), DATE(2024,12,31)),
    "Year", YEAR([Date]),
    "Month", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Day Name", FORMAT([Date], "dddd")
)
