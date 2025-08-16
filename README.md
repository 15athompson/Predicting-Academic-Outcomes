# Student Dropout and Academic Success Prediction

A machine learning project that predicts undergraduate student academic outcomes using statistical and ML methods, based on a Portuguese higher education study.

## Overview

This project addresses two key research questions:
- **RQ1**: Can prediction accuracy and F1-score be improved by incorporating first-year academic data?
- **RQ2**: Can results be further improved by modeling each target class separately?

The analysis aims to exceed the baseline Portuguese study results:
- F1-scores: 0.83 (Success), 0.68 (Failure), 0.44 (Relative success)
- Average F1-score: 0.65
- Accuracy: 0.73

## Dataset

**Source**: [UCI Machine Learning Repository - Predict Students Dropout and Academic Success](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)

**Target Classes**:
- Graduate (successful completion)
- Enrolled (still studying)
- Dropout (discontinued studies)

## Project Structure

```
├── S244679.ipynb              # Main analysis notebook
├── S244679.pdf                # Project report
├── TechnicalReport.docx       # Technical documentation
├── README.md                  # This file
└── generated_files/           # Output files from analysis
    ├── *.csv                  # Data summaries
    └── *.png                  # Visualization outputs
```

## Key Features

### Data Processing
- **Categorical Features**: Course, gender, scholarship status, tuition fees, etc.
- **Continuous Features**: Grades, age, curricular units, economic indicators
- **Feature Engineering**: Age groups, semester summaries, binary target encoding
- **Data Cleaning**: Outlier capping, minority class grouping, validation checks

### Machine Learning Models
- Logistic Regression
- Random Forest
- Decision Trees  
- Gradient Boosting
- Various sampling techniques (SMOTE, ADASYN, Random Over/Under-sampling)

### Analysis Workflow
1. **Data Preparation & Cleaning**
2. **Exploratory Data Analysis**
3. **Feature Selection** (Chi-squared, Kruskal-Wallis, Mann-Whitney tests)
4. **Model Training & Evaluation**
5. **Hyperparameter Tuning**
6. **Results Comparison**

## Key Functions

The notebook includes several utility functions for analysis:

- `save_figure()` - High-resolution plot saving
- `report_summary_of_categorical_columns()` - Categorical data summaries
- `report_summary_of_continuous_columns()` - Statistical summaries
- `plot_count_plot_grid()` - Categorical data visualization
- `cap_outliers_at_iqr_and_report()` - Outlier handling
- `plot_bar_grid()` - Target-split visualizations
- `plot_hist_and_box()` - Distribution analysis

## Requirements

```python
pandas
seaborn
matplotlib
numpy
scipy
scikit-learn
imbalanced-learn
```

## Usage

1. **Download the dataset** from the UCI repository
2. **Place the CSV file** in the project directory as `students_dropout_and_academic_success.csv`
3. **Run the notebook** `S244679.ipynb` cell by cell
4. **Generated outputs** will be saved automatically (CSV summaries, PNG visualizations)

## Results Summary

### RQ1 Findings
✅ **Confirmed**: Including first-year academic data significantly improved prediction performance over baseline models without academic data.

**Best Models**:
- Logistic Regression with SMOTE
- Decision Tree with Random Over-sampling
- Random Forest with Random Under-sampling  
- Gradient Boosting with SMOTE

### RQ2 Findings
✅ **Confirmed**: Binary classification models for individual target classes outperformed multi-class classification.

**Performance by Target**:
- **Graduate & Dropout**: Significant improvements in accuracy and F1-score
- **Enrolled**: Mixed results - higher accuracy but F1-score depends on precision/recall trade-offs

### Feature Importance
Key predictive features identified:
- First and second semester grades
- Units approved/enrolled
- Course selection
- Scholarship status
- Tuition fee status

## Model Performance

The hyperparameter-tuned models successfully exceeded the original Portuguese study benchmarks, with Gradient Boosting + SMOTE showing the best overall performance for multi-class prediction.

## Files Generated

During execution, the notebook creates:
- `initial_data_summary_cat.csv` - Initial categorical data summary
- `processed_data_summary_cat.csv` - Processed categorical data summary  
- `initial_data_summary_cont.csv` - Initial continuous data summary
- `processed_data_summary_cont.csv` - Processed continuous data summary
- Multiple PNG files for visualizations and model results

## Citation

Based on the research:
> M.V.Martins, D. Tolledo, J. Machado, L. M.T. Baptista, V.Realinho. (2021) "Early prediction of student's performance in higher education: a case study" Trends and Applications in Information Systems and Technologies, vol.1, in Advances in Intelligent Systems and Computing series. Springer. DOI: 10.1007/978-3-030-72657-7_16