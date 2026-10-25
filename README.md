

# Student Risk Assessment – Group 6

## Project Overview

**Project Title:** Identifying Students at Risk of Academic Failure Using Educational Data

**Project Type:** Educational Data Analysis and Rule-Based Risk Classification

This project aims to identify students who may be at risk of poor academic performance by analysing selected educational factors.

Using a student performance dataset, we develop a rule-based algorithm to classify students into three academic risk categories: **Low Risk, Medium Risk, and High Risk**.

The objective is to explore how educational data can help identify students who may benefit from additional academic guidance and support.

## Research Question

How effectively can previous academic failures, weekly study time, and school absences be used to identify students at risk of poor academic performance?

## Dataset Description

The project uses a student performance dataset containing **649 student records and 33 attributes**.

We selected three features for risk classification:

- **Previous Failures (`failures`):** Number of previous academic failures.
- **Study Time (`studytime`):** Weekly study-time category.
- **Absences (`absences`):** Number of school absences.

The final grade (`G3`) is used separately to evaluate the algorithm's predictions.

## Project Methodology

Our algorithm consists of seven stages:

1. **Data Loading:** Import the student performance dataset.
2. **Data Cleaning:** Check missing values, invalid values, and possible duplicate records.
3. **Initialisation:** Prepare variables and counters.
4. **Risk Scoring:** Calculate risk scores using the selected features.
5. **Risk Classification:** Classify students as Low, Medium, or High Risk.
6. **Evaluation:** Compare predictions with actual final grades using G3.
7. **Final Results:** Display risk categories, student counts, and prediction accuracy.

## Preliminary Findings

Our initial analysis included 649 student records.

### Risk Classification Results

| Risk Category | Students | Percentage |
|---------------|----------|------------|
| Low Risk | 367 | 56.5% |
| Medium Risk | 260 | 40.1% |
| High Risk | 22 | 3.4% |
| **Total** | **649** | **100%** |

### Evaluation Results

- **Prediction Accuracy:** 84.90%
- **True Positives:** 12
- **False Positives:** 10
- **False Negatives:** 88
- **True Negatives:** 539

Although the algorithm achieved 84.90% binary prediction accuracy, it correctly identified only 12 of the 100 students who actually failed.

This indicates that the current scoring rules require further improvement to identify more students at risk.

These results are preliminary and depend on the selected thresholds.

## Technologies Used

- **Python:** Data processing and risk classification
- **Pandas:** Dataset loading and cleaning
- **Jupyter Notebook:** Algorithm development and testing
- **HTML and CSS:** Website development
- **GitHub:** Version control and team collaboration
- **GitHub Pages:** Website hosting

## Project Website

The project website will present:

- Project overview and research objectives
- Dataset description and selected features
- Algorithm design and pseudocode
- Python implementation
- Risk classification results
- Evaluation findings
- Group members and contributions

## Limitations and Future Improvements

The algorithm uses predefined scoring rules rather than a trained machine-learning model.

The current model has limitations, particularly in identifying students who actually fail.

Future improvements may include:

- Testing alternative risk-scoring thresholds
- Reducing the number of missed failures
- Investigating additional educational factors
- Improving the evaluation methodology
- Considering fairness and responsible use of student data

## Group Collaboration

This repository is a shared workspace for Group 6.

Team members will collaborate on dataset analysis, algorithm development, documentation, website design, and project findings.

**Project Status:** In Development
