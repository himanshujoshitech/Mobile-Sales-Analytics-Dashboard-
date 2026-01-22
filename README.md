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
)
```

---

## 🔗 Building Relationships in the Data Model View

After creating the custom calendar, relationships were built following **Star Schema best practices** to ensure accurate analysis and optimal performance.

### 📋 Tables Involved

- **Fact Table:** `Sales_Data`  
  - Contains transaction-level data  
  - Stores numerical metrics such as *Units Sold, Price per Unit, Sales Amount*

- **Dimension Table:** `Custom_Calendar`  
  - Contains date-related attributes such as *Date, Month, Quarter, Year, Day Name*

### 🔗 Relationship Setup

```text
Custom_Calendar[Date]  →  Sales_Data[Date]
```
📌 This relationship ensures accurate **date filtering** and enables all **time intelligence calculations** such as **MTD, QTD, YTD, and Year-over-Year analysis**.

---

## 🧮 Writing Essential DAX Measures

DAX (Data Analysis Expressions) was used to create **core measures** that power all KPIs across the dashboard.

### 🔹 Total Sales

```DAX
Total Sales =
SUMX(
    Sales_Data,
    Sales_Data[Units Sold] * Sales_Data[Price Per Unit]
)
```

### 🔹 Total Quantity Sold

```DAX
Total Quantity Sold =
SUM(Sales_Data[Units Sold])
```

### 🔹 Total Transactions

```DAX
Total Transactions =
COUNT(Sales_Data[Transaction ID])
```

### 🔹 Average Price

```DAX
Average Price =
AVERAGE(Sales_Data[Price Per Unit])
```

📌 These measures serve as the base metrics for analysis and reporting.

---

## 🎛️ Using Edit Interactions

Edit Interactions were used to control how visuals interact with each other on the report page.

- Enabled filtering where cross-analysis was required  
- Disabled interactions for KPI cards to prevent distortion  
- Improved dashboard clarity and overall usability  

📌 This ensures that users focus only on **relevant insights** and avoids unnecessary visual disturbances.

---

## 🎨 Designing a Professional Dashboard

The dashboard was designed with **business users and decision-makers** in mind, focusing on clarity, usability, and a modern look.

### 🎯 Design Highlights

- Clean and consistent color theme  
- Rounded corners for a modern UI  
- KPI cards for quick, high-level insights  
- Logical visual placement and alignment  
- Locked visuals using **Selection Pane** to avoid accidental movement  

✔ Main Dashboard  
✔ MTD Report  
✔ Same Period Last Year Report  

📌 The design ensures the dashboard is **easy to understand, visually appealing, and business-ready**.

---

## 🧪 Using the DAX Query View

The **DAX Query View** was used to:

- Test and validate DAX measures independently  
- Debug and verify calculation logic  
- Improve confidence before using measures in report visuals  

📌 This step helped ensure **accuracy and reliability** of all calculations.

---


## 🎯 Key Outcomes & Learnings

- Strong understanding of **data modeling principles**  
- Hands-on experience with **DAX and time intelligence functions**  
- Ability to design **professional and interactive Power BI dashboards**  
- Practical experience with **Power BI Service deployment**

---

## 🧾 Conclusion

This project demonstrates the ability to:

- Transform raw data into actionable business insights  
- Apply real-world **Power BI best practices**  
- Build scalable, interactive, and performance-optimized dashboards  
- Think analytically from a **business intelligence perspective**

⭐ *If you found this project useful, feel free to star the repository!* ⭐
