# M-Pesa Statement Analysis: Personal Financial Transaction Analysis (2024–2026)

## Project Overview

This project presents an exploratory data analysis (EDA) of personal M-Pesa transaction records covering the period from **September 2024 to May 2026**.

The objective is to analyse transaction behaviour, spending patterns, transaction frequency, recipient activity, transaction costs, and changes in financial activity over time.

The project follows an end-to-end data analytics workflow:

**Data Collection → Data Cleaning → Feature Engineering → Exploratory Data Analysis → Visualization → Insight Generation**

The analysis was conducted using Python and is documented in a Jupyter Notebook developed in Google Colab.

---

## Objectives

The project seeks to answer the following questions:

- How much money was recorded as received during the analysis period?
- How much money was recorded as withdrawn?
- Which transaction types account for the largest share of outgoing transactions?
- Which months recorded the highest and lowest spending?
- What was the highest-spending day?
- On which day was the largest amount received?
- Which recipients received the largest total amounts?
- When during the day are transactions most frequent?
- What were the estimated M-Pesa transaction costs?
- What patterns can be identified from the transaction history?

---

## Dataset

The dataset was derived from personal Safaricom M-Pesa statements covering **September 2024 to May 2026**.

The original statement contained fields including:

- Completion Time
- Transaction Status
- Paid In
- Withdrawn
- Balance
- Transaction Type
- Details

The raw data was processed and transformed into an analysis-ready dataset.

### Data Privacy

Because the dataset contains personal financial information, sensitive identifiers and personally identifiable information should be removed or anonymized before publishing the dataset publicly.

---

## Data Preparation

The raw M-Pesa statement was prepared for analysis through several cleaning and transformation steps.

### Data Cleaning

The following operations were performed:

- Removed unnecessary columns
- Removed the `Unnamed: 7` column
- Handled missing values
- Converted monetary fields to numeric data types
- Converted withdrawal values to positive values for expenditure analysis
- Converted transaction timestamps to datetime format
- Standardized transaction information
- Prepared the dataset for aggregation and visualization

The original transaction direction was retained using the `Paid In`, `Withdrawn`, and `Transaction_Type` fields.

---

## Feature Engineering

Additional variables were derived from the transaction timestamp to support temporal analysis.

| Feature | Description |
|---|---|
| `Completion_Time` | Standardized transaction timestamp |
| `Date` | Transaction date |
| `Time` | Transaction time |
| `Year` | Transaction year |
| `Month Name` | Transaction month |
| `Year-Month` | Combined month and year |
| `Hour` | Hour of transaction |
| `Time_Period` | Time-of-day classification |

### Time-of-Day Classification

Transactions were grouped into four periods:

| Period | Time Range |
|---|---|
| Midnight | 00:00 – 05:59 |
| Morning | 06:00 – 11:59 |
| Afternoon | 12:00 – 17:59 |
| Evening | 18:00 – 23:59 |

This feature was used to determine the most active period for M-Pesa transactions.

---

# Exploratory Data Analysis

## 1. Financial Summary

The analysis calculated the total value of transactions recorded as incoming and outgoing during the study period.

| Metric | Amount |
|---|---:|
| Total Money Received | KES 841,413.98 |
| Total Money Spent | KES 1,349,341.94 |

These figures represent transaction flows recorded in the M-Pesa statement and should not be interpreted directly as personal income and expenditure.

The difference can partly be explained by transactions involving linked bank accounts and other movements of funds between financial accounts.

---

## 2. Spending by Transaction Type

Outgoing transactions were grouped by transaction type to determine which categories accounted for the largest amounts.

The analysis considered categories including:

- Customer Transfer
- Pay Bill
- Merchant Payment
- Bundle Purchase
- Loan Repayment
- Transaction Charges
- Business Payment
- Overdraft
- Other transaction categories

The results were visualized using interactive Plotly charts to facilitate comparison between transaction categories.

---

## 3. Monthly Spending Analysis

Monthly withdrawals were aggregated using the `Year-Month` feature.

The analysis covers:

