# Canadian Household Financial Resilience Study (CHFRI)
> **Empirical Research, Statutory Open Methodologies, and Synthetic Microdata Architecture for Next-Generation Financial Planning.**

Developed by **Pennywise 2.0** | Led by **Jeremy Pillon, CFP®** 25+ Year Wealth Advisory Veteran & Systems Architect & Financial Data Science Team

---

## 📌 Executive Overview

Standard Canadian mortgage underwriting relies on pre-tax Gross Debt Service (GDS) and Total Debt Service (TDS) ratios. However, personal income tax represents a mandatory statutory lien collected at source under the *Income Tax Act*. Evaluating real operational solvency requires decoupling gross borrowing capacity from net discretionary cash flow.

The **Canadian Household Financial Resilience Study (CHFRI)** provides an unassailable empirical baseline analyzing how monetary policy shifts, housing inflation, and statutory compounding mechanics impact Canadian households. By evaluating **72,295 empirical microdata records** from Statistics Canada’s Survey of Financial Security (SFS 1999–2023) across a 50-year macroeconomic panel (1976–2026), this study bridges macro financial stability metrics with individual cash-flow survival horizons—powering the commercial **Pennywise 2.0** planning engine to help everyday Canadians build toward, achieve, maintain, and strengthen real financial resilience.

---

## 🔄 A Living Empirical Baseline

CHFRI is an active, continuously evolving data science initiative. We regularly expand our copula models, macroeconomic baselines, and cohort mappings to capture the shifting reality of Canadian household balance sheets:

* **Pre-Tax vs. After-Tax Longitudinal Tracking:** Quantifying the divergence between pre-tax and after-tax debt-service ratios across all age cohorts (1999–2023) to measure the real impact of tax bracket drag on discretionary cash flow.
* **High-Frequency Macro Injections:** Integrating Bank of Canada Financial System Indicators (FSI) and monthly CPI releases via dual-form entropy balancing to bridge the multi-year lag between Statistics Canada microdata waves.

---

## 📊 Core Empirical Findings

* **Active-Debtor Debt Service Peak:** Under the 7.50% OSFI qualifying stress rate, active debtors aged 35–44 commit **17.55%** of real net after-tax income to debt service under baseline conditions, escalating to **20.89%** under acute mortgage stress.
* **The Structural Liquidity Squeeze:** **61.7%** of active mortgagees and debtors aged 35–44 hold under 3 months of unencumbered liquid reserves relative to their stressed monthly debt obligations.
* **Lifecycle Resilience Trough:** Using non-linear Constant Elasticity of Substitution (CES) harmonic indexing, the Composite Financial Resilience Index (CHFRI) identifies a lifecycle resilience trough score of **38.9 out of 100** for the 35–44 prime family-formation cohort—demonstrating that illiquid real estate equity fails to buffer acute cash-flow shocks.

---

## ⚙️ Statutory Methodology & Mathematical Framework

### 1. Statutory Canadian Mortgage Compounding
In accordance with the Canadian *Interest Act* (R.S.C., 1985, c. I-15, s. 6), real estate liabilities enforce statutory semi-annual compounding rather than standard simple monthly rates:

> **Monthly Effective Rate ($r_m$):** `r_m = (1 + r_annual / 2)^(1/6) - 1`
>
> **Annual Cash Outflow Factor ($K_r$):** `K_r = 12 × [ r_m / (1 - (1 + r_m)^(-300)) ]`

| Interest Rate Scenario | Annual Cash Outflow Factor ($K_r$) | Stressed Monthly Debt Impact |
| :--- | :--- | :--- |
| **5.50% FP Canada Baseline** | **7.3117%** | Standard Underwriting Baseline |
| **7.50% OSFI Qualifying Stress Rate** | **8.7801%** ($K_{7.50\%}$) | +20.08% Cash Flow Friction Shift |

### 2. Tax-Friction Liquidity Classification
To reflect statutory liquidity realities, assets are categorized by tax haircut friction:
* **100% Net Liquid Buffer:** Cash deposits, high-interest savings, and Tax-Free Savings Accounts (TFSAs). TFSA withdrawals incur zero withholding tax and generate zero clawbacks on income-tested benefits.
* **Excluded Registered Reserves:** RRSPs and RRIFs are excluded from primary liquidity buffers due to mandatory marginal tax withholdings (30% haircut applied) and permanent contribution room destruction upon liquidation.
* **Non-Registered Tax Friction:** Non-registered investments incur a 15% haircut to account for embedded capital gains tax friction.

### 3. Real Discretionary Surplus (RDS) Engine
Evaluating dynamic household survival requires subtracting regional essential living costs defined by Statistics Canada's Market Basket Measure (MBM):

> **Real Discretionary Surplus:** `RDS_i = After-Tax Income_i - Amortized Debt Service_i - Regional MBM Baseline_i`

### 4. Non-Linear Composite Index (CHFRI)
To prevent high illiquid housing equity from artificially inflating household resilience scores, the composite index uses a 40/40/20 weighted Constant Elasticity of Substitution (CES) formulation with penalty parameter `ρ < 0`:

> **Composite Resilience Score:** `CHFRI_i = ( w_1 · S_Buffer,i^ρ + w_2 · S_DSR,i^ρ + w_3 · S_Solvency,i^ρ )^(1 / ρ)`

---

## 🏗️ Synthetic Microdata Engine & Data Vault Architecture

To transition empirical microdata into production-ready planning engines without compromising privacy, CHFRI generates a **500,000-profile Synthetic Data Vault (SDV)** hosted in PostgreSQL (`pennywise-db`):

> **Pipeline Flow:**
> `StatCan SFS Microdata (1999–2023)` ➔ `Age-Period-Cohort (APC) Engine` ➔ `500,000 Profile Synthetic Vault (Zero-Inflated KDE + Student's t-Copula)` ➔ `Automated Red Team Audit Suite (100% pytest Pass)` ➔ `Pennywise 2.0 Engine Execution`

* **Sampling Integrity:** Ledoit-Wolf regularized Student's *t*-Copula (`ν = 4`) and zero-inflated log-domain KDE models preserve StatCan `family_weight` distributions across Census Metropolitan Areas (CMAs) and rural strata.
* **Asset Realism:** Real estate asset fields are deflated using the Teranet-National Bank House Price Index (HPI) to eliminate general CPI inflation artifacts.
* **Stress Validation:** Automated Red Team `pytest` audits confirm 100% green pass rates across OSFI B-20 Baseline, Asymmetric Stagflation (with regional industry elasticity scalars), and Real Estate Liquidity Freeze scenarios.

---

## 🛡️ Privacy, Open Science & IP Guardrails

* **Zero Client PII:** This public repository utilizes exclusively anonymized Public Use Microdata Files (PUMF) from Statistics Canada and synthetic data distributions. No proprietary database schemas, credentials, or raw client information are contained within this repository.
* **Commercial Application:** The statutory methodologies and resilience engines validated here directly power **[Pennywise (bepennywise.co)](https://bepennywise.co)**—bringing institutional-grade cash-flow intelligence to Canadian households and planners.

---

## 📬 Connect & Follow the Research

* **Platform & Prototype:** [bepennywise.co](https://bepennywise.co)
* **GitHub Organization:** [github.com/pennywise-ca](https://github.com/pennywise-ca)
* **Author:** [Jeremy Pillon, CFP® on LinkedIn](https://linkedin.com/in/jeremypillon)
