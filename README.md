# Accounts-receivable-and-accounts-payable-analysis
Accounts Receivable and Payable analysis for a fictional Cape Town wholesaler using Excel, SQL and Power BI. Analyses overdue debt, invoice ageing, DSO, DPO, customer credit risk and cash flow gaps, delivering actionable insights and recommendations to improve collections, supplier payments and working capital management. Synthetic ZAR data.
# Accounts Receivable & Accounts Payable Analysis

### Cape Wholesale Distributors | Excel · SQL (SQLite) · Power BI

A financial analytics project investigating where a wholesale business's cash is tied up: outstanding customer debts, supplier obligations, overdue invoices and working capital pressures.

Using Excel, SQL and Power BI, this project analyses receivables and payables, evaluates collection and payment performance, identifies credit risks and provides actionable recommendations to improve cash flow and working capital management.

## 1. Business Scenario

Cape Wholesale Distributors supplies products to small retailers, offering customers credit payment terms. The business also purchases inventory from suppliers, with payments often made after an agreed credit period.

Management has identified several financial challenges:

- Customers are taking longer than expected to settle outstanding invoices.
- A significant portion of customer debt has become overdue.
- Some customers are exceeding their approved credit limits.
- Supplier payment deadlines are creating pressure on available cash.
- Management lacks a consolidated view of receivables, payables and future cash obligations.

The business needs a clearer understanding of its working capital position to make better credit-control, collection and supplier-payment decisions.

## 2. Problem Statement

Cape Wholesale Distributors lacks sufficient visibility into outstanding customer invoices, overdue receivables, supplier obligations and payment patterns.

This creates potential risks, including delayed collections, increased credit exposure, poor cash-flow planning and strained supplier relationships.

This project analyses accounts receivable and accounts payable data to identify overdue balances, evaluate collection and payment performance, assess customer credit risk and examine the timing difference between customer collections and supplier payments.

The objective is to provide management with data-driven insights and practical recommendations to strengthen credit control, improve working capital efficiency and reduce cash-flow pressure.

## 3. Business Objectives & Questions

### Accounts Receivable (AR)

*Money owed to the business by customers.*

1. What is the total outstanding customer balance?
2. How much of the receivables balance is overdue?
3. Which customers account for the largest outstanding debts?
4. How long does the business take to collect customer payments?
5. Which customers present the highest credit risk?
6. Are customers operating within their approved credit limits?

### Accounts Payable (AP)

*Money the business owes its suppliers.*

1. What is the total outstanding supplier balance?
2. How much of the payable balance is overdue?
3. Which suppliers account for the largest outstanding obligations?
4. When are upcoming supplier payments due?
5. How effectively is the business managing supplier payment terms?

### Combined Working Capital Analysis

1. Is the business collecting customer payments faster or slower than it pays suppliers?
2. What is the difference between outstanding receivables and payables?
3. How much financial pressure could upcoming supplier payments create?
4. What actions can management take to improve working capital?

## 4. Dataset Overview

The project uses three main datasets.

| Dataset | Records | Description |
|---|---:|---|
| Customers | 25 | Customer IDs, names, areas, credit terms and credit limits |
| Suppliers | 12 | Supplier IDs, names, categories and payment terms |
| Transactions | 757 | 583 customer invoices (AR) and 174 supplier invoices (AP) |

**Reporting period:** 1 November 2025 – 31 October 2026  
**Analysis date:** 31 October 2026  
**Currency:** South African Rand (ZAR)

### Data characteristics

The transaction dataset includes:

- Fully paid invoices.
- Partially paid invoices.
- Unpaid invoices.
- Current invoices that have not reached their due dates.
- Overdue invoices across different ageing categories.

### Calculated fields

Excel formulas are used to derive:

- Invoice due dates.
- Outstanding balances.
- Invoice payment status.
- Days past due.
- Ageing categories.
- Days to payment.

### Receivables and Payables Ageing

Outstanding balances are classified into five categories:

| Ageing category | Definition |
|---|---|
| Current | Not yet overdue |
| 1–30 days | Overdue by 1–30 days |
| 31–60 days | Overdue by 31–60 days |
| 61–90 days | Overdue by 61–90 days |
| 90+ days | Overdue by more than 90 days |

**Data limitation:** Each invoice contains a single payment record. Actual accounting systems may record multiple partial payments against one invoice.

A data dictionary, assumptions and limitations are documented in the Excel workbook.

## 5. Tools & Methodology

