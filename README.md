# Panic Attack Dataset Analysis | Snowflake + Power BI

An end-to-end descriptive data analysis project using **Snowflake SQL** and **Microsoft Power BI**. The project explores a sample dataset of 1,200 records and presents the results through a four-page interactive dashboard.

## Project Overview

The analysis examines recorded panic-attack duration, trigger categories, age and gender groups, sleep-hour categories, medical-history values, and medication/therapy combinations.

### Tools and workflow

- **Source:** `panic_attack_dataset.csv`
- **Data warehouse and SQL analysis:** Snowflake
- **Power BI connection:** Import Mode
- **Dashboard:** Power BI Desktop
- **Presentation:** Gamma.app

```text
CSV dataset
    |
    v
Snowflake table
    |
    v
Snowflake SQL Worksheet
(data validation, summary statistics, group comparisons)
    |
    v
Power BI Desktop (Import Mode)
    |
    v
Interactive four-page dashboard
```

## Dataset

- 1,200 rows
- 21 columns
- 1,200 unique IDs
- 122 blank values in `Medical_History` in the uploaded source CSV

Main fields include age, gender, panic attack frequency, duration, trigger, heart rate, symptoms, medical history, medication, caffeine intake, exercise frequency, sleep hours, alcohol consumption, smoking, therapy, and panic score.

## Dashboard Pages

1. **Panic Attack Overview**: headline KPIs and overall record distributions.
2. **Attack Duration & Trigger Analysis**: duration groups and average duration by trigger.
3. **Demographic Analysis**: record distribution and metrics by age and gender.
4. **Lifestyle & Medical History Analysis**: sleep groups and medical-history categories.

## Selected Findings

- Average recorded duration: **24.39 minutes**.
- Median duration: **24 minutes**.
- Sample standard deviation of duration: approximately **11.40 minutes**.
- Average panic score: **5.57**.
- Average recorded attack frequency: **4.41**.
- Medium duration group (15–24 minutes): **323 records (26.92%)**.
- Medium and Long duration groups combined (15–34 minutes): **626 records (52.17%)**.
- Caffeine trigger group has the highest average recorded duration: **25.04 minutes**.
- Age group 46–55 has the highest record count: **272**.
- The 5–7 hours sleep group has the highest average panic score: **5.65**.

These are descriptive patterns in the sample dataset. They do not establish cause and effect or support medical conclusions.

## Repository Structure

```text
panic-attack-data-analysis/
├── README.md
├── report/
│   └── project_report.md
├── sql/
│   └── panic_attack_analysis.sql
├── presentation/
│   └── gamma_presentation_prompt.txt
├── dashboard/
│   └── (add your Power BI .pbix file and screenshots)
└── data/
    └── (optional: add the source CSV only if sharing is permitted)
```

## How to Reproduce

1. Load `panic_attack_dataset.csv` into a Snowflake table.
2. Update the table reference in `sql/panic_attack_analysis.sql` if your database or schema name differs.
3. Run the SQL sections in Snowflake SQL Worksheet.
4. Connect Power BI Desktop to Snowflake.
5. Select **Import** mode and load the analysis table.
6. Create the calculated columns, measures, charts, and slicers.
7. Refresh Power BI after changes to the Snowflake source.
8. Compare key totals and category boundaries between Snowflake and Power BI.

## Data Quality Note

The uploaded CSV has 122 blank `Medical_History` values. The Power BI report displayed a `None` category with 122 records. Confirm whether those blanks were converted to `None` during loading or modelling. Until confirmed, label this category **Not recorded** rather than treating it as a confirmed medical-history value.

Use consistent, non-overlapping age groups:

- 18–25
- 26–35
- 36–45
- 46–55
- 56–64

Use consistent duration groups:

- Short: 5–14 minutes
- Medium: 15–24 minutes
- Long: 25–34 minutes
- Very Long: 35–44 minutes

## Limitations

- The dataset is a sample dataset; its real-world source and sampling method are not documented.
- Definitions and units for some fields need confirmation, including the time period for attack frequency and the scale definition for panic score.
- Blank medical-history values require clear handling.
- Medication and therapy comparisons are observational and cannot establish treatment effectiveness.
- The analysis does not establish causal relationships and is not medical advice.
- No date field is available for time-based trend analysis.

## Deliverables

- Snowflake SQL analysis queries.
- Four-page Power BI dashboard.
- Detailed project report.
- Project presentation.

## Author

Add your name, LinkedIn profile, and GitHub profile here.

---

**Disclaimer:** This project is for data analytics learning and portfolio demonstration. It is not a clinical study and should not be used for diagnosis or treatment decisions.
