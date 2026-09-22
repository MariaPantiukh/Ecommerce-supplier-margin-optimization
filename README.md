# E-commerce Supplier & Margin Optimization: Sales Analytics Case Study

## Executive Summary
This project addresses a critical e-commerce challenge: **identifying unprofitable suppliers and optimizing advertising budgets** to improve overall store profitability. Using real-world CRM data from a dropshipping online business, raw transaction records were processed with **PostgreSQL** and visualized in **Tableau** to evaluate supplier sales performance, margins, and advertising efficiency.

🔗 **[View Interactive Dashboard on Tableau Public](https://public.tableau.com/views/YOUR_DASHBOARD_URL_HERE)**
---

## 🎯 Business Problem & Key Questions
* **Which suppliers are unprofitable and should be removed from the product catalog?**
* **How can advertising expenses be reallocated to maximize profit margin across supplier brands?**
* **What is the overall trend in monthly revenue and supplier margin dynamics?**

<img width="1578" height="1468" alt="SALES PERFORMANCE OVERVIEW" src="https://github.com/user-attachments/assets/ded0365e-f2fa-43a2-8f44-7f2d135dd6da" />

---

## 🛠️ Tech Stack & Methodology
* **Database & Data Cleaning:** PostgreSQL (CTEs, Regex text normalization, Type conversions, Data joining)
* **Visualization & BI:** Tableau (Combo charts, Pivot tables, Metric scorecards, Filter controls)
* **Domain Context:** E-commerce / Dropshipping Sales Analytics

---

## 🧹 Data Cleaning & ETL Pipeline (SQL)
Raw CRM data required substantial cleaning and transformations before BI integration:
1. **Product & Supplier Standardisation:** Inner joined product details with categories and normalized supplier names using REGEXP pattern matching (removed raw noise like `копія`, `відправка`, `кременчук`, `big`).
2. **Missing Data Handling:** Imputed `NULL` and empty supplier values with baseline vendor tags (`skyfarb`).
3. **Data Type Conversion:** Standardized dirty string prices into clean decimal numeric values (`NUMERIC(10,2)`), removing non-breaking spaces and formatting separators.

---
## Key Insights & Business Recommendations

Based on the supplier performance analysis, the following actionable optimizations were identified:

* **Assortment Pruning (Shadow & DMT):** Remove suppliers `Shadow` and `DMT` from the catalog. Despite generating sales, high advertising expenses combined with low profit margins make these items non-profitable for the business.
* **Ad Budget Optimization (Bottleneck):** Reduce the advertising spend rate for supplier `Bottleneck` to balance acquisition cost (CPA) with product margins and improve campaign ROI.
  
