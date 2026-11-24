# FinSight: Finance Analytics Dashboard (Power BI)

An interactive 2-page Power BI dashboard that monitors financial transactions, customer behavior, fees and taxes across customer segments, states and transaction types.

**Tools:** Power BI, DAX, Power Query

---

## Dashboard preview

### Page 1: Overview Analysis
![Overview Analysis](images/overview.png)

### Page 2: Transactions (detailed grid)
![Transactions](images/transactions.png)

---

## Business problem

A financial organization wants one central dashboard to track:

- Overall transaction growth and financial performance
- Monthly trends in transaction amounts
- Successful vs failed transactions
- Customer segment contribution
- State-wise financial performance
- Transaction type profitability
- Gender-based customer analysis
- Year-over-Year (YoY) performance changes

## Features

**Filters (slicers):** Year, Dynamic Metric (field parameter), Occupation, Category

**KPIs (with YoY comparison vs previous year)**

| KPI | Description |
|---|---|
| Total Amount | Total transaction amount processed |
| Total Transactions | Number of transactions |
| Average Transaction Value | Average amount per transaction |
| Total Fees | Fees collected from transactions |
| Total Tax | Tax generated from transactions |

**Visuals on the Overview page**

| Visual | Chart type | Purpose |
|---|---|---|
| Total Amount by Month | Area chart | Monthly trend, seasonal spikes and drops |
| Total Amount by Transaction Status | Donut | Success vs Failed vs Pending |
| Total Amount by Customer Segment | Horizontal bar | Retail, Premium, SME, Corporate, Wealth contribution |
| Total Amount by State | Horizontal bar | Top-performing states |
| Transaction Type Analysis | Matrix with heatmap | Amount, Fees, Tax and Transaction count by type |
| Total Amount by Gender | Donut | Male vs Female contribution |

**Transactions page:** a transaction-level grid (ID, date, status, customer name, transaction type, gender, segment, state, amount, fees) for auditing individual records.

---

## Dataset

| File | Rows | Description |
|---|---|---|
| `customers.csv` | 5,000 | Customer demographics, city, state, occupation, segment, annual income, join date |
| `finance_transactions.csv` | 50,069 | Transaction date, type, channel, merchant category, amount, fee, tax, status, fraud flag, risk score |

- **Date range:** Jan 2023 to Apr 2026 (2026 is a partial year, so YoY for 2026 is not a full-year comparison)
- **Relationship:** `finance_transactions.customer_id` to `customers.customer_id` (many-to-one)

### Data quality notes (observed in the raw files)

- 69 duplicate transaction IDs
- 24 missing values in `fee_amount`
- Inconsistent channel labels (for example "M@bile App" and extra spaces)
- Currency written in mixed case ("INR" and "inr")
- 9 negative transaction amounts

---

## Sample insights (Year filter = 2025)

| Metric | Value |
|---|---|
| Total Amount | ₹137.53M |
| Total Transactions | 14.94K (-0.57% vs previous year) |
| Average Transaction Value | ₹9.20K (+1.98% vs previous year) |
| Total Fees | ₹216.94K (-0.17% vs previous year) |
| Total Tax | ₹39.04K (-0.26% vs previous year) |

- **Status:** about 85.4% of the amount came from Success transactions, 10.4% from Failed and 4.2% from Pending.
- **Segment:** Retail contributed the most (about ₹76M), followed by Premium (about ₹26M).
- **State:** Maharashtra was the top state (about ₹22M), followed by Karnataka and Gujarat.
- **Transaction type:** Loan EMI had the highest amount (₹40.0M), followed by Transfer (₹36.2M).
- **Gender:** Female customers contributed 52.8% of the amount and Male customers 47.2%.
- **Trend:** monthly amount peaked around July and dipped in February and September.

---

## Skills demonstrated

Power BI dashboard development, DAX measures (KPIs and YoY growth), Power Query, field parameters, data visualization, and KPI design.

## Author

**Meet Pujara**
[LinkedIn](https://linkedin.com/in/meet-pujara) | [GitHub](https://github.com/MeetPujara) | meetpujara02@gmail.com