| Stage | Tool | Activities |
|---|---|---|
| Business understanding | Business analysis | Defined the problem, objectives and business questions |
| Data preparation | Excel | Structured datasets, calculated balances and classified invoice ageing |
| Data analysis | SQL (SQLite) | Analysed outstanding balances, overdue debt, payment performance and working capital |
| Data visualisation | Power BI | Developed interactive financial dashboards |
| Financial interpretation | Business analysis | Identified risks, evaluated performance and developed recommendations |

### Analytical Approach

1. Examined customer and supplier transaction records.
2. Calculated outstanding balances using invoice and payment information.
3. Classified unpaid balances according to overdue periods.
4. Identified customers with high outstanding balances and credit-limit exposure.
5. Evaluated collection and supplier-payment performance.
6. Compared receivables and payables to understand working capital pressure.
7. Translated the findings into practical management recommendations.

## 6. Key Financial KPIs

| KPI | Definition | Business purpose |
|---|---|---|
| Total AR | Total outstanding customer invoices | Measures money owed by customers |
| Total AP | Total outstanding supplier invoices | Measures money owed to suppliers |
| Overdue AR | Outstanding customer debt past due date | Measures collection risk |
| Overdue AP | Outstanding supplier debt past due date | Measures late-payment exposure |
| DSO | Average receivables / credit sales × days in period | Measures collection efficiency |
| DPO | Average payables / credit purchases × days in period | Measures supplier payment timing |
| Cash Gap | DSO − DPO | Highlights the timing difference between collections and payments |
| Collection Rate | Amount collected / amount invoiced × 100 | Measures the proportion of invoiced amounts collected |
| Credit Utilisation | Customer outstanding balance / credit limit × 100 | Identifies customers exceeding credit limits |

**Important:** Net outstanding position (AR − AP) is an indicator of the receivables/payables position, not actual available cash.

## 7. Key Findings & Financial Insights

### 7.1 Accounts Receivable

The analysis identified significant customer collection and credit-control risks.

- Total outstanding receivables: **R3.25 million**.
- Overdue receivables: **R1.33 million (41.0%)**.
- Debt overdue by more than 90 days: **R780,000 (24% of total AR)**.
- Days Sales Outstanding (DSO): **74.5 days**.
- Average collection period for paid invoices: **46.3 days**, compared with average credit terms of approximately 37 days.
- Eight customers exceeded their approved credit limits.

**Customer concentration risk**

Four customers account for approximately R560,000, or 71%, of the debt overdue by more than 90 days:

- Atlantis Community Store
- Delft Super Spaza
- Malmesbury Farm Stall
- Blue Downs Kasi Foods

The analysis also identified severe credit-limit breaches, with the four highest-risk accounts reaching approximately 299%–376% of their approved limits.

**Business implication:** A relatively small number of customers account for a substantial proportion of aged receivables. Continuing to extend credit to these accounts increases the business's exposure to delayed payments and potential bad debts.

### 7.2 Accounts Payable

The analysis also identified supplier payment obligations that require closer monitoring.

- Total outstanding payables: **R2.43 million**.
- Overdue payables: **R490,000 (20.3%)**.
- Days Payable Outstanding (DPO): **52.1 days**.
- Average payment period: **40.1 days**, compared with average supplier terms of approximately 39.8 days.
- Two suppliers, Peninsula Freight & Logistics and Winelands Snacks, account for approximately 91% of overdue payables.
- Three suppliers account for approximately 57% of the total outstanding supplier balance.

**Upcoming payment obligations**

Approximately **R1.94 million** in supplier payments is scheduled to fall due during November and December 2026.

**Business implication:** Although overall supplier payment performance is relatively close to agreed terms, concentrated overdue balances and upcoming payment obligations create potential liquidity pressure.

### 7.3 Combined Working Capital Analysis

The combined analysis highlights the timing difference between customer collections and supplier payments.

| Metric | Result |
|---|---:|
| Total Accounts Receivable | R3.25m |
| Total Accounts Payable | R2.43m |
| Net Outstanding Position | R0.81m |
| DSO | 74.5 days |
| DPO | 52.1 days |
| Cash Gap | 22.4 days |
| Overdue Receivables | R1.33m |
| Upcoming Supplier Payments | R1.94m |

**Key insight:** Customers take approximately 22 days longer to pay than the business takes to pay its suppliers.

Furthermore, the R1.33 million in overdue customer balances would cover only approximately 69% of the R1.94 million in upcoming supplier obligations, assuming those overdue balances are collected in full.

