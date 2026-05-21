# 🏦 Banking Customer Analytics — Exploratory Data Analysis

> **A full-stack data analytics project** uncovering customer behaviour, loyalty patterns, and risk profiles across 3,000 banking clients using Python, Power BI, and structured EDA methodology.

---

## 📌 Project Overview

Banks manage thousands of client relationships with vastly different financial profiles. Without structured analysis, institutions risk misallocating resources, designing generic products, and failing to retain high-value customers.

This project applies **Exploratory Data Analysis (EDA)** to a banking customer dataset to answer:

- Who are the bank's most profitable and loyal customers?
- What drives loyalty tier classification — and where are the gaps?
- How does income relate to savings, borrowing, and investment behaviour?
- Which customer segments carry the highest financial risk?
- Are there patterns in product adoption across nationalities and fee structures?

---

## 📁 Repository Structure

```
banking-customer-analytics/
│
├── 📊 Banking_Dataset.csv          # Raw dataset — 3,000 clients, 25 features
├── 📓 Python_EDA.ipynb             # Full EDA notebook (Python)
├── 📈 project_dashboard.pbix       # Power BI interactive dashboard
├── 📄 Banking_Analytics_Report.docx # Detailed project report with findings
└── 📋 README.md                    # You are here
```

---

## 🗃️ Dataset Summary

| Attribute | Details |
|---|---|
| **Records** | 3,000 clients |
| **Features** | 25 columns |
| **Missing Values** | None — 100% complete |
| **Age Range** | 17 to 85 years (mean: 51) |
| **Nationalities** | 5 — European, Asian, American, Australian, African |
| **Loyalty Tiers** | Jade, Silver, Gold, Platinum |
| **Fee Structures** | High, Mid, Low |
| **Income Range** | Low (<$100K), Medium ($100K–$300K), High (>$300K) |

### Feature Categories

| Domain | Columns |
|---|---|
| **Demographic** | Age, Gender, Nationality, Occupation, Location ID |
| **Relationship** | Joined Bank, Banking Contact, Loyalty Classification, Fee Structure |
| **Financial** | Estimated Income, Credit Card Balance, Bank Loans, Bank Deposits, Saving Accounts, Superannuation Savings, Business Lending, Foreign Currency Account |
| **Risk** | Risk Weighting, BRId, IAId |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3** | Core analysis language |
| **Pandas** | Data loading, transformation, feature engineering |
| **Seaborn / Matplotlib** | Statistical visualisations |
| **NumPy** | Numerical operations |
| **Jupyter Notebook** | Interactive EDA environment |
| **Power BI** | Executive-level business dashboard |

---

## 🔍 Methodology

The project followed a structured 7-step EDA pipeline:

1. **Data Understanding** — Shape inspection (3000×25), dtypes, null audit via `df.isnull().sum()`
2. **Feature Engineering** — Income Band: segmented Estimated Income into `Low / Medium / High` bands using `pd.cut()`
3. **Univariate Analysis** — Frequency distributions and countplots for all 11 categorical variables
4. **Bivariate Analysis** — Countplots segmented by Nationality for cross-group behavioural comparison
5. **Numerical Distributions** — `seaborn.histplot` with KDE curves across 7 financial columns
6. **Correlation Analysis** — Pearson heatmap for 8 financial features to detect linear relationships
7. **Dashboard & Reporting** — Power BI dashboard with KPIs, slicers by loyalty/nationality/fee, and trend views

---

## 📊 Key Findings

### 👥 Customer Demographics
- **Average age:** 51 years (range 17–85)
- **Dominant nationality:** European — 1,309 clients (43.6%)
- **Income distribution:** 50.6% Medium income, 15.2% High income ($300K+)

### 🏆 Loyalty Classification
| Tier | Count | Share |
|---|---|---|
| Jade | 1,331 | 44.4% |
| Silver | 767 | 25.6% |
| Gold | 585 | 19.5% |
| Platinum | 317 | 10.6% |

