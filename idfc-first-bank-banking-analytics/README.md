# IDFC FIRST Bank: Banking Analytics Dashboards (Excel and Power BI)

An end-to-end data analytics project that cleans two banking datasets and turns them into interactive dashboards, built twice: once in **Microsoft Excel** and once in **Microsoft Power BI**. The dashboards use IDFC FIRST Bank's maroon and white colour theme.

> This is an academic group project. It is not affiliated with or endorsed by IDFC FIRST Bank. The bank name, logo and brand colours belong to IDFC FIRST Bank and are used here only to give the dashboards a realistic look.

---

## Table of contents
1. [Project overview](#project-overview)
2. [Dashboards](#dashboards)
3. [KPIs covered](#kpis-covered)
4. [Key insights](#key-insights)
5. [Data preparation](#data-preparation)
6. [Assumptions and definitions](#assumptions-and-definitions)
7. [How it was built](#how-it-was-built)
8. [Repository structure](#repository-structure)
9. [How to open the files](#how-to-open-the-files)
10. [Limitations](#limitations)
11. [Author](#author)

---

## Project overview

| | Bank loan analytics | Debit and credit analytics |
|---|---|---|
| **Records** | 65,535 loans, 52 columns | 100,000 transactions, 12 columns |
| **Period** | Disbursements FY 2017 to FY 2020 | 1 January 2024 to 1 December 2024 |
| **Coverage** | 14 bank codes, 112 branches, 16 states | 6 banks, 6 branches |
| **KPIs** | 18 | 12 |
| **Dashboards** | Excel (1 sheet) and Power BI (3 pages) | Excel (1 sheet) and Power BI (3 pages) |

**Goals**
- Clean and validate the raw data so every number can be trusted.
- Turn the KPI requirements into clear visuals with a Bank Name filter on every dashboard.
- Build the same dashboards in Excel and Power BI, and check that both show identical numbers.

---

## Dashboards

### 1. Bank loan analytics: Excel
![Excel loan dashboard, top section](images/excel-loan-dashboard-1.png)
![Excel loan dashboard, middle section](images/excel-loan-dashboard-2.png)
![Excel loan dashboard, branch-wise revenue](images/excel-loan-dashboard-3.png)

### 2. Debit and credit analytics: Excel
![Excel debit and credit dashboard, overview](images/excel-debit-credit-dashboard-1.png)
![Excel debit and credit dashboard, branch, bank and risk](images/excel-debit-credit-dashboard-2.png)

### 3. Bank loan analytics: Power BI
**Page 1: Portfolio Overview**
![Power BI loan dashboard, Portfolio Overview](images/powerbi-loan-overview.png)

**Page 2: Portfolio Mix**
![Power BI loan dashboard, Portfolio Mix](images/powerbi-loan-mix.png)

**Page 3: Portfolio Branch (risk and branch revenue)**
![Power BI loan dashboard, Portfolio Branch](images/powerbi-loan-branch.png)

### 4. Debit and credit analytics: Power BI
**Page 1: Cash Flow Overview**
![Power BI debit and credit dashboard, Cash Flow Overview](images/powerbi-debit-credit-overview.png)

**Page 2: Branch and Bank**
![Power BI debit and credit dashboard, Branch and Bank](images/powerbi-debit-credit-branch-bank.png)

**Page 3: Risk Monitoring**
![Power BI debit and credit dashboard, Risk Monitoring](images/powerbi-debit-credit-risk.png)

---

## KPIs covered

### Bank loan dashboard (18 KPIs)

| # | KPI | Visual |
|---|---|---|
| 1 | Total Loan Amount Funded | Card |
| 2 | Total Loans | Card |
| 3 | Total Collection | Card |
| 4 | Total Interest | Card |
| 5 | Branch-Wise (Interest, Fees, Total Revenue) | Table and chart |
| 6 | State-Wise Loan | Bar chart |
| 7 | Religion-Wise Loan | Donut chart |
| 8 | Product Group-Wise Loan | Bar chart |
| 9 | Disbursement Trend | Line chart |
| 10 | Grade-Wise Loan | Column chart |
| 11 | Count of Default Loan | Card |
| 12 | Count of Delinquent Clients | Card |
| 13 | Delinquent Loans Rate | Card |
| 14 | Default Loan Rate | Card |
| 15 | Loan Status-Wise Loan | Bar chart |
| 16 | Age Group-Wise Loan | Column chart |
| 17 | No Verified Loan | Card |
| 18 | Loan Maturity | Stacked bar or pie |

### Debit and credit dashboard (12 KPIs)

| # | KPI | Visual |
|---|---|---|
| 1 | Total Credit Amount | Card |
| 2 | Total Debit Amount | Card |
| 3 | Credit to Debit Ratio | Card |
| 4 | Net Transaction Amount | Card |
| 5 | Account Activity Ratio | Card |
| 6 | Transactions per Day / Week / Month | Line chart with Day, Week and Month switch |
| 7 | Total Transaction Amount by Branch | Bar chart |
| 8 | Transaction Volume by Bank | Bar chart |
| 9 | Transaction Method Distribution | Donut chart |
| 10 | Branch Transaction Growth | Column chart (October and November 2024) |
| 11 | High-Risk Transaction Flag | Table |
| 12 | Suspicious Transaction Frequency | Column chart by month |

---

## Key insights

**Bank loan data**
- ₹73.27 crore was funded across 65,535 loans, with ₹81.49 crore collected and ₹15.53 crore earned as interest.
- Funding peaked in FY 2019 at ₹41.81 crore, then fell in FY 2020 (₹6.05 crore).
- About 55% of loans are still active (36,351 loans) and about 70% have a 36-month term.
- 10.84% of loans are delinquent (7,106) and 1.56% are in default (1,020). 16,921 loans are marked as not verified.
- Uttar Pradesh has the most loans (12,412), followed by Punjab and Bihar. Product code XLG makes up about 87% of all loans.
- About 39% of loans (25,818) have no grade recorded.
- Mathura is the top branch by total revenue (about ₹52.9 lakh).

**Debit and credit data**
- Credits (₹12.76 crore) are slightly higher than debits (₹12.73 crore): a ratio of 1.0025 and a net inflow of about ₹3.18 lakh.
- Debit card, bank transfer and credit card are almost equally used (about 33.3% each).
- Branch totals range from ₹4.17 crore to ₹4.29 crore. Kotak Mahindra Bank has the highest transaction amount (₹4.28 crore) and HDFC Bank the lowest (₹4.19 crore).
- Total amount grew 4.39% in October and fell 4.64% in November compared with the previous month.
- 19,084 of 100,000 transactions (19.08%) are flagged as high risk.

---

## Data preparation

**Bank loan data**
- Trimmed stray spaces in headers and text, and renamed misspelt headers (`Grrade` to `Grade`, `Total Rrec int` to `Total Rec Int`).
- Repaired 5,031 misaligned rows where `State Name` held the text "State Name" and the real state sat in another column.
- Corrected 320 wrong state codes.
- Converted text dates (mixed `dd-mm-yyyy` and `d/m/yyyy`) into real dates.
- Fixed spelling in categories (`Transffered` to `Transferred`, `GUWAAHATI` to `GUWAHATI`) and merged near-duplicate purpose categories.
- Filled blanks with `Not Available` or `Unknown`, so no rows were deleted.
- The `01-01-1900` values in `Closed Date` were kept as provided in the source data.

**Debit and credit data**
- No blanks, duplicates or spacing problems were found.
- Added helper columns: `Month`, `Week Start` and `High Risk Flag`.

---

## Assumptions and definitions

- **Total Collection** is the sum of `Total Pymnt`.
- **Account Activity Ratio** is total transactions divided by total account balance (each account has only one transaction, so a per-account ratio would not be meaningful).
- **High-risk transaction:** an Amount of ₹4,500 or more, or a Debit larger than the account balance. The limit is a project assumption because the requirement did not give one.
- **Branch Transaction Growth** compares October and November 2024 with the previous month. December is left out because the data ends on 1 December 2024 (only 305 transactions).
- **Branch names** repeat across banks in the debit and credit data, so branch comparisons should be read with the bank in mind.
- In the debit and credit data, the transaction type does not always match the description (for example, some "Salary Deposit" rows are debits). Results follow the type as given in the data.

---

## How it was built

**Excel**
- PivotTables for every number and chart, with Bank Name and Month or Financial Year slicers connected to them.
- Dashboard cards, charts and a camera-tool picture of the flagged-transactions table.
- A small VBA macro drives the Day, Week and Month buttons (file saved as `.xlsm`).

**Power BI**
- Data loaded and typed in Power Query, then modelled with DAX measures, for example:
  - `Total Credit Amount = CALCULATE(SUM(TxnData[Amount]), TxnData[Transaction Type] = "Credit")`
  - `Credit to Debit Ratio = DIVIDE([Total Credit Amount], [Total Debit Amount])`
  - `Delinquent Loans Rate = DIVIDE(CALCULATE(COUNTROWS(BankData), BankData[Is Delinquent Loan] = "Y"), [Total Loans])`
- A field parameter and a button slicer switch the trend chart between Day, Week and Month.
- Custom theme file (`IDFC_FIRST_Bank_theme.json`), page navigation buttons and synced Bank Name slicers across pages.

---

## Repository structure

```
.
├── README.md
├── images/                          # dashboard screenshots used above
├── excel/
│   ├── Bank_Loan_Dashboard.xlsx
│   └── Debit_Credit_Dashboard.xlsm
├── powerbi/
│   ├── Bank_Loan_Dashboard.pbix
│   ├── Debit_Credit_Dashboard.pbix
│   └── IDFC_FIRST_Bank_theme.json
└── data/                            # optional: cleaned datasets (leave out if confidential)
```

---

## How to open the files

- **Excel files:** open in desktop Excel. For the `.xlsm` file, click **Enable Content** when the yellow security bar appears so the Day, Week and Month buttons work. If the file was downloaded, right-click it, choose **Properties** and tick **Unblock** first.
- **Power BI files:** open in Power BI Desktop (free from the Microsoft Store). To reuse the theme, go to **View > Themes > Browse for themes** and pick `IDFC_FIRST_Bank_theme.json`.

---

## Limitations

- The debit and credit data has one transaction per customer, so repeat behaviour cannot be analysed.
- The balance in the debit and credit data is not a running balance.
- Excel slicers and the macro buttons need the desktop version of Excel. They do not work in Excel Online.

---

## Author

**Ambati Sarath**: [LinkedIn](https://www.linkedin.com/in/ambatisarath/)

Group project. Team members: *add names here*. Mentor: *add name here*.
