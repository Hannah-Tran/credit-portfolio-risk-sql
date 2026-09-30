Credit Portfolio Risk Analysis Using SQL
📊 Project Overview

This project analyses over 2 million peer-to-peer loans from the Lending Club dataset (2007–2018) to identify key drivers of credit default, assess portfolio concentration risk, and evaluate whether loan pricing adequately compensates for borrower risk. The analysis applies CFA-level credit frameworks — including the 5 Cs of Credit, Probability of Default (PD), and Expected Loss (EL) — to real-world lending data using SQL.

🎯 Objective

To simulate a credit risk analyst's approach to portfolio surveillance: identifying which borrower segments carry the highest default risk, whether the portfolio is over-concentrated in risky grades, and whether interest rates are pricing that risk correctly — presented as a portfolio-ready case study.

🧰 Tools Used
SQL (SQLite via DB Browser for SQLite)
GitHub (project documentation and version control)
Dataset: Lending Club Loan Data 2007–2018 via Kaggle
📂 Folder Structure
credit-portfolio-risk-sql/
├── data/
│   └── sample_1000rows.csv        # Small sample for reference (full dataset via Kaggle)
├── queries/
│   ├── 01_portfolio_overview.sql
│   ├── 02_default_rate_by_grade.sql
│   ├── 03_concentration_risk.sql
│   ├── 04_vintage_analysis.sql
│   ├── 05_delinquency_trends.sql
│   └── 06_risk_vs_pricing.sql
├── credit_portfolio.db            # SQLite database (local only, not pushed to GitHub)
└── README.md
📌 Key Business Questions
Which risk grades have the highest default rates — and is the portfolio pricing this correctly?
Where is exposure most concentrated, and does this create concentration risk?
Which loan cohorts (vintages) performed worst over time?
Do borrower characteristics (DTI, income, FICO, home ownership) predict default?
What is the Expected Loss by grade — which segment poses the greatest risk to the portfolio?
🔍 Analysis Modules
A — Default Rate by Grade

Framework: CFA Credit Analysis (Probability of Default)

Step	Business Question
Portfolio overview	How large is this portfolio?
Grade distribution	Where is the money concentrated?
Default rate by grade	Which grades default most?
Pricing assessment	Is interest rate covering the risk?
Expected Loss	What is the true financial impact per grade?
Sub-grade drill-down	Within the riskiest grade, which sub-grades drive losses?

Key finding: Grade G default rates exceed 30%, yet interest rate spreads may not fully compensate — implying under-priced credit risk at the tail.

B — Concentration Risk

Framework: CFA Portfolio Management (Concentration & Diversification)

Measures what % of total exposure sits in each grade and loan purpose — identifying single-segment concentration that could amplify losses in a downturn.

C — Vintage Analysis

Framework: CFA Fixed Income (Cohort Performance, Credit Cycles)

Groups loans by year of issuance and tracks default rates across cohorts — identifying whether underwriting standards tightened or loosened over time.

D — Borrower Profile Analysis (5 Cs of Credit)

Framework: CFA Credit Analysis (5 Cs)

5C	Dataset Proxy
Capacity	DTI, annual income, installment
Capital	Loan amount, funded amount
Character	Delinquencies, FICO score, credit history length
Conditions	Loan purpose, term, economic vintage
Collateral	Home ownership status

Compares borrower profiles of Fully Paid vs Charged Off loans across all five dimensions.

E — Risk vs Pricing (Risk-Adjusted Return)

Framework: CFA Portfolio Management (Sharpe Ratio concept applied to credit)

Calculates a return-per-unit-of-risk metric across grades:

Risk-Adjusted Spread = Avg Interest Rate − Default Rate %
Return per Unit Risk = Avg Interest Rate ÷ Default Rate %

Identifies grades where lenders are not being adequately compensated.

📈 Key Insights
Grade G loans carry the highest default rate (~30%+), but the interest rate premium does not fully offset expected losses — indicating structural under-pricing at the high-risk tail
Grades B and C dominate portfolio exposure, creating concentration risk if macro conditions deteriorate
DTI > 30% borrowers show significantly higher default rates — consistent with CFA capacity-to-repay analysis
MORTGAGE holders default less than RENT borrowers of the same grade — suggesting collateral quality signals beyond the grade itself
2007–2009 vintages show elevated default rates consistent with the Global Financial Crisis credit cycle
💡 CFA Concepts Applied
Concept	Where Applied
Probability of Default (PD)	Default rate queries by grade, DTI, FICO
Expected Loss (EL = PD × LGD × EAD)	Grade-level expected loss calculation
5 Cs of Credit	Borrower profile comparison (Paid vs Default)
Yield Spread Analysis	Interest rate vs default rate by grade and term
Concentration Risk	Exposure % by grade and loan purpose
Vintage Analysis	Cohort default tracking over time
✅ How to Reproduce
Download the Lending Club dataset from Kaggle
Open DB Browser for SQLite → New Database → credit_portfolio.db
Import CSV: File → Import → Table from CSV file (tick "Column names in first line")
Open and run any .sql file from the /queries/ folder
Results appear in the bottom panel of the Execute SQL tab
💼 Author

Hannah (Huong) Tran
MSc Banking & Finance (Distinction) — Queen Mary University of London
CFA Levels I & II | CeMAP in progress
Finance Administrator, Gordon Blair Financial Services

LinkedIn | GitHub
