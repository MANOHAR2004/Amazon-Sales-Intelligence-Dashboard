# Amazon Sales Intelligence Dashboard

**Excel business analytics project | Data cleaning, INDEX MATCH, Pivot Tables, KPI cards and slicers**

![Dashboard Preview](<img width="1575" height="642" alt="image" src="https://github.com/user-attachments/assets/639b8b7c-a0b0-4d17-8916-8fc46d05c8de" />

)
![Dashboard Demo](<img width="1131" height="701" alt="Excel_dashboard_demo" src="https://github.com/user-attachments/assets/566fee4b-64c0-430d-ac48-14e20f9c51b9" />

)
---

## Project Overview

This project takes a raw sales table of **100 orders (2023)** and turns it into a cleaned, documented Excel workbook with an interactive dashboard. It follows the workflow of a reporting analyst: check data quality, fix problems, join reference tables, summarise with Pivot Tables, and present KPIs that a manager can act on.

- **Type:** Practice project on a practice dataset. It is not real Amazon data and was not done for a client.
- **Tool:** Microsoft Excel
- **Dataset:** 100 sales orders (order, delivery and cancel dates, region, product, price, quantity, payment method, delivery status, fulfilment partner)
- **Customer data:** The CustomerMaster sheet is simulated reference data. CUST050 was missing from it and was added as simulated data.

## Business Questions

1. How much order value did each region, category and product generate?
2. What share of orders were cancelled, and where?
3. How fast are orders delivered, and which regions are slowest?
4. Do any fulfilment partners stand out on cancellations?

## Workbook Structure

| Sheet | Purpose |
|---|---|
| AmazonSales | Cleaned order data plus engineered columns |
| ProductMaster | Product reference data (category, product name) |
| CustomerMaster | Customer reference data (simulated) |
| RegionGoals | Regional reference data |
| Pivot_table_sheet | Pivot Tables behind the dashboard |
| KPI's metrix | KPI calculations |
| Dashboard | Final interactive dashboard (KPI cards, Pivot Charts, slicers) |
| Brainstorming | Business questions and written answers |
| Issue_Log | 12 documented data-quality issues |

## Tools and Techniques

| Technique | Where it was used |
|---|---|
| Data cleaning | Trimmed spaces in Region and Payment Method, standardised delivery status values, fixed a wrong Total Amount column |
| INDEX MATCH | Pulled Category, Product Name, Customer Name and Customer Type into the sales sheet |
| Feature engineering | `Days to delivery`, `Delivery_perfomance` (Fast = delivered in 2 days or less, otherwise Slow, N/A if not delivered), `Delivery_level1` |
| Pivot Tables | Order value by region and category, orders by delivery status, average delivery time |
| KPI cards | Total order value, % fast deliveries, top 3 regions, top product by revenue |
| Dashboard design | Dark theme, teal KPI cards, slicers (Category, Region, Delivery Status, Payment Method) and Pivot Charts |
| Issue log | Each problem recorded with severity, cause, fix and business impact |

> INDEX MATCH was used instead of XLOOKUP because of Excel version compatibility.

## Key Findings

All figures were checked against the cleaned data (100 orders).

| KPI | Value |
|---|---|
| Total order value (all orders, including cancelled and in transit) | ₹35,258 |
| Order value excluding cancelled orders | ₹28,297 |
| Order value from delivered orders only | ₹13,656 |
| Order status | 34 delivered, 36 in transit, 30 cancelled |
| Overall cancellation rate | 30% |
| Fast deliveries (2 days or less) | 11 of 34 delivered orders (32%) |
| Average delivery time (delivered orders) | 3.76 days |
| Top category by order value | Electronics, ₹15,209 |
| Top region by order value | North, ₹10,491 (then West ₹8,359, South ₹7,317) |
| Top product by revenue | Smartphone, ₹9,644 |
| Top product by units sold | Cookware Set Pro, 24 units |

### Cancellation rate by region

| Region | Cancelled orders | Total orders | Rate |
|---|---|---|---|
| North | 10 | 25 | 40.0% |
| Central | 5 | 14 | 35.7% |
| West | 8 | 23 | 34.8% |
| South | 4 | 20 | 20.0% |
| East | 3 | 18 | 16.7% |

### Average delivery time by region (delivered orders)

| Region | Days |
|---|---|
| East | 4.25 |
| Central | 4.20 |
| North | 3.62 |
| West | 3.43 |
| South | 3.33 |

