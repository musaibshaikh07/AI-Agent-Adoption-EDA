# AI Agent Adoption & Workplace Productivity — EDA Project

## Project objective
Analyze a 523-record dataset (2024–2026) to explore AI-agent adoption, industry and job-role representation, productivity changes, weekly time savings, training, satisfaction, trust, and overall AI impact.

## Files
- `AI_Agent_Adoption_EDA_Portfolio.ipynb` — complete, executed Jupyter Notebook with data audit, cleaning, EDA, feature engineering, visualizations, findings, and limitations.
- `AI_Agent_Adoption_Workplace_Productivity_2024_2026.csv` — supplied source dataset (kept unchanged).
- `outputs/ai_agent_adoption_cleaned.csv` — cleaned dataset with missingness flags and engineered features.
- `outputs/data_quality_report.csv` — missingness audit before imputation.
- `outputs/imputation_log.csv` — imputation method and fill value per affected column.
- `outputs/numeric_range_audit.csv` — values outside assumed ranges, flagged for review rather than silently deleted.
- `outputs/outlier_summary.csv` — IQR-based potential outlier counts.
- `outputs/numeric_correlation_matrix.csv` — numerical correlation matrix.

## How to run
1. Extract the project ZIP.
2. Open the project folder in Jupyter Notebook or JupyterLab.
3. Install dependencies if needed:
   `pip install pandas numpy matplotlib seaborn jupyter`
4. Open `AI_Agent_Adoption_EDA_Portfolio.ipynb`.
5. Run all cells from top to bottom. The CSV is expected in the same folder as the notebook; outputs are saved to `outputs/`.

## Selected findings
- 523 records across 2024–2026; 120 records in 2024, 185 in 2025, and 218 in 2026.
- Moderate AI-agent usage is the largest category (175; 33.5%), followed by High (162; 31.0%).
- Technology is the most represented industry (106 records).
- Software Engineer is the most represented job role (80 records).
- Among 517 originally observed productivity values, 396 are positive and 121 are negative; observed mean is about 10.26% and median 8.1%.
- Multi-Agent Systems have the highest mean weekly hours saved among agent types with meaningful sample counts (97 records; mean 11.28 hours).
- Average training hours increase across the recorded AI skill levels: Beginner 8.93, Intermediate 15.81, Advanced 24.95, Expert 40.72.
- Pearson correlation between training hours and productivity change is approximately 0.22; between productivity change and weekly hours saved approximately 0.55; between job satisfaction and trust in AI approximately 0.38.

## Methodology and caveats
- Exact duplicate rows: none detected.
- 90 missing cells across 10 columns were found before imputation. Numerical columns were imputed with the median; categorical columns with the mode. Missingness flags and an imputation log are retained.
- Category spelling/capitalization variants were harmonized only when they clearly represented the same category.
- IQR outliers and numeric range issues are flagged for review, not automatically removed. Check the source data dictionary before deciding whether unusual values are invalid.
- `Automation_Intensity` is not calculated because the dataset does not provide a documented total-workload denominator.
- `Cost_Per_Hour_Saved` is monthly AI cost divided by estimated monthly hours saved (weekly hours × 4.345); it is undefined when weekly hours saved is zero.
- This is observational data. Correlation does not establish causation, and sample representativeness is unknown. Annual row counts describe this file, not overall market growth.