**September 2024 – May 2026**

Monthly analysis was used to identify:

- Highest-spending months
- Lowest-spending months
- Changes in expenditure over time
- Periods of unusually high transaction activity
- Longer-term spending patterns

A significant increase in withdrawals was observed during **January and February 2025**, followed by a substantial decline in March 2025.

Spending subsequently showed a more gradual upward pattern during the latter part of 2025 and the first five months of 2026.

---

## 4. Daily Transaction Analysis

Daily transaction values were aggregated to identify significant transaction days.

The analysis identifies:

- Highest-spending day
- Amount spent on the highest-spending day
- Largest amount received on a single day
- Daily spending patterns

Daily analysis provides a more granular perspective than monthly aggregation and helps identify individual periods of unusually high financial activity.

---

## 5. Top Recipients Analysis

Recipient information was extracted from transaction descriptions using **Regular Expressions (Regex)**.

The resulting recipient-level dataset was used to calculate:

- Total amount sent to each recipient
- Number of transactions per recipient
- Top recipients by total amount sent

### Highest Recipient by Total Amount

The analysis identified:

**Ali Abdul — KES 127,099.96**

across **671 transactions**.

This analysis also demonstrates the difference between transaction frequency and transaction value. A recipient with a high number of transactions does not necessarily receive the largest individual payments.

---

## 6. Transaction Cost Analysis

Transaction costs were estimated using the applicable M-Pesa tariff structure.

The analysis examined:

- Number of chargeable transactions
- Monthly transaction costs
- Annual transaction costs
- Average transaction cost per day

This provides an estimate of the cumulative cost associated with transaction activity during the study period.

---

## 7. Time-of-Day Transaction Analysis

A total of **8,290 transactions** were analysed according to time of day.

| Time Period | Number of Transactions |
|---|---:|
| Evening | 4,477 |
| Afternoon | 1,735 |
| Midnight | 1,134 |
| Morning | 944 |

### Key Finding

**Evening was the most active transaction period**, accounting for the highest number of transactions.

This indicates that transaction activity was concentrated more heavily during the evening than during the other three periods.

---

# Key Findings

The analysis produced several notable observations:

- The dataset contains **8,290 transactions**.
- Recorded outgoing transaction value exceeded recorded incoming transaction value.
- Linked bank transactions contributed to the movement of funds into and out of the M-Pesa account.
- Customer Transfers represented the largest spending category.
- January and February 2025 recorded substantially higher spending than the surrounding months.
- Transaction activity was highest during the evening.
- A relatively small number of recipients accounted for a significant proportion of outgoing transaction value.
- Transaction charges accumulated over the analysis period.
- Temporal analysis revealed changes in transaction behaviour across months and times of day.

---

# Visualizations

The project includes a combination of static and interactive visualizations.

Key visualizations include:

- Spending by Transaction Type
- Monthly Spending Trend
- Daily Spending Trend
- Top 10 Recipients
- Time-of-Day Transaction Activity
- Transaction Cost Analysis
- Highest Spending Day
- Largest Amount Received
- Spending Distribution

Interactive Plotly visualizations allow individual values and categories to be explored directly from the charts.

---

# Tools and Technologies

| Technology | Application |
|---|---|
| Python | Data analysis and processing |
| Pandas | Data manipulation and aggregation |
| NumPy | Numerical operations |
| Matplotlib | Static visualization |
| Seaborn | Statistical visualization |
| Plotly | Interactive visualization |
| Regular Expressions | Recipient extraction |
| Google Colab | Development environment |
| Jupyter Notebook | Analysis documentation |

---

# Project Structure

```text
mpesa-statement-analysis/
│
├── data/
│   ├── mpesa.csv
│   └── cleaned_mpesa.csv
│
├── notebook/
│   └── mpesa_analysis.ipynb
│
├── images/
│   ├── spending_categories.png
│   ├── monthly_spending.png
│   ├── daily_spending.png
│   ├── top_recipients.png
│   └── transaction_time.png
│
├── README.md
├── requirements.txt
└── LICENSE
