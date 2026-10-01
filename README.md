# Credit Portfolio Risk Analysis Using SQL

## 📊 Project Overview
This project analyses over 2 million peer-to-peer loans from the Lending Club dataset (2007 - 2018) to identify key drivers of credit default, assess portfolio concentration risk, and evaluate whether loan pricing adequately compensates for borrower risk. The analysis applies CFA-level credit frameworks - including the 5 Cs of Credit, Probability of Default (PD), and Expected Loss (EL) - implemented entirely in SQL.

## 🎯 Objective
To simulate a credit risk analyst's approach to portfolio surveillance: identifying which borrower segments carry the highest default risk, whether the portfolio is over-concentrated in risky grades, and whether interest rates are pricing that risk correctly - presented as a portfolio-ready case study.

## 🧰 Tools Used
- SQL (SQLite via DB Browser for SQLite)
- GitHub (project documentation)
- Dataset: [Lending Club Loan Data 2007–2018](https://www.kaggle.com/datasets/wordsforthewise/lending-club) via Kaggle

## 📌 Key Business Questions
1. Which risk grades have the highest default rates — and is the portfolio pricing this correctly?
2. Where is exposure most concentrated, and does this create concentration risk?
3. Which loan cohorts (vintages) performed worst over time?
4. What separates borrowers who repay from those who default?
5. What is the Expected Loss by grade - which segment poses the greatest financial risk?

## 🔍 Summary of Insights
- **Grade G loans** default at 30%+, yet interest rate premiums do not fully compensate - indicating under-priced tail risk
- **Grades B and C** represent over 50% of total portfolio exposure - significant concentration risk in mid-risk borrowers
- **DTI > 30%** borrowers default at nearly double the rate of those under 10% - capacity to repay is the strongest default signal
- **MORTGAGE holders** default less than RENT borrowers within the same grade - collateral quality matters beyond the grade itself
- **2007–2009 vintages** show significantly elevated default rates, consistent with the Global Financial Crisis credit cycle

## ✅ How to Reproduce
1. Download the Lending Club dataset from [Kaggle](https://www.kaggle.com/datasets/wordsforthewise/lending-club)
2. Open **DB Browser for SQLite** → New Database → name it `credit_portfolio.db`
3. Import CSV: **File → Import → Table from CSV file** (tick "Column names in first line") — table will be named `accepted_2007_to_2018Q4` automatically
4. Open any `.sql` file from the `/queries/` folder
5. Paste into the **Execute SQL** tab and press **F5**

## 💼 Author
**Hannah (Huong) Tran** |
Financial Analysis |
MSc Banking & Finance with Distinction |
CFA Levels I & II cleared

[LinkedIn](https://www.linkedin.com/in/huong-hannah/) | [GitHub](https://github.com/Hannah-Tran)