### Cancellation rate by fulfilment partner

| Partner | Cancelled | Orders | Rate |
|---|---|---|---|
| USPS | 5 | 14 | 35.7% |
| DHL | 7 | 21 | 33.3% |
| FedEx | 5 | 15 | 33.3% |
| Amazon Logistics | 8 | 29 | 27.6% |
| UPS | 5 | 21 | 23.8% |

## Brainstorming Reflection

**Q1. Which product category earned the most?**
Electronics, with ₹15,209 of total order value (₹13,035 after excluding cancelled orders). It stays first either way.

**Q2. Which region has the highest cancellation rate?**
North, with 10 cancelled orders out of 25 (40%). The overall rate is 30%.

**Q3. How many delivered orders arrived within 2 days?**
11 of 34 delivered orders (32%).

**Q4. How did INDEX MATCH help?**
It pulled category, product name, customer name and customer type from the master sheets into the sales sheet. This replaced manual lookups across 100 rows and removed copy errors.

**Q5. What would improve delivery performance?**
- Central (4.20 days) and East (4.25 days) are the slowest regions, so review fulfilment in these two first.
- North, Central and West have the highest cancellation rates (35% to 40%). The data has no cancellation reason, so the next step is to collect one.
- Only 32% of delivered orders are fast. The business should set a target based on its service goals.
- No fulfilment partner clearly stands out on cancellations. Rates range from 24% to 36% on only 14 to 29 orders each, so this sample is too small to blame one partner.

## Data Cleaning Summary (12 issues logged)

| # | Issue | Severity | Resolution |
|---|---|---|---|
| DQ-001 | Trailing spaces in Region | Low | Created `Region_fixed` |
| DQ-002 | Trailing spaces in Payment Method | Low | Created `Payment Method_fixed` |
| DQ-003 | Inconsistent Delivery Status values | Medium | Standardised and mapped to a new stage column |
| DQ-004 | Blank Delivery Date (66 cancelled or in-transit orders) | Medium | Expected. Handled with IFERROR |
| DQ-005 | Blank Cancel Date (70 delivered or in-transit orders) | Low | Expected. Left blank on purpose |
| DQ-006 | `Days to delivery` needed | Low | Calculated from Order Date and Delivery Date |
| DQ-007 | `Delivery_perfomance` needed | Low | Fast, Slow or N/A rule added |
| DQ-008 | Total Amount wrong (44 on every row) | High | Created `Total_amount_fixed` = Sale Price × Quantity |
| DQ-009 | Category not in sales sheet | Low | INDEX MATCH on ProductMaster |
| DQ-010 | Product Name not in sales sheet | Low | INDEX MATCH on ProductMaster |
| DQ-011 | Customer Name not in sales sheet | Low | INDEX MATCH on CustomerMaster |
| DQ-012 | Customer Type not in sales sheet | Low | INDEX MATCH on CustomerMaster |

Full details are in the **Issue_Log** sheet.

## Limitations

- The dataset is small (100 orders), so percentages move a lot with one or two orders.
- "Total order value" includes cancelled and in-transit orders. Net revenue (excluding cancelled orders) is ₹28,297.
- The data has no cancellation reason, so the reasons behind cancellations cannot be analysed.
- Order status is a single snapshot. In-transit orders may still be delivered or cancelled later.
- The customer reference data is simulated.

## What I Learned

- Checking and documenting data quality before any analysis
- Joining data across sheets with INDEX MATCH
- Building Pivot Tables, KPI cards and slicers into one dashboard
- Defining each KPI clearly (what counts as Fast, Cancelled and Revenue)
- Checking my own numbers and correcting claims the data did not support

## Skills Demonstrated

Excel (Pivot Tables, Pivot Charts, slicers, INDEX MATCH, IFERROR, conditional logic), data cleaning, KPI design, dashboard design, issue logging, business recommendations.

## Repository Files

```
Amazon-Sales-Intelligence-Dashboard/
├── Amazon_Sales_Dashboard_Manohar_Choudhary.xlsx
├── dashboard_screenshot.png
└── README.md
```

## About Me

**Manohar Choudhary**
MBA (Marketing), IMS DAVV Indore | Aspiring Data Analyst and Business Analyst

- LinkedIn: [linkedin.com/in/manohar-choudhary](https://www.linkedin.com/in/manohar-choudhary)
- GitHub: [github.com/MANOHAR2004](https://github.com/MANOHAR2004)

*This project was completed independently as part of my data analytics learning.*
