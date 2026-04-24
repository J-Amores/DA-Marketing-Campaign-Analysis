# Bank Marketing Campaign Analysis

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-444876?style=for-the-badge&logo=seaborn&logoColor=white)](https://seaborn.pydata.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

## Overview

End-to-end exploratory data analysis of a Portuguese bank's direct marketing campaign for term deposit subscriptions, covering 41,188 customer contacts from May 2008 to November 2010. The project uses a structured **Size → Rank → Explain → Compare → Recommend** framework to identify high-conversion customer segments and optimize contact strategy.

**Central Finding:** Students (31.4%) and retired customers (25.2%) convert at 2–3x the baseline rate of 11.3%, while customers with prior campaign success convert at 65.1% — a 7.4x lift. Cellular contact outperforms telephone by 9.5 percentage points, and conversion decays sharply beyond 3 contacts.

## Project Structure

```
DA03_Bank-Marketing-Campaign-Analysis/
├── README.md
├── DA03_Project-Plan.md              # Problem statement and methodology
├── analysis.ipynb                    # Stage 1: 5-stage EDA pipeline
├── final-report.ipynb                # Stage 2: Narrative report
├── index.html                        # Stage 3: Self-contained editorial HTML report
├── data/
│   ├── bank-additional-full.csv      # Primary dataset (41,188 records × 21 features)
│   ├── bank-additional.csv           # 10% sample for prototyping
│   ├── bank-additional-names.txt     # Feature descriptions
│   ├── bank-full.csv                 # Older version (reference)
│   ├── bank.csv                      # Legacy version
│   ├── bank-names.txt                # Legacy feature descriptions
│   └── bank_grain_final.csv          # Analysis-ready output (41,188 × 30 columns)
└── charts/
    ├── A2_target_distribution.png
    ├── A4_numeric_distributions.png
    ├── B2_age_analysis.png
    ├── B3_correlation_matrix.png
    ├── B5_duration_conversion.png
    ├── chart1_conversion_funnel.png
    ├── chart2_segment_conversion.png
    ├── chart3_monthly_conversion.png
    ├── chart4_contact_method.png
    ├── chart5_frequency_decay.png
    ├── chart6_heatmap.png
    ├── E4_previous_outcome.png
    ├── E5_targeting_scorecard.png
    └── kpi_cards.png
```

## Dataset

| Property | Detail |
|----------|--------|
| **Source** | [UCI Machine Learning Repository — Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing) |
| **Period** | May 2008 – November 2010 |
| **Records** | 41,188 customer contacts |
| **Features** | 21 original → 30 after feature engineering |
| **Target** | Term deposit subscription (yes/no) |
| **Class Balance** | 11.3% positive (4,640) / 88.7% negative (36,548) |

**Feature Categories:** Demographics (age, job, marital, education), Financial (default, housing, loan), Campaign (contact type, month, day_of_week, duration, campaign count), Previous campaign (pdays, previous, poutcome), and Economic indicators (emp.var.rate, cons.price.idx, cons.conf.idx, euribor3m, nr.employed).

## Data Processing

- **No rows removed** — all 41,188 records retained after cleaning
- **Recoding:** `default` converted to binary risk flag; target encoded as binary
- **Feature Engineering:** 10 derived features including age_bucket, job_group, edu_level, duration_bucket, contact_bucket, season, and previously_contacted flag
- **Unknown values preserved** as own category in 5 categorical fields
- **Campaign outliers** (>20 contacts) flagged but retained (157 records)

## Project Includes

- Conversion funnel analysis (overall 11.3% baseline)
- Segment conversion profiling by job, age, education, and marital status
- Monthly conversion trends with dual-axis volume analysis
- Contact method comparison (cellular vs. telephone)
- Contact frequency decay curve
- Job group × age bucket conversion heatmap
- Prior campaign outcome lift analysis (65.1% for prior success)
- Composite targeting scorecard with actionable rankings

## Key Findings

1. **Students and retirees are highest-converting segments** — 31.4% and 25.2% respectively, 2–3x above baseline
2. **Prior campaign success is the strongest predictor** — 65.1% conversion rate (7.4x lift)
3. **Cellular outperforms telephone** by 9.5 percentage points (14.7% vs. 5.2%)
4. **Conversion decays sharply beyond 3 contacts** — 11.1% drops to 5.3%
5. **Peak months: March (50.6%), December (48.9%)** — seasonal timing is a major lever
6. **4.4x spread across job segments** — targeting the right profile dramatically improves ROI

## Technologies Used

- **Python** — pandas, numpy, scikit-learn (TfidfVectorizer), matplotlib, seaborn
- **Jupyter Notebook** — Reproducible analytical pipeline
- **HTML/CSS** — Self-contained editorial report with scroll animations, animated KPI counters, and dark mode

## How to Run

```bash
# 1. Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# 2. Run the EDA pipeline (generates processed data + all 13 charts)
jupyter nbconvert --to notebook --execute analysis.ipynb

# 3. Run the narrative report
jupyter nbconvert --to notebook --execute final-report.ipynb

# 4. Open the editorial report
open index.html
```

## Caveats

- **Duration excluded from targeting** — only known post-call; included descriptively only
- **Class imbalance (88.7% negative)** — all rates are descriptive, not predictive
- **Eurozone crisis era** — May 2008–Nov 2010 economic context may not generalize to current conditions

## Conclusion

This project demonstrates that **targeted segment selection and contact strategy optimization** can dramatically improve term deposit conversion. By prioritizing students, retirees, and prior success customers via cellular contact with a 3-call cap, the bank can maximize subscription rate while minimizing campaign cost. The composite targeting scorecard provides an actionable framework for campaign planning.

## Author

- **John**
- [GitHub](https://github.com/)
