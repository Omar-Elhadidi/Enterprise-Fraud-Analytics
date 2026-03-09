# Enterprise Fraud Analytics Architecture

## 📌 Project Overview
This project is a robust, relational database architecture designed to simulate an enterprise-level banking environment. The objective was to build a data pipeline that generates, ingests, and analyzes high-volume financial data to detect anomalous (potentially fraudulent) behavior. 

Built to demonstrate database design, data integrity enforcement, and highly optimized, advanced SQL querying (CTEs, Window Functions, and multi-table Joins) for Data Engineering.

## 🛠️ Tech Stack & Architecture
* **Data Generation:** Python (`Faker`, `Pandas`) to script 50,000+ rows of realistic mock data.
* **Database Engine:** MySQL.
* **Schema Design:** 3rd Normal Form (3NF) Relational Database.

## 🗄️ Database Schema
The database consists of three core tables linked via Primary and Foreign keys:
1. **Customers:** The core dimension table containing demographic data and risk scores.
2. **Accounts:** Linked to Customers, tracking account types and balances.
3. **Transactions:** The central fact table logging 50,000 individual financial events.

## 📊 Key Analytics & SQL Logic

### 1. The Anomaly Detector (Using CTEs)
**Objective:** Identify transactions drastically higher than a customer's normal spending habits.
<img width="1603" height="865" alt="Screenshot 2026-03-09 154542" src="https://github.com/user-attachments/assets/abf46bb6-27e9-487f-814d-fb59d6c98e7e" />


### 2. Geographical Fraud Profiling
**Objective:** Create a high-level BI summary of fraud losses grouped by country.
<img width="1595" height="603" alt="Screenshot 2026-03-09 155044" src="https://github.com/user-attachments/assets/b61aeba3-d2bc-4574-a7a9-752c1adef669" />


### 3. Time-Series Running Totals
**Objective:** Calculate the running total of fraudulent spending per account over time using Window Functions.
<img width="1608" height="805" alt="Screenshot 2026-03-09 155112" src="https://github.com/user-attachments/assets/d6b493cd-6311-4b68-a067-b2f185d3dda4" />


### 4. ETL Daily Summary View
**Objective:** Transform raw transaction logs into a daily summary view for dashboarding.
<img width="1602" height="696" alt="Screenshot 2026-03-09 155350" src="https://github.com/user-attachments/assets/296ae392-14d9-4595-8e4b-343d4c7f4690" />


## 🚀 How to Run Locally
1. Run `generate_bank_data.py` to generate the raw CSV files.
2. Execute `database_schema.sql` to build the schema.
3. Import the CSVs: `Customers` -> `Accounts` -> `Transactions`.
4. Run `analysis_queries.sql` to generate insights.
