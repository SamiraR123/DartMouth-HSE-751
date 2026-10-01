# Diabetes Risk Factor Analysis

## Purpose
This project explores which patient characteristics (glucose, BMI, age, etc.) are associated with diabetes outcome, using descriptive statistics, visualizations, and inferential tests. It was completed as a reproducibility exercise for Programming for Health Data Science (HSE 751).

## Description
The notebook loads a clinical dataset, flags and corrects a data quality issue (physiologically implausible zero values in several columns), then analyzes the cleaned data with summary statistics, plots, a Spearman correlation matrix, and two statistical tests: a t-test comparing glucose between patients with and without diabetes, and a Mann-Whitney U test comparing BMI between the same two groups.

## Dataset Source and Requirements
The project uses the diabetes example dataset (`Example Dataset_Diabetes.csv`) provided with the analysis. It contains 768 patients, each with 8 clinical measurements and a binary diabetes outcome column (`Outcome`: 1 = diabetes, 0 = no diabetes). The file is included in this repository. The notebook expects the columns in this exact order: `Pregnancies`, `Glucose`, `D_BP`, `Skin_Thickness`, `Insulin`, `BMI`, `Pedigree`, `Age`, `Outcome`.

## Required Software and Libraries
- Python 3.10+
- pandas 2.2.3
- numpy 2.1.3
- matplotlib 3.10.0
- seaborn 0.13.2
- scipy 1.16.3

These are the versions the notebook was tested with and prints at runtime. Google Colab's default runtime already includes all of them, so no installation step is usually needed there. For a local Jupyter install, run:
```
pip install pandas==2.2.3 numpy==2.1.3 matplotlib==3.10.0 seaborn==0.13.2 scipy==1.16.3
```

## How to Run
1. Open `starter_diabetes_risk_factor_analysis_SR.ipynb` in Google Colab (link below) or Jupyter.
2. Make sure `Example Dataset_Diabetes.csv` is in the same folder as the notebook (already true if you cloned this repo; in Colab, upload it via the file browser if you didn't clone the repo).
3. Run all cells top to bottom, or use **Runtime → Restart session and run all**.

## Expected Output
- Printed package versions and a confirmation that the dataset loaded and passed validation.
- A data-preparation summary showing how many implausible zero values were recoded and imputed per column.
- Summary statistics, four figures (two histograms, a boxplot, a scatter plot, and a correlation heatmap).
- Printed results for a t-test (Glucose by outcome) and a Mann-Whitney U test (BMI by outcome), both significant at p < 0.001.
- A Results and Conclusions section summarizing the findings above.

## Assumptions and Limitations
- `Glucose`, `D_BP`, `Skin_Thickness`, `Insulin`, and `BMI` use 0 to represent missing values rather than `NaN`. These were recoded and filled with each column's median; `Insulin` and `Skin_Thickness` had the most missing values (374 and 227 of 768), so results involving those two columns should be read with that limitation in mind.
- The dataset includes only female patients, so findings may not generalize to other populations.
- All relationships reported are correlational, not causal.

## Computational Environment
Built and tested in Google Colab (Python 3.12). Also runs in a standard local Jupyter Notebook installation with the package versions listed above.

## Google Colab Link
https://colab.research.google.com/drive/1ZKwg5QcdUHQPo75HoMWgY7gOAsvrK49p?usp=sharing

## Repository Contents
- `starter_diabetes_risk_factor_analysis_SR.ipynb`: completed, executable notebook
- `Example Dataset_Diabetes.csv`: dataset used by the notebook
- `README.md`: this file
- `reproducibility_summary.md`: summary of reproducibility issues found and fixed
