# 📊 IPEDS Data Quality Audit: Python and AI Comparative Analysis

**Tools:** Python, Google Colab, Claude AI (Anthropic)  
**Framework:** DAMA DMBOK Six Data Quality Dimensions  
**Year:** 2026

## Project Overview
Comprehensive data quality audit of five Integrated Postsecondary Education Data 
System (IPEDS) datasets for Academic Year 2024, published by the U.S. Department 
of Education. IPEDS is the primary data source for 6,000+ U.S. higher education 
institutions and supports federal financial aid, accreditation decisions, and 
public institutional rankings.

The project was conducted twice using two different methods — Python/Google Colab 
and Claude AI — to compare speed, rigor, and depth of findings.

## Datasets Audited

| Dataset | Description | Rows | Columns |
|---------|-------------|------|---------|
| DF1 | 12-Month Enrollment by race and gender | 115,026 | 72 |
| DF2 | Institutional Financial Data (FY 2023-24) | 1,911 | 288 |
| DF3 | Graduation Rates by cohort, race, gender | 51,011 | 66 |
| DF4 | Institution Directory with location and type | 6,072 | 72 |
| DF5 | Institution Characteristics (programs, admissions) | 5,963 | 111 |

## Audit Framework: DAMA DMBOK Six Dimensions
Each dataset was evaluated across six data quality dimensions:
- **Completeness** — Are all required values present?
- **Uniqueness** — Are records free of unintended duplicates?
- **Timeliness** — Is data current for its intended use?
- **Validity** — Do values conform to defined rules and formats?
- **Accuracy** — Does data correctly represent reality?
- **Consistency** — Is data coherent across datasets?

## Key Findings
- **100% referential integrity** confirmed across all five datasets — every 
institution resolves cleanly to the master Directory via UNITID
- **Critical encoding defect** identified in DF4 Directory: byte-order-mark (BOM) 
encoding error in the primary key, invisible to manual review
- **DF2 Finances** carries a 13.3% imputation rate and 22.2% null rate on total 
revenues — a required disclosure for any financial benchmarking
- **14 closed institutions** still appearing in active enrollment and graduation 
data, creating a currency gap requiring reconciliation
- **39 institutions share OPEIDs** with administrative offices, posing a federal 
financial aid compliance risk
- **For-profit institutions** represent 37% of campuses but only 8.4% of 
enrollment — institution counts and enrollment counts tell opposite stories

## Python vs. AI Comparative Analysis

| | Python / Google Colab | Claude AI |
|---|---|---|
| **Time to complete** | ~7 working days | 19 minutes |
| **Unique strengths** | Institutional context, sector narrative, policy interpretation | Speed, encoding defect detection, imputation rate analysis |
| **Best suited for** | Annual deep-dive audits | Routine quality checks at every data release |

**Conclusion:** Both methods confirmed IPEDS data is governance-ready with no 
dataset scoring below Acceptable. The two approaches are complementary — AI 
excels at speed and technical detection; Python excels at institutional depth 
and policy interpretation.

## Data Quality Scores

| Dataset | Python Score | AI Score |
|---------|-------------|----------|
| DF1 Enrollment | 8.0 / Good | 8.5 / Good |
| DF2 Finances | 7.3 / Acceptable | 9.2 / Good |
| DF3 Graduation Rates | 8.0 / Good | 8.2 / Good |
| DF4 Directory | 7.8 / Acceptable | 8.2 / Good |
| DF5 Characteristics | 7.8 / Acceptable | 9.5 / Excellent |

## Skills Demonstrated
- Large-scale dataset profiling (179,000+ total rows across 5 datasets)
- Application of DAMA DMBOK data governance framework
- Cross-dataset referential integrity validation
- Statistical anomaly detection and encoding defect identification
- AI-assisted vs. code-based audit methodology comparison
- Formal governance report and executive presentation development

## Files in This Repository
- `IPEDS_Audit_Notebook.ipynb` — Full Python/Google Colab notebook with code, 
visualizations, and scoring
- `IPEDS_Data_Quality_Python_Presentation.pptx` — Python audit findings presentation
- `IPEDS_Comparison_Presentation.pptx` — AI vs. Python comparative analysis
- `IPEDS_Claude_AI_Audit_Report.pdf` — Full AI-generated audit report
