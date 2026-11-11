# DataScience-Hackathon

# H1N1 Vaccine Uptake Prediction

## Project Overview

This project was developed as part of a Data Science Hackathon to predict whether an individual is likely to receive the H1N1 influenza vaccine based on demographic information, health conditions, opinions, and behavioural factors.

The main objective was to build and evaluate machine learning models that predict H1N1 vaccine uptake and identify an effective prediction strategy while considering the potential costs associated with vaccination and hospitalisation.

The project uses **Dataset B**, with `h1n1_vaccine` as the target variable.

## Team Members

This project was completed by all eight members of **Team Likith**. Every member contributed equally to the hackathon through collaboration, analysis, implementation, model development, evaluation, and project preparation.

1. Likith Rathipinni
2. Mohan Marthala
3. Shivani Bashetty
4. Sandeep Patel
5. Manikanta Nagendla
6. Gnana Malleswari Pagadala
7. Gopal Reddy Marella
8. Sai Subramanya Teja Sarvade

## Problem Statement

The goal is to predict whether a respondent will receive the H1N1 vaccine.

The target variable is:

- `h1n1_vaccine`
  - `1` – Respondent received or is willing to receive the H1N1 vaccine, as represented by the dataset label.
  - `0` – Respondent did not receive or is not willing to receive the H1N1 vaccine, as represented by the dataset label.

The dataset includes demographic, behavioural, health-related, and opinion-based features that may influence vaccination decisions.

## Project Workflow

The project followed these major stages:

### 1. Data Loading and Understanding
- Loaded the training, testing, and sample submission datasets.
- Examined dataset dimensions, column types, and descriptive statistics.
- Identified missing values and checked for duplicate records.
- Checked respondent IDs and potential overlap between training and testing datasets.

### 2. Exploratory Data Analysis (EDA)
- Analysed the distribution of the target variable.
- Examined numerical, ordinal, and categorical features.
- Visualised distributions using plots.
- Investigated relationships and correlations between selected features.

### 3. Data Preprocessing
Different preprocessing strategies were applied according to feature types.

- **Numerical and ordinal features:** Median imputation and standard scaling.
- **Binary features:** Most-frequent-value imputation.
- **Categorical features:** Most-frequent-value imputation and one-hot encoding.
- Used a column transformer and pipeline-based preprocessing to ensure consistent transformations.

### 4. Model Development

The following machine learning algorithms were implemented and evaluated:

1. Logistic Regression
2. Random Forest
3. Extra Trees Classifier
4. Support Vector Machine (SVM)
5. AdaBoost Classifier

### 5. Model Evaluation

Models were evaluated using the following classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Brier Score
- Log Loss

A stratified train-validation split was used to preserve the target class distribution.

### 6. Hyperparameter Tuning

Randomized Search with cross-validation was used to explore model hyperparameters and improve model performance.

ROC-AUC was used as the hyperparameter search scoring metric.

### 7. Threshold and Cost Analysis

Instead of relying only on the default classification threshold of 0.50, different probability thresholds were tested to understand their effect on vaccination predictions and estimated costs.

The cost analysis considered:

- Vaccination cost: $500
- Estimated hospitalisation cost: $25,000
- Estimated baseline hospitalisation risk: 0.451%
- Assumed vaccine effectiveness against hospitalisation: 61%

The analysis estimated vaccination and hospitalisation costs under different prediction outcomes.

**Important assumption:** The dataset does not contain individual hospitalisation outcomes. Therefore, hospitalisation costs were estimated using external population-level assumptions rather than an individually trained hospitalisation prediction model. These estimates should be interpreted as assumptions used for comparative analysis, not as actual observed costs.

### 8. Final Predictions and Submission

- Selected probability thresholds for the evaluated models.
- Retrained tuned models using the complete training dataset.
- Generated predictions for the test dataset.
- Created individual submission CSV files for all five models.
- Validated submission formats, respondent IDs, missing values, and binary predictions.
- Packaged the submission files into a ZIP archive.

## Models Included in the Submission

The final submission archive contains:

| File | Model |
|---|---|
| `logistic_regression_submission.csv` | Logistic Regression |
| `random_forest_submission.csv` | Random Forest |
| `extra_trees_submission.csv` | Extra Trees |
| `svm_submission.csv` | Support Vector Machine |
| `adaboost_submission.csv` | AdaBoost |

Each submission contains:

- `respondent_id`
- `h1n1_vaccine`

## Repository Structure

```text
H1N1-Vaccine-Uptake-Prediction/
│
├── README.md
├── untitled4.py
│
├── H1N1_Final_Submissions.zip
│   ├── logistic_regression_submission.csv
│   ├── random_forest_submission.csv
│   ├── extra_trees_submission.csv
│   ├── svm_submission.csv
│   └── adaboost_submission.csv
│
└── Dataset/
    ├── training_set_features.csv
    ├── test_set_features.csv
    └── submission_format.csv
```

*Note: The Dataset folder represents the expected input structure. Include the original dataset files separately if they are permitted to be shared.*

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## How to Run the Project

1. Clone or download the project repository.
2. Open the Python notebook or script in Google Colab or a local Python environment.
3. Install the required dependencies if they are not already available:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

4. Place the training, testing, and sample submission CSV files in the expected directory.
5. Update file paths if necessary.
6. Run the notebook or Python script sequentially.
7. The final submission CSV files and ZIP archive will be generated after execution.

## Team Contribution and Work Distribution

All eight members contributed equally to the successful completion of this hackathon. The work was organised into the following areas to ensure collaboration and balanced participation.

| Team Member | Primary Work Area |
|---|---|
| Likith Rathipinni | Project coordination, problem understanding, and overall workflow integration |
| Mohan Marthala | Data loading, data understanding, and data quality checks |
| Shivani Bashetty | Exploratory Data Analysis and data visualisation |
| Sandeep Patel | Feature analysis and preprocessing strategy |
| Manikanta Nagendla | Machine learning model development and baseline evaluation |
| Gnana Malleswari Pagadala | Hyperparameter tuning and model performance comparison |
| Gopal Reddy Marella | Probability threshold optimisation and cost analysis |
| Sai Subramanya Teja Sarvade | Final predictions, submission validation, and project documentation |

### Equal Contribution Statement

Although responsibilities were organised into different primary work areas, the project was completed through collective effort and continuous collaboration.

All eight members participated in discussions, shared ideas, reviewed the implementation, contributed to decision-making, and supported the overall development of the solution.

**We confirm that all eight team members contributed equally to this hackathon project.**

## Conclusion

This project demonstrates an end-to-end machine learning workflow for predicting H1N1 vaccine uptake. Multiple classification algorithms were developed, tuned, and evaluated using classification and probability-based metrics.

The project also explored probability threshold optimisation and estimated vaccination and hospitalisation costs to understand the practical implications of different prediction strategies.

Through collaborative development, experimentation, and evaluation, the team produced five model-based prediction submissions.

---

**Project:** H1N1 Vaccine Uptake Prediction  
**Team Size:** 8 Members  
**Contribution:** Equal contribution from all team members  
**Environment:** Python / Google Colab
