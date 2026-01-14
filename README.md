# supply-chain-analysis-tableau-prep

🧹 Nova Retailers – Data Cleaning & Preparation using Tableau Prep
📌 Project Overview

Nova Retailers is a mid-sized e-commerce company offering products ranging from gadgets to home goods. Although sales have increased over the last two quarters, profits have not grown proportionally. Leadership suspects that product returns, customer segmentation issues, and inconsistent order data across multiple regions are impacting profitability.

This project focuses on cleaning, standardizing, and preparing order and return data from multiple regional sources using Tableau Prep, creating a single, analysis-ready dataset for dashboarding and insights.

🎯 Objective

Clean and standardize inconsistent order data from multiple regions

Resolve schema mismatches across datasets

Enrich data with calculated fields for analysis

Prepare a final unified dataset for Tableau Public dashboards

🛠️ Tools & Technologies

Tableau Prep Builder – Data cleaning, transformation, and joins

Excel / CSV – Source and output datasets

GitHub – Version control and documentation

📂 Data Sources

orders_central

orders_east

orders_west

orders_south

products

return_reasons

Each source had different schemas, formats, and data quality issues, requiring extensive preprocessing.

🔧 Data Cleaning & Transformation Steps
🧩 Orders – Central

Added Region field using a calculated field mapped from Central reference sheet

Created Order Date using MAKEDATE(order_year, order_month, order_day)

Created Ship Date using MAKEDATE(ship_year, ship_month, ship_day)

Removed separate order and ship year/month/day columns

Replaced NULL discounts with 0

Converted Discount field to Decimal

🧩 Orders – East

Removed "USD" from Sales

Converted Sales field to Decimal

🧩 Orders – West

Removed all duplicate and redundant fields

🔗 Union & Integration

Unioned all cleaned order sheets:

orders_central

orders_east

orders_west

orders_south

Resolved mismatched column names and data types

Removed duplicate fields post-union

🔄 Returns Data Processing

Connected Return Reasons sheet

Removed leading and trailing white spaces from Customer Notes

Extracted Approver Name from Customer Notes

Grouped approver names using common character grouping

Converted Customer Notes to Title Case

Left Joined Return Reasons with unioned orders data

Added Return Status field:

Returned

Not Returned

⏱️ Feature Engineering

Created Order to Shipment Days field

DATEDIFF('day', Order Date, Ship Date)

🧹 Final Cleanup

Removed duplicate fields between Products and Orders

Ensured consistent naming conventions

Validated data types across all columns

📤 Final Output

Exported the cleaned and unified dataset to Excel (.xlsx)

Used as the data source for Tableau Public dashboards:

Sales & Performance Dashboard

Customer & Returns Dashboard

📁 Project Files

📄 Nova_Retailers_Data_Cleaning.tfl – Tableau Prep Flow

📄 Cleaned_Output.xlsx – Final dataset for analysis

📄 README.md – Project documentation

🚀 Key Outcomes

Eliminated inconsistencies across regional order datasets

Standardized dates, sales, discounts, and customer text fields

Enabled accurate analysis of returns, shipping delays, and customer behavior

Created a reusable ETL-style data preparation workflow

🧠 Skills Demonstrated

Data Cleaning & Preparation

Tableau Prep Flows

Schema Alignment & Unioning

Joins & Feature Engineering

Text Cleaning & Standardization

Analytical Thinking for Business Use Cases
