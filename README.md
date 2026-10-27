# R for All of Us Bootcamp

Notebooks for the IGNITE **R for All of Us Bootcamp**, October 29–30, 2026 (10 a.m.–3 p.m. ET each day). Each session is a 1-hour demonstration followed by a 1-hour coding lab on the All of Us Researcher Workbench (CDR v9, `C2025Q4R6`).

## Before Day 1

1. Have an approved Researcher Workbench account and a workspace with CDR v9.
2. Download the notebooks below and upload them to your workspace in JupyterLab.
3. Open `00_SETUP_C2025Q4R6.ipynb` with the **Python 3** kernel and run every cell.
4. Open `01_Demographics.ipynb` with the **R** kernel and run the Setup cells. They should finish without errors.

## Notebooks

| File | Kernel | When | What you do |
| --- | --- | --- | --- |
| `00_SETUP_C2025Q4R6.ipynb` | Python 3 | Before Day 1 | Find your project, buckets and CDR; write the R file every notebook loads |
| `01_Demographics.ipynb` | R | Day 1, 10–12 | Age groups, race/ethnicity, education, income, insurance |
| `02_PHQ9_GAD7.ipynb` | R | Day 1, 1–3 | Check question IDs; score PHQ-9 and GAD-7 |
| `03_BMI.ipynb` | R | Day 2, 10–12 | BMI from EHR and program measurements |
| `04_Cancer_Table1.ipynb` | R | Day 2, 1–3 | Colorectal cancer from EHR, Table 1 and logistic regression (base R and tidyverse only) |

Run them in order: each session saves a file to your workspace bucket (`S1_DEMOGRAPHICS.csv`, `S2_PHQ_GAD.csv`, `S3_BMI.csv`) that Session 4 reads.

## Data used

- Every query keeps only participants **born in 1975 or later** (at most 49 at any point in 2024; the CDR v9 data cutoff is January 1, 2025, per the [release notes](https://support.researchallofus.org/hc/en-us/articles/50653909888788-Curated-Data-Repository-CDR-version-9-Release-Notes)). The cohort uses year of birth because the Controlled Tier generalizes date of birth to the year ([Participant Privacy Protections](https://support.researchallofus.org/hc/en-us/articles/4552681983764-Participant-Privacy-Protections)), and ages are computed as event year minus year of birth. The filter runs in BigQuery, so queries return less data and finish faster.
- The first time you run a query, its result is saved in your bucket (`bq_exports/`). Running the notebook again reads the saved result instead of querying again. Use `refresh = TRUE` in `bq_to_df()` after changing a query.

## How the labs work

- Run a **checkpoint** cell after each task. A pass earns points; a miss prints a tip.
- `hint("1.C")` prints a clue for that task and costs 1 point.
- **Level 1** is for everyone. **Level 2 (boss level)** is optional.
- `scoreboard()` shows your score. Report your score only in the Zoom poll.

## Data rules

- Never share participant-level data, screenshots of it, or any count from 1 to 19 (including numbers someone could use to work one out). See the [Data and Statistics Dissemination Policy](https://support.researchallofus.org/hc/en-us/articles/360043016291).
- These notebooks contain code only. Don't commit outputs or data files back to this repository.

## Contact

sjones3@med.cuny.edu  
npourkey@med.cuny.edu
