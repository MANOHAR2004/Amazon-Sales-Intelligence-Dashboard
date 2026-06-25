# 🛒 Amazon Sales Intelligence Dashboard
### Excel-Based Business Analytics Project | Career247 Week 03

![Dashboard Preview](<img width="1575" height="642" alt="image" src="https://github.com/user-attachments/assets/639b8b7c-a0b0-4d17-8916-8fc46d05c8de" />

)
![Dashboard Demo](<img width="1131" height="701" alt="Excel_dashboard_demo" src="https://github.com/user-attachments/assets/566fee4b-64c0-430d-ac48-14e20f9c51b9" />

)
---

## 📌 Project Overview

This project simulates a real-world Business Analyst task at **Amazon Retail Partners**. Raw sales data of 100 transactions was transformed into a fully interactive Excel dashboard using data cleaning, cross-sheet lookups, Pivot Tables, KPI cards, and dynamic slicers.

**Role:** Reporting Analyst  
**Tool:** Microsoft Excel  
**Dataset:** 100 Amazon Sales Transactions (2023)  
**Sheets:** AmazonSales | ProductMaster | CustomerMaster | Pivot Tables | KPI Metrics | Dashboard | Issue Log

---

## 🎯 Objectives

- Clean and standardize raw sales data for analysis
- Engineered calculated features for deeper insights
- Connect data across multiple sheets using INDEX MATCH
- Summarize data using Pivot Tables
- Design an interactive dashboard with KPI cards and slicers

---

## 🛠️ Tools & Techniques Used

| Technique | Application |
|---|---|
| **Data Cleaning** | Trailing spaces, standardizing values, fixing Total Amount integrity issue |
| **INDEX MATCH** | Cross-sheet lookup for Category, Product Name, Customer Name, Customer Type |
| **Feature Engineering** | Days_to_Delivery, Delivery_Performance (Fast/Slow/N/A), Delivery_Stage |
| **Pivot Tables** | Revenue by Region & Category, Orders by Delivery Status, Avg Delivery Time |
| **KPI Metrics** | Total Revenue, % Fast Deliveries, Top 3 Regions, Highest Selling Product |
| **Dashboard Design** | Dark theme, teal KPI cards, interactive slicers, Pivot Charts |
| **Issue Log** | 13-issue professional data quality documentation |

---

## 📊 Key Business Insights

| KPI | Value |
|---|---|
| 💰 Total Revenue | ₹35,258 |
| 🚀 Fast Deliveries | 32% of delivered orders |
| 🏆 Top Region | North (₹10,491) |
| 📦 Top Product | Smartphone (Electronics) |
| ⚠️ Cancellation Rate | 30% — highest in North region |
| ⏱️ Avg Delivery Time | 3.76 days overall |

---

## 🔍 Brainstorming Reflection

**Q1. Most successful product category by revenue?**  
Electronics with ₹15,209 — significantly ahead of other categories.

**Q2. Which region has the highest cancellation rate?**  
North region with 10 cancelled orders (~45% cancellation rate).

**Q3. How many orders were delivered within 2 days?**  
11 orders (32% of all delivered orders classified as Fast).

**Q4. How did INDEX MATCH simplify cross-sheet analysis?**  
Instead of manually searching ProductMaster and CustomerMaster sheets, INDEX MATCH automatically pulled Category, Product Name, Customer Name, and Customer Type into AmazonSales — saving time and eliminating manual errors across 100 rows. *(Note: Used INDEX MATCH as a substitute for XLOOKUP due to Excel version compatibility.)*

**Q5. Recommendations to improve delivery performance?**
- Central and East have the highest average delivery times (4.20 and 4.25 days) → prioritize fulfillment partners in these regions
- 30% cancellation rate is critically high → investigate root causes by region
- Only 32% fast deliveries → set operational target of 60%+
- DHL appears frequently in cancelled orders → audit DHL fulfillment performance

---

## 📁 Project Structure

```
Amazon-Sales-Intelligence-Dashboard/
│
├── Amazon_Sales_Dashboard_Manohar_Choudhary.xlsx
│   ├── AmazonSales         # Cleaned data + engineered features
│   ├── ProductMaster       # Product reference data
│   ├── CustomerMaster      # Simulated customer reference data
│   ├── Pivot_table_sheet   # 3 Pivot Tables
│   ├── KPI's metrix        # KPI calculations
│   ├── Dashboard           # Final interactive dashboard
│   └── Issue_log           # 13-issue data quality log
│
├── dashboard_screenshot.png
└── README.md
```

---

## 🧹 Data Cleaning Summary

| # | Issue | Severity | Resolution |
|---|---|---|---|
| 1 | Trailing spaces in Region | Low | Created Region_fixed column |
| 2 | Trailing spaces in Payment Method | Low | Created Payment_Method_fixed column |
| 3 | Inconsistent Delivery Status values | Medium | Mapped to standardized values |
| 4 | Blank Delivery Dates (cancelled orders) | Medium | Handled with IFERROR |
| 5 | Total Amount integrity error | 🔴 High | Recalculated as Sale Price × Quantity |
| 6 | CUST050 missing from CustomerMaster | Medium | Added as simulated data |
| + 7 more | Documented in Issue Log | — | See Issue_log sheet |

---

## 💡 What I Learned

- How to approach real-world messy data with a structured cleaning pipeline
- Professional issue logging as practiced in BA/DA roles
- Cross-sheet data modeling using INDEX MATCH
- Dashboard design principles — layout, KPI cards, color theming
- Translating raw numbers into actionable business recommendations

---

## 👤 About Me

**Manohar Choudhary**  
MBA (Marketing) | IMS DAVV Indore  
Aspiring Data Analyst & Business Analyst

📧 Connect with me on [LinkedIn](#)  
💻 More projects on [GitHub](MANOHAR2004)

---

*This project was independently completed as part of my Data Analytics learning journey.*
