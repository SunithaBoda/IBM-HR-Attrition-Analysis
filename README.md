# IBM HR Employee Attrition Analysis

**Author:** Boda Sunitha
**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn  
**Dataset:** IBM HR Analytics Dataset — 1,470 employees · 35 features · [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

# Dashboard Preview

![IBM HR Dashboard]([Employee_Attrition_Dashboard.png]https://github.com/SunithaBoda/IBM-HR-Attrition-Analysis/blob/main/Employee_Attrition_%20Dashboard.png)



<p align="center">
  <img src="[[Employee_Attrition_Dashboard.png](https://github.com/SunithaBoda/IBM-HR-Attrition-Analysis/blob/main/Employee_Attrition_%20Dashboard.png](https://github.com/SunithaBoda/IBM-HR-Attrition-Analysis/blob/main/Employee_Attrition_%20Dashboard.png))" alt="IBM HR Dashboard" width="100%">
</p>

---

## Business Problem

IBM's HR team lacks clarity on why employees leave. Without understanding the key attrition drivers, retention programs remain generic, costly, and ineffective.

**This project answers:** *Which employees are most likely to leave IBM, and what organizational factors are pushing them out?*

---

## Project Objective

Analyze IBM's HR employee data to identify the strongest predictors of attrition — including compensation gaps, overtime patterns, satisfaction scores, and career growth stagnation — so the HR team can prioritize high-impact retention interventions.

---

## Dataset Overview

| Attribute | Value |
|-----------|-------|
| Total Employees | 1,470 |
| Total Features | 35 (32 used after dropping 3 constants) |
| Employees Who Left | 237 (16.1%) |
| Employees Who Stayed | 1,233 (83.9%) |
| Departments | 3 (Sales, R&D, Human Resources) |
| Unique Job Roles | 9 |
| Overtime Employees | ~416 (~28%) |
| Satisfaction Columns | 4 (Job, Environment, Relationship, Work-Life Balance) |
| Constant Columns Dropped | 3 (EmployeeCount, StandardHours, Over18) |

---

## KPIs Defined

This project is structured around 6 business KPIs defined before the analysis began — not after.

| # | KPI | Business Question |
|---|-----|-------------------|
| 1 | Overall Attrition Rate | What percentage of IBM's 1,470 employees left? |
| 2 | Attrition by Department & Job Role | Which teams are bleeding talent the most? |
| 3 | Tenure of Attrited vs Retained Employees | Do employees leave early or after years of service? |
| 4 | Compensation Gap Index | How much less do employees who left earn vs those who stayed? |
| 5 | Overtime & Work-Life Balance Impact | Does overtime predict attrition? Does work-life balance rating matter? |
| 6 | Employee Satisfaction Risk Score | Which satisfaction dimension most strongly predicts attrition? |

---

## Key Findings

### KPI 1 — Overall Attrition Rate
- IBM's overall attrition rate is **16.1%** — 237 out of 1,470 employees left.
- This serves as the baseline benchmark. Any department or group above 16.1% is a higher-risk segment.

### KPI 2 — Attrition by Department & Job Role
- **Sales** has the highest department-level attrition at **20.6%**, followed by HR at **19.0%**.
- At job role level, **Sales Representatives** have a **39.8% attrition rate** — the highest of any role.
- R&D is the most stable department at **13.8%**.

### KPI 3 — Tenure of Attrited vs Retained Employees
- Employees who left had a **median tenure of 3 years** vs **6 years** for those who stayed.
- The **0–2 year group** recorded the highest attrition at **29.8%** — the most critical retention window.
- Attrition consistently declines as tenure increases.

### KPI 4 — Compensation Gap Index
- Employees who left earned a **median monthly income of ₹3,202** vs **₹5,204** for those who stayed — a **₹2,002 gap**.
- The **Low income category** had a **24.2% attrition rate**, compared to just **5.3%** for Very High earners.
- Employees with high performance ratings but no recent promotion are at elevated attrition risk.

### KPI 5 — Overtime & Work-Life Balance Impact
- Overtime employees had a **30.5% attrition rate** — nearly **3× higher** than non-overtime employees (10.4%).
- Employees with the lowest Work-Life Balance rating showed a **31.2% attrition rate**.
- Overtime is the **strongest single behavioral predictor** of employee turnover in this dataset.

### KPI 6 — Employee Satisfaction Risk Score
- Employees with the lowest Environment Satisfaction had a **25.4% attrition rate**.
- Employees who left averaged a satisfaction score of **2.51** vs **2.76** for those who stayed.
- A high-risk segment (overtime + low satisfaction + no promotion in 3+ years): **39 employees, 33.3% attrition rate** — more than **double** the company average.

---

## Methodology

```
Raw Dataset (1,470 rows × 35 features)
        ↓
Data Cleaning
  → Null check (0 missing values)
  → Duplicate check (0 duplicates)
  → Dropped 3 constant columns
        ↓
Statistical Baseline
  → Skewness analysis (7 key numeric features)
  → Correlation matrix with Attrition
        ↓
EDA — 6 KPIs
  → KPI 1: Overall attrition rate
  → KPI 2: Department & job role breakdown
  → KPI 3: Tenure analysis
  → KPI 4: Compensation gap
  → KPI 5: Overtime & work-life balance
  → KPI 6: Satisfaction risk scoring
        ↓
HR Executive Summary + Export
  → IBM_HR_Cleaned.csv for Power BI
```

---

## Statistical Highlights

| Feature | Finding |
|---------|---------|
| YearsSinceLastPromotion Skewness | 1.984 (highest right skew) |
| YearsAtCompany Skewness | 1.765 |
| Top Correlation with Attrition | TotalWorkingYears (−0.171), JobLevel (−0.169), MonthlyIncome (−0.160) |
| Attrition is driven by | Multiple factors combined — no single strong predictor |

---

## Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python | Core analysis language |
| Pandas | Data wrangling and groupby analysis |
| NumPy | Numerical operations and derived columns |
| Matplotlib | Bar charts, histograms, line plots |
| Seaborn | Boxplots, heatmaps, distribution plots |

---

## Project Structure

```
IBM-HR-Attrition-Analysis/
│
├── IBM_HR_Attrition_Analysis_DA.ipynb   # Main analysis notebook
├── Dataset.csv                          # Raw IBM HR dataset
├── IBM_HR_Cleaned.csv                   # Cleaned export for Power BI
└── README.md
```

---

## HR Executive Summary

| KPI | Key Number | Insight |
|-----|-----------|---------|
| Overall Attrition Rate | 16.1% | Baseline for all comparisons |
| Highest Risk Job Role | Sales Rep — 39.8% | Priority for retention |
| Most Critical Tenure Window | 0–2 years — 29.8% attrition | Strengthen onboarding |
| Compensation Gap | ₹2,002/month | Low earners leave at 24.2% |
| Overtime Attrition Rate | 30.5% | 3× company average |
| High-Risk Segment Attrition | 33.3% (39 employees) | Early warning flag |

IBM should focus retention efforts on **early-career employees, overtime reduction, compensation reviews, and satisfaction monitoring** — particularly in Sales and HR departments.

---

## Related Projects

- [SkillScope — India Data Science Job Market Dashboard](https://github.com/samruddhibhandari/SkillScope)
