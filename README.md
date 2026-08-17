# M-Pesa Statement Analysis: Personal Financial Transaction Analysis (2024–2026)

## Project Overview

This project presents an exploratory data analysis (EDA) of personal M-Pesa transaction records covering the period from **September 2024 to May 2026**.

The objective is to analyse transaction behaviour, spending patterns, transaction frequency, recipient activity, transaction costs, and changes in financial activity over time.
The analysis was conducted using Python and is documented in a Jupyter Notebook developed in Google Colab.

## Dataset

The dataset used in this project was obtained from my personal **Safaricom M-Pesa transaction statement**, covering transactions from **September 2024 to May 2026**.

### Obtaining the M-Pesa Statement

The transaction statement was obtained directly from my Safaricom M-Pesa account using the **\*334#** USSD service.

The process was:

1. Access the M-Pesa menu using **\*334#** on my Safaricom line.
2. Navigate to the option for requesting/downloading an **M-Pesa statement**.
3. Select the required transaction period, covering **September 2024 to May 2026**.
4. Request the statement and download the resulting statement, which was provided in **PDF format**.

### Converting the Statement to a Usable Dataset

Since the PDF format was not convenient for data analysis, I converted the statement into an Excel-compatible format using **iLovePDF's PDF-to-Excel conversion tool**.

The converted Excel file was then reviewed and prepared for analysis before being imported into Python.

### Original Dataset Structure

The original dataset contained transaction-level information such as:

| Column | Description |
|---|---|
| Completion Time | Date and time when the transaction was completed |
| Transaction Status | Status of the transaction |
| Paid In | Amount received into the M-Pesa account |
| Withdrawn | Amount withdrawn or spent |
| Balance | M-Pesa account balance after the transaction |
| Transaction Type | Category/type of transaction |
| Details | Detailed description of the transaction |

An unnecessary column contained in the converted dataset was removed during the cleaning process.


**Privacy:** The M-Pesa statement used in this analysis is my personal financial data.**The original statement is not included in this public repository**.


## Financial Summary

The analysis calculated the total value of transactions recorded as incoming and outgoing during the study period.

| Metric | Amount |
|---|---:|
| Total Money Received | KES 841,413.98 |
| Total Money Spent | KES 1,349,341.94 |

These figures represent transaction flows recorded in the M-Pesa statement and should not be interpreted directly as personal income and expenditure.

The difference can partly be explained by transactions involving linked bank accounts and other movements of funds between financial accounts.


## Spending by Transaction Type

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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a13b044b-83e4-4886-bebc-33446fd4e514" />


## Monthly Spending Analysis

Monthly withdrawals were aggregated using the `Year-Month` feature.

The analysis covers:


Monthly analysis was used to identify:

- Highest-spending months
- Lowest-spending months
- Changes in expenditure over time
- Periods of unusually high transaction activity
- Longer-term spending patterns

A significant increase in withdrawals was observed during **January and February 2025**, followed by a substantial decline in March 2025.

Spending subsequently showed a more gradual upward pattern during the latter part of 2025 and the first five months of 2026.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2ced92ee-35ff-414a-b204-f076634c97ee" />


## Top Recipients Analysis

Recipient information was extracted from transaction descriptions using **Regular Expressions (Regex)**.

The resulting recipient-level dataset was used to calculate:

- Total amount sent to each recipient
- Number of transactions per recipient
- Top recipients by total amount sent
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6adc5639-8fae-4552-9f7e-42576ce2b635" />



## Time-of-Day Transaction Analysis

A total of **8,290 transactions** were analysed according to time of day.

| Time Period | Number of Transactions |
|---|---|

| Evening | 4,477 |
| Afternoon | 1,735 |
| Midnight | 1,134 |
| Morning | 944 |

### Key Finding

**Evening was the most active transaction period**, accounting for the highest number of transactions.

This indicates that transaction activity was concentrated more heavily during the evening than during the other three periods.


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


├── requirements.txt
└── LICENSE
