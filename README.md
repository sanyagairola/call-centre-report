# call-centre-report
# Call Centre Performance Report

A data analysis project reviewing one year (FY2023) of call centre activity — 1,000 calls, 5 representatives, and 15 customer accounts — to surface performance patterns and produce a consultant-style findings & recommendations report.

## 📄 Overview

This repository contains:
- The raw source workbook (`Call_Centre_Report_Project.xlsx`) with call-level records, a customer reference table, and pivot summaries.
- A cleaned/rebuilt analysis of that data (representative, monthly, city, and duration-band breakdowns), since several of the workbook's original pivot tables and lookups contained broken formulas (`#VALUE!`, `#NAME?`).
- A polished Word report (`Call_Centre_Report.docx`) summarizing key findings and prioritized recommendations for customer support leadership.

## 📊 Data

**Source:** `Call_Centre_Report_Project.xlsx`

| Sheet | Contents |
|---|---|
| `Data` | 1,000 raw call records — call ID, customer ID, representative, date, duration, purchase amount, satisfaction rating |
| `Cutomer Support Report` | Pre-built pivot tables (purchase amount by representative/customer/city) |
| `Sheet2` | Additional pivots — monthly trend, day-of-week, gender/city breakdowns, rep summary |
| `Assets` | Representative ID → image lookup (broken references) |

**Coverage:**
- Period: 1 January 2023 – 31 December 2023
- 1,000 calls across 5 representatives (`R01`–`R05`)
- 15 unique customer accounts across 3 cities: Cincinnati, Cleveland, Columbus
- Per-call fields: duration (minutes), purchase amount ($), satisfaction rating (1–5)

## 🔍 Methodology

1. Extracted all 1,000 call records directly from the `Data` sheet rather than relying on the workbook's existing pivots.
2. Rebuilt the customer reference table (city, gender, age) and correctly joined it to each call by customer ID — the original file's city/gender/age columns were misaligned with per-call data.
3. Recomputed summary statistics: representative performance, monthly/seasonal trends, day-of-week distribution, duration-band analysis, and city/demographic breakdowns.
4. Tested the relationship between call duration and both revenue and satisfaction (correlation analysis).
5. Flagged low-satisfaction calls (rating ≤ 2) by representative to identify coaching priorities.

## 🧠 Key Findings

- **Overall health is strong:** average satisfaction of 3.89/5, only 3.1% of calls rated ≤2, $96,623 in total purchase value driven.
- **Representative performance is uneven in quality, not volume:** `R03` leads on revenue, shortest average handle time, and lowest poor-rating rate (1.9%); `R02` has the highest poor-rating rate (4.1%) despite strong volume.
- **Call duration doesn't predict outcomes:** correlation with revenue (≈ –0.01) and satisfaction (≈ +0.01) is negligible — longer calls are not better calls.
- **Volume is highly seasonal:** calls range from 50/month (August) to 155/month (March), with no evidence of staffing flexing to match.
- **Regional differences exist but are directional:** Columbus shows the lowest average satisfaction (3.77) vs. Cincinnati's highest (4.03), though the small account base (15 total) limits statistical confidence.

## ✅ Recommendations

1. **Codify and roll out R03's approach** as the team standard (high priority)
2. **Run a focused quality review** on R02's low-rated calls (high priority)
3. **Build a lightweight seasonal staffing plan** for peak months (medium priority)
4. **Set a data-backed handle-time efficiency target** (medium priority)
5. **Investigate the Columbus satisfaction gap** before drawing conclusions (lower priority)
6. **Clean up the underlying reporting workbook** to fix broken formulas (lower priority)

Full detail, supporting tables, and rationale for each recommendation are in the report.

## 📁 Repository Structure

```
.
├── Call_Centre_Report_Project.xlsx   # Source data workbook
├── Call_Centre_Report.docx           # Final findings & recommendations report
└── README.md                         # This file
```

## 🛠️ Tools Used

- Python (pandas, openpyxl) for data extraction, cleaning, and analysis
- Word (docx) for the final report deliverable

## 📌 Notes / Limitations

- The customer base is small (15 accounts), so city- and account-level findings should be treated as directional rather than statistically conclusive.
- Several formulas in the original workbook (representative images, named ranges, some pivot fields) were broken and are not relied upon in this analysis — see Recommendation 6.

## 📬 Contact

For questions about this analysis, open an issue in this repository.
