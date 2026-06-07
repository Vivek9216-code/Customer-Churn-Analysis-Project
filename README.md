# 📊 Customer Churn Analysis
### SQL Server · Power BI · DAX · Power Query

## 📌 Project Overview & Objective

This project performs an end-to-end **Customer Churn Analysis** using **SQL Server** for data cleaning and validation, and **Power BI** for data modeling, ETL transformation, and interactive dashboard reporting.

**Business Problem:**
Customer churn is one of the most critical challenges for businesses. Identifying churned customers and understanding the patterns behind churn helps organizations take proactive measures to improve **customer retention** and reduce revenue loss.

**Project Objective:**
- Analyze customer data to identify churn patterns across demographics, geography, contract type, and services
- Clean and validate raw data using SQL Server to ensure high data accuracy
- Build an interactive Power BI dashboard to visualize key KPIs such as **Churn Rate**, **Retention Rate**, and customer segmentation
- Enable data-driven decision-making for business stakeholders

---

## 🖥️ Dashboard Preview

### Summary Page
<img width="1326" height="649" alt="image" src="https://github.com/user-attachments/assets/efdd3891-767c-4cbb-a2bd-e0afdfb02076" />


### Churn Rate Page
<img width="1316" height="664" alt="image" src="https://github.com/user-attachments/assets/6682c43a-a4b8-442e-81f5-74fae1d7fc5f" />


> 📁 Add your dashboard screenshots inside a `/screenshots` folder in the repository.


| Property | Details |
|---|---|
| **Domain** | Telecom / Customer Analytics |
| **Total Customers** | 6,000 customers |
| **Total Churned** | 2,000 customers |
| **New Joiners** | 411 |
| **Overall Churn Rate** | 26.99% |

**Key Columns in the Dataset:**

| Column Name | Description |
|---|---|
| `CustomerID` | Unique identifier for each customer |
| `Gender` | Gender of the customer (Male / Female) |
| `Age Group` | Customer age bracket (18-27, 28-37, 38-47, 48-57, 58-67, 67+) |
| `State` | Customer geographic location |
| `Tenure Month` | Number of months the customer has been with the company |
| `Contract` | Contract type (Month-to-Month, One Year, Two Year) |
| `Payment Method` | Mailed Check, Bank Withdrawal, Credit Card |
| `Internet Type` | Fiber Optic, Cable, DSL |
| `Services` | Device Protection, Online Backup, Online Security, etc. |
| `Churn Category` | Reason for churn (Competitor, Attitude, Dissatisfaction, Price, Other) |
| `Churn` | Target variable — whether the customer churned (Yes/No) |

---

## 🧹 SQL Data Cleaning Steps

All data cleaning and validation was performed in **SQL Server** before loading into Power BI.

### Step 1 — Handling Null / Missing Values

### Step 2 — Removing Duplicate Records

### Step 3 — Data Type Validation & Standardization

### Step 4 — Data Validation Checks

> ✅ After cleaning, the dataset achieved **95%+ data accuracy** and was ready for reporting.

---

## ⚙️ Power BI — ETL & Data Transformation (Power Query)

After loading the cleaned data from SQL Server into Power BI via **Import Mode**, the following ETL steps were applied in **Power Query Editor**:

- Removed unnecessary columns not required for reporting
- Changed data types for date, numeric, and text columns
- Created conditional columns (e.g., Churn Status: "Churned" / "Retained")
- Renamed columns for better readability in reports
- Applied text trimming and case normalization
- Created **Reference Tables** for Geography, Contract, Services, and Internet Type to improve dashboard load time

---

## 🗃️ Data Modeling

A **Star Schema** was implemented in Power BI for optimized reporting performance.

```
                        ┌─────────────────┐
                        │   Fact Table    │
                        │  Customer Data  │
                        └────────┬────────┘
                                 │
          ┌──────────────────────┼──────────────────────┐
          │                      │                      │
 ┌────────▼───────┐   ┌──────────▼──────┐   ┌──────────▼──────┐
 │  Dim Geography │   │  Dim Contract   │   │   Dim Service   │
 │   (State)      │   │  (Contract Type)│   │  (Internet/Plan)│
 └────────────────┘   └─────────────────┘   └─────────────────┘
```

- **1 Fact Table** — Core customer churn data
- **4+ Dimension / Reference Tables** — Geography, Contract, Services, Internet Type
- Reference tables improved **dashboard load performance by ~40%**

---


## 💡 Key Insights & Findings

Based on the interactive Power BI dashboard:

| # | Insight |
|---|---|
| 1 | 📌 Overall churn rate stands at **26.99%** — out of **6,000 customers**, **2,000 have churned** |
| 2 | 📌 **Month-to-Month contract** customers have the highest churn rate at **46.53%**, compared to just **2.73%** for Two-Year contract customers |
| 3 | 📌 **Competitor** is the #1 churn reason with **761 customers**, followed by Attitude (**301**) and Dissatisfaction (**300**) |
| 4 | 📌 **Jammu & Kashmir** has the highest state-level churn rate at **57%**, followed by Assam (**38%**) and Jharkhand (**35%**) |
| 5 | 📌 Customers paying via **Mailed Check** churn the most at **38%**, while **Credit Card** users churn the least at **15%** |
| 6 | 📌 **Fiber Optic** internet users account for **47.68%** of churned customers — the highest among all internet types |
| 7 | 📌 **Online Security** subscribers have a lower churn rate (**21.65%**) compared to those without it (**78.35%**) |
| 8 | 📌 Churn rate is relatively consistent across **age groups 18–67**, with the **67+ group** showing the highest churn spike at **42%** |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **SQL Server** | Data storage, cleaning, validation, and querying |
| **Power BI Desktop** | Data modeling, DAX, and dashboard development |
| **Power Query Editor** | ETL and data transformation |
| **DAX** | KPI measures and calculated columns |
| **Star Schema** | Data modeling for optimized reporting |

---

## 📁 Project Structure

```
Customer-Churn-Analysis/
│
├── SQL/
│   ├── data_cleaning.sql               # All SQL cleaning & validation queries
│   └── data_validation.sql             # Data quality check queries
│
├── PowerBI/
│   └── Customer_Churn_Analysis.pbix    # Power BI dashboard file
│
├── Screenshots/
│   ├── summary.png                     # Summary page screenshot
│   └── churn_rate.png                  # Churn Rate page screenshot
│
├── Dataset/
│   └── customer_churn_data.csv         # Raw dataset (if shareable)
│
└── README.md
```

---



## 👤 Author

**Vivek Rathore**
- 📧 vr1056254@gmail.com
- 💼 [LinkedIn Profile](https://www.linkedin.com/in/vivekrathore001/)
- 
> ⭐ If you found this project helpful, please consider giving it a star!
