#  Prescriptive Credit Risk Engine: End-to-End Analytics Suite

## Executive Project Overview
This repository delivers an end-to-end data analytics and risk mitigation solution that seamlessly bridges the gap between **Predictive Data Science (Python)** and **Executive Corporate Strategy (Power BI)**. 

Instead of relying on traditional, rigid credit scoring systems or stopping at raw default probabilities, this engine implements an automated **Prescriptive Strategy Logic** to segment loan applicants into actionable operational tiers. When applied to a validation portfolio of **$63M in gross exposure**, this framework successfully isolates toxic risk, **safeguarding the institution from a projected $15.05M in bad debt write-offs.**

---

##  Business Impact & The Data Story

By analyzing the distribution of our model's individual `Default_Probability` outputs, the portfolio is partitioned into three high-impact management guardrails:

* **🟢 Green Tier (Standard Approval):** Captures **$27M** in clean exposure. Boasting a highly safe baseline Non-Performing Loan (NPL) rate of just **12%** ($3M expected loss), these borrowers are fast-tracked for automated operational approval.
* **🟡 Amber Tier (Risk-Adjusted Conditional Approval):** Isolates **$18M** in mid-level risk exposure carrying a **40%** NPL rate ($7M expected loss). The prescriptive strategy routes these to credit officers for specialized risk-mitigation pricing, higher interest rates, or extra collateral requirements.
* **🔴 Red Tier (Automatic Decline):** Successfully traps **$18M** of the most toxic exposure in the dataset. Because this specific segment exhibits a catastrophic **82% NPL rate**, enforcing an automatic rejection rule **instantly insulates $15.05M in bank capital from certain default**.

### 🏥 Behavioral Insights by Loan Intent
The analytical pipeline evaluates borrower behavior to highlight granular macro risk trends:
* **Medical Loans (`loan_intent_MEDICAL`):** Carry an elevated baseline risk profile. Across the entire portfolio, medical borrowers default at a higher rate (**28%**) compared to non-medical counterparts (**20%**). Within the isolated Red Tier, the medical default rate skyrockets to **68%**.
* **Venture Loans (`loan_intent_VENTURE`):** Demonstrate robust repayment indicators, maintaining a highly sustainable baseline default rate of **14%**.

---

## Technical Architecture & Implementation

### 1. Data Science Pipeline (Python Backend)
* **Exploratory Data Analysis & Descriptive Statistics:** Validated the statistical spread of probabilities over a pool of 6,515 applicants. High standard deviation (`std: 0.293`) confirmed strong model discrimination between high-risk and low-risk candidates.
* **Libraries:** `Pandas`, `NumPy`, `Scikit-Learn`, `Seaborn`, `Matplotlib`

### 2. Business Intelligence Architecture (Power BI Frontend)
* **Advanced DAX Modeling:** Developed custom business logic measures to drive executive key performance indicators (KPIs):
  * **Total Exposure:** `SUM(Portfolio[Loan_Amount])`
  * **Expected Loss:** `SUMX(Portfolio, Portfolio[Loan_Amount] * Portfolio[Default_Probability])`
  * **Projected NPL Rate:** `AVERAGE(Portfolio[Default_Probability])`
* **UI/UX Executive Design:** Built using a high-contrast dark theme optimized for readability, multi-layered data hierarchies to bypass drill-down column constraints, and app-like tile slicers for real-time dynamic portfolio cross-filtering.

---

##  Video Walkthrough & Presentation
For a comprehensive breakdown of the coding backend, the data storytelling narrative, and a live demonstration of the dashboard cross-filtering, watch the full project presentation on YouTube: 

 **[Watch the Project Walkthrough on YouTube](https://youtu.be/q6W9mWttGK4)**