This highlights the importance of improving collection performance and planning supplier payments around expected cash inflows.

## 8. Power BI Dashboard

The Power BI report is structured into three analytical pages.

### Page 1: Accounts Receivable

**Focus:** Customer debt and collection performance.

Key visuals:
- Total outstanding receivables.
- Overdue receivables.
- AR ageing analysis.
- Top customers by outstanding balance.
- Customer credit-limit utilisation.
- Collection performance and DSO.

### Page 2: Accounts Payable

**Focus:** Supplier obligations and payment performance.

Key visuals:
- Total outstanding payables.
- Overdue supplier balances.
- AP ageing analysis.
- Top suppliers by outstanding balance.
- Upcoming supplier payments.
- Supplier payment performance and DPO.

### Page 3: Working Capital Overview

**Focus:** Cash-flow pressure and the relationship between receivables and payables.

Key visuals:
- AR versus AP comparison.
- Net outstanding position.
- DSO versus DPO.
- Cash gap.
- Upcoming supplier obligations.
- Key financial risks and management recommendations.

## 9. Management Recommendations

Based on the analysis, the following actions are recommended.

| Identified issue | Recommended action |
|---|---|
| High overdue customer debt | Prioritise collection of the R1.33m overdue balance, starting with invoices aged 90+ days |
| Concentrated bad-debt exposure | Review and restrict further credit to the four highest-risk customers until payment arrangements are established |
| Credit-limit breaches | Introduce automated credit-limit checks before approving new customer orders |
| Delayed collections | Introduce weekly debtor follow-ups, payment reminders and structured collection procedures |
| Concentrated overdue supplier balances | Prioritise communication and payment arrangements with Peninsula Freight & Logistics and Winelands Snacks |
| Upcoming supplier obligations | Prepare a rolling 13-week cash-flow forecast to align expected collections with supplier payment deadlines |
| Working capital pressure | Negotiate improved payment terms with key suppliers where commercially appropriate |
| Slow collection performance | Set a DSO reduction target and monitor collection performance monthly |

### Potential Financial Impact

Reducing DSO by 10 days could release approximately **R430,000** in working capital, assuming sales remain consistent.

This is an illustrative estimate based on the current daily credit sales run rate, not guaranteed cash savings.

## 10. Conclusion

The analysis indicates that Cape Wholesale Distributors' working capital challenges are strongly linked to concentrated customer credit risk and the timing mismatch between receivables and payables.

Although the business has R3.25 million in outstanding receivables against R2.43 million in payables, a substantial portion of customer debt is overdue. More concerningly, a small group of customers accounts for most of the severely aged debt, with some operating significantly above their approved credit limits.

At the same time, the business faces R1.94 million in upcoming supplier payment obligations. With a 22.4-day cash gap, the business effectively carries the financial burden of customer credit for longer than it takes to settle supplier obligations.

The findings suggest that improving working capital does not simply require collecting from every customer more aggressively. It requires targeted credit control, stronger credit-limit enforcement, structured collection procedures and better cash-flow forecasting.

By prioritising high-risk accounts, improving collection efficiency and coordinating supplier payments with expected cash inflows, management can strengthen liquidity, reduce credit exposure and improve the business's overall working capital position.

**The central finding: Better credit control and smarter cash-flow planning can make a meaningful difference to the financial health of a wholesale business.**

## 11. Project Limitations & Assumptions

- All data is synthetic and does not represent an actual business.
- Each invoice contains one payment record rather than multiple payment transactions.
- DSO and DPO are based on 12-month transaction totals and should be interpreted in line with the stated calculation assumptions.
- Purchases are used as a proxy for credit purchases where separate credit-purchase information is unavailable.
- Average days-to-pay calculations exclude invoices that have never been paid. Consequently, they may understate the actual collection delay.
- The net AR/AP position does not account for other cash inflows, operating expenses, inventory commitments or available bank balances.
- Upcoming supplier payments represent scheduled obligations, not confirmed cash outflows.

## 12. About the Author

**Mavis Masikati | Data Analytics & Financial Analysis**

I am developing practical skills at the intersection of accounting, financial analysis and data analytics.

My work focuses on helping small businesses understand their financial performance through structured data, financial reporting and interactive dashboards.

**Tools:** Excel | SQL | Power BI | Python

**Areas of interest:** Financial Analysis | Management Reporting | Accounts Receivable | Accounts Payable | Working Capital Analysis | Business Intelligence

Portfolio: https://mavismasikati.netlify.app/
