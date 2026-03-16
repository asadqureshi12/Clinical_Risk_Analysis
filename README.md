# Clinical Risk Stratification & Population Health Analytics

## Project Overview
The objective of this project was to develop a **data-driven risk stratification model** to identify high-risk patients within a clinical cohort. By integrating multiple clinical variables — including encounter frequency, disease burden, and polypharmacy — the analysis provides a framework for proactive intervention and optimized resource allocation.

## Risk Stratification Methodology
The project utilized a structured **Python-based data science pipeline** to develop a multi-factorial risk scoring algorithm:

- **Feature Engineering:** Aggregated EHR datasets to create quantitative indicators of patient complexity:
  - `encounter_count`
  - `condition_count`
  - `medication_count`
- **Risk Scoring Logic:** Assigned points based on:
  - Age > 65 → +2 points  
  - Number of conditions ≥ 3 → +2 points  
  - Encounters ≥ 5 → +1 point  
  - Medications ≥ 4 → +1 point  
  - Patients categorized into **Low (0–1), Medium (2–3), High (4+)** risk tiers.
- **Age Transformation:** Converted birthdates into age metrics to include age as a core risk factor.

## Key Findings
- **High-Risk Prevalence:**  
  - 72.6% (851 patients) classified as **High Risk**  
  - 19.0% (223 patients) as **Medium Risk**  
  - 8.3% (97 patients) as **Low Risk**  
  Indicates a population with significant multimorbidity.

- **Polypharmacy Burden:**  
  - Cohort-wide average: 36.7 medications per patient  
  - Median: 7 medications  
  - Wide gaps suggest outliers due to historical prescriptions, duplicates, or short-term medications.  
  - In production, outlier handling would be necessary for accurate risk scoring.

- **Clinical Intensity:**  
  - Average: 45.6 encounters and 7.2 diagnosed conditions per patient  
  - Median: 27 encounters and 7 conditions  
  - Shows high overall healthcare utilization.

- **Age & Utilization Trends:**  
  - Patients aged 81–100 average **67.6 encounters** and **80.1 medications**  
  - Patients aged 0–20 average **19.2 encounters** and **5.5 medications**  
  - Demonstrates sharp increases in healthcare utilization with age.

## Project Files
- `Clinical_Risk_Analysis.ipynb` — Jupyter notebook with full analysis workflow  
- `Clinical_Risk_Analysis_Output.csv` — Processed dataset including risk scores and risk levels