### 💰 Financial Correlations (Heatmap Insights)
- **Bank Deposits ↔ Saving Accounts** — strongest relationship (r = **0.75**): clients who save more also deposit more
- **Business Lending ↔ Bank Loans** (r = 0.42) and **Bank Deposits** (r = 0.44): businesses that borrow also maintain larger deposit buffers
- **Estimated Income** correlates with Superannuation Savings (r = 0.37), Credit Card Balance (r = 0.30), and Business Lending (r = 0.33) — higher earners engage with more products

### ⚠️ Risk Distribution
| Risk Level | Count | Share |
|---|---|---|
| Risk 1 (Low) | 836 | 27.9% |
| Risk 2 | 1,222 | 40.7% |
| Risk 3 | 460 | 15.3% |
| Risk 4 | 322 | 10.7% |
| Risk 5 (High) | 160 | 5.3% |

> 68.6% of clients are low-risk (1–2). The 16% in Risk 4–5 warrant active credit monitoring.

### 💳 Credit Card Penetration
- 1 card: **64.1%** of clients
- 2 cards: **25.5%**
- 3 cards: **10.4%**

---

## 💡 Business Recommendations

| # | Focus Area | Recommendation |
|---|---|---|
| 01 | **Loyalty Upselling** | Target 767 Silver-tier clients with deposit-growth incentives to progress to Gold |
| 02 | **Fee Realignment** | Review 668 High-fee Jade clients — potential churn risk from value misalignment |
| 03 | **High-Income Targeting** | Offer premium bundles (wealth management, FX, business lending) to 456 High-income clients |
| 04 | **Risk Monitoring** | Flag Risk 4–5 clients (482 total) for quarterly credit reviews with automated threshold alerts |
| 05 | **Cross-Selling** | Target multi-card holders with investment products and superannuation top-up options |
| 06 | **Nationality Segmentation** | Build regional strategies for smaller segments (African 5.9%, Australian 8.5%) |

---

## 🚀 How to Run the Notebook

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Launch

```bash
git clone https://github.com/yourusername/banking-customer-analytics.git
cd banking-customer-analytics
jupyter notebook Python_EDA.ipynb
```

> Make sure `Banking_Dataset.csv` is in the same directory as the notebook before running.

---

## 📈 Power BI Dashboard

The `.pbix` file contains an interactive dashboard with:
- KPI cards: Total Clients, Avg Income, Avg Deposits, Avg Loans
- Loyalty tier breakdown (donut chart)
- Nationality distribution (bar chart)
- Fee structure vs Loyalty cross-analysis
- Risk weighting heatmap
- Slicers: Loyalty Tier / Nationality / Fee Structure / Income Band

> Open `project_dashboard.pbix` in **Power BI Desktop** (free download from Microsoft).

---

## 📄 Project Report

A full Word document report (`Banking_Analytics_Report.docx`) is included, covering:
- Business Problem Statement
- Dataset documentation
- Methodology breakdown
- All findings with tables and insight cards
- 6 strategic business recommendations
- Appendix of techniques used

---

## 🔮 Future Scope

- [ ] Churn prediction model (Logistic Regression / Random Forest)
- [ ] Customer Lifetime Value (CLV) modelling
- [ ] Time-series analysis of deposit growth post onboarding
- [ ] Clustering (K-Means) for unsupervised customer segmentation
- [ ] Credit scoring model using Risk Weighting as target variable

---

## 👤 Author

**VICKY KUMAR YADAV**
📧 your.email@example.com
🔗 [LinkedIn]()https://www.linkedin.com/in/vicky-kumar-yadav-55135a259/
🐙 [GitHub]https://github.com/vicky-22-developer/Banking-Customer-Analysis/edit/main/README.md

---

## 📜 License

This project is open for portfolio and educational use.

---

*Built with Python · Power BI · Jupyter · Pandas · Seaborn*
