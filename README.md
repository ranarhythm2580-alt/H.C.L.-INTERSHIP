# Heart Failure Data Analysis (EDA)

Descriptive exploratory data analysis of the Heart Failure clinical records
dataset using NumPy, Pandas and Matplotlib. No machine learning, only
cleaning, statistics and visualisation.

## Dataset
- 299 patient records, 12 original columns
- Features: age, anaemia, creatinine_phosphokinase, diabetes,
  ejection_fraction, high_bp, platelets, serum_creatinine, sex, smoking
- Target: `death_event` (0 = survived, 1 = died)

## Data Preprocessing
1. Standardised column names (lowercase, underscores) and renamed `death` to `death_event`
2. Dropped the `s_no` row-index column
3. Checked missing values (none found; median imputation is built in if needed)
4. Checked duplicates (none found)
5. Fixed data types (integer and binary columns)
6. Validity checks for impossible values (age range, ejection fraction, 0/1 flags, negatives)
7. Outlier detection with the IQR rule (NumPy), with outlier flags and capped (winsorised) copies
8. Feature engineering: age groups and readable labels (sex, death, diabetes, etc.)
9. Saved the output as `Heart_Failure_Cleaned.csv` (299 rows x 26 columns)

## Questions Answered
| # | Question |
|---|----------|
| 1 | Age distribution (mean, std, percentiles, age-group counts, histogram) |
| 2 | Record count by `death_event` (bar chart) |
| 3 | Mean, median, min, max of age, ejection fraction and serum creatinine |
| 4 | Average ejection fraction and serum creatinine by death_event group |
| 5 | Counts with and without diabetes, high blood pressure and anaemia |
| 6 | Missing values and duplicates check |

## Key Findings
- Mean age is about 60.8 years (range 40 to 95). The 60-69 group is the largest (93 patients).
- 96 patients (32.11%) had a death event; 203 (67.89%) survived.
- Patients who died had a lower average ejection fraction (33.47 vs 40.27) and a higher average serum creatinine (1.84 vs 1.18).
- Diabetes: 125 with / 174 without. High BP: 105 with / 194 without. Anaemia: 129 with / 170 without.
- IQR outliers: 29 in creatinine_phosphokinase, 21 in platelets, 29 in serum_creatinine, 2 in ejection_fraction.

## Tech Stack
Python, NumPy, Pandas, Matplotlib, Google Colab

## How to Run
1. Clone the repo and place `Heart_Failure_Details.csv` in the same folder as the notebook
2. Open the notebook in Jupyter or Google Colab
3. Run all cells top to bottom

## Files
- `Heart_Failure_Analysis.ipynb`: main notebook
- `Heart_Failure_Details.csv`: raw dataset
- `Heart_Failure_Cleaned.csv`: cleaned output
