# Student Risk Assessment – Group 6

## Project Overview

**Project Title:** Identifying Students at Risk of Academic Failure Using Educational Data

**Project Type:** Educational Data Analysis and Rule-Based Risk Classification

This project explores how educational data can be used to identify students who may be at risk of poor academic performance.

Using a student performance dataset, we develop a rule-based algorithm to classify students into three academic risk categories:

- Low Risk
- Medium Risk
- High Risk

The main objective is to investigate how previous academic failures, weekly study time, and school absences relate to student performance and how these factors can support the early identification of students who may need additional academic guidance.

## Research Question

**How effectively can previous academic failures, weekly study time, and school absences be used to identify students at risk of poor academic performance?**

## Dataset Description

The project uses a student performance dataset containing **649 student records and 33 attributes**.

The dataset includes information about students' academic performance, study habits, school attendance, and other educational and background factors.

For our algorithm, we selected three input features:

| Feature | Description |
|---------|-------------|
| `failures` | Number of previous academic failures |
| `studytime` | Weekly study-time category |
| `absences` | Number of school absences |
| `G3` | Final grade, used only for evaluation |

The final grade (`G3`) is not used to calculate the risk score. It is used separately to evaluate the algorithm's predictions.

## Dataset Source

The dataset used in this project is publicly available on Kaggle.

- **Dataset Name:** Students Performance Prediction
- **Platform:** Kaggle
- **Dataset Link:** [Students Performance Prediction – Kaggle](https://www.kaggle.com/datasets/adeelumar/students-performance-prediction/data)
- **Dataset Size:** 649 records and 33 attributes
- **Data Format:** CSV

The dataset provides information about students' academic performance and related educational factors.

We use this dataset for educational analysis and the development of a rule-based student risk classification algorithm.

**Dataset Credit:** The dataset is available through Kaggle. Credit for the original data belongs to its respective creators and contributors.

## Project Objectives

The main objectives of this project are:

1. Explore the relationship between selected educational factors and academic performance.
2. Identify relevant features for student risk classification.
3. Develop a simple and understandable rule-based algorithm.
4. Classify students into Low, Medium, and High Risk categories.
5. Evaluate the algorithm using actual final grades.
6. Present the methodology, results, and limitations through a project website.

## Project Methodology

Our proposed algorithm consists of seven stages.

### Stage 1: Data Loading

Import the student performance dataset using Python and Pandas.

### Stage 2: Data Cleaning

Check the dataset for:

- Missing values
- Invalid values
- Possible duplicate records

Retain valid records for further analysis.

### Stage 3: Initialisation

Initialise the variables and counters required for risk classification and evaluation.

### Stage 4: Risk Scoring

Calculate a risk score for each student using three selected features:

- Previous academic failures
- Weekly study time
- School absences

The current algorithm uses the following scoring rules:

| Condition | Risk Points |
|-----------|-------------|
| Two or more previous failures | +2 |
| One previous failure | +1 |
| Study-time category = 1 | +1 |
| Absences greater than 10 | +1 |

These are preliminary scoring rules that require further testing.

### Stage 5: Risk Classification

Students are classified according to their calculated risk scores.

| Risk Score | Classification |
|------------|----------------|
| 0 | Low Risk |
| 1–2 | Medium Risk |
| 3–4 | High Risk |

### Stage 6: Evaluation

The algorithm's predictions are evaluated using the final grade (`G3`).

For the current binary evaluation:

- `G3 < 10` represents academic failure.
- `G3 >= 10` represents academic success.
- High Risk is treated as a predicted failure.
- Low and Medium Risk are treated as predicted non-failures.

The evaluation uses:

- True Positives (TP)
- False Positives (FP)
- False Negatives (FN)
- True Negatives (TN)
- Prediction Accuracy

### Stage 7: Final Results

Display the following information:

- Data-cleaning summary
- Number of students in each risk category
- Evaluation results
- Prediction accuracy

## Exploratory Data Analysis

We performed descriptive statistics and correlation analysis to understand the relationships between the selected features and final academic performance.

### Correlation Analysis

The preliminary Pearson correlation results are:

| Feature | Correlation with G3 | Interpretation |
|---------|---------------------|----------------|
| Previous failures | -0.393 | Moderate negative relationship |
| Study time | +0.250 | Weak positive relationship |
| Absences | -0.091 | Very weak negative relationship |

### Key Observations

- Previous academic failures have the strongest relationship with final grades among the three selected features.
- Study time has a positive relationship with academic performance.
- Absences have a very weak negative relationship with final grades.
- Correlation does not establish a cause-and-effect relationship.

These findings provide a starting point for selecting and discussing the algorithm's risk-scoring rules.

## Preliminary Findings

Our initial analysis included **649 student records**.

### Risk Classification Results

| Risk Category | Number of Students | Percentage |
|---------------|-------------------:|-----------:|
| Low Risk | 367 | 56.5% |
| Medium Risk | 260 | 40.1% |
| High Risk | 22 | 3.4% |
| **Total** | **649** | **100%** |

### Evaluation Results

| Evaluation Metric | Result |
|-------------------|-------:|
| True Positives (TP) | 12 |
| False Positives (FP) | 10 |
| False Negatives (FN) | 88 |
| True Negatives (TN) | 539 |
| Prediction Accuracy | 84.90% |
| Failure Detection Rate (Recall) | 12.00% |

### Key Findings

- The algorithm classified most students as Low or Medium Risk.
- Only 22 students were classified as High Risk.
- The algorithm achieved 84.90% binary pass/fail prediction accuracy.
- Of the 100 students who actually failed, only 12 were correctly identified as High Risk.
- The algorithm missed 88 students who actually failed.
- Ten students were classified as High Risk but actually passed.
- The results demonstrate that high overall accuracy does not necessarily mean that an algorithm effectively identifies students who need academic support.

### Main Conclusion

Although the preliminary algorithm achieved relatively high overall accuracy, its ability to identify students who actually failed was limited.

This highlights the importance of evaluating missed failures and considering alternative scoring thresholds.

The findings are preliminary and may change as the algorithm is refined.

## Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Data processing and algorithm development |
| Pandas | Data loading, cleaning, and analysis |
| Matplotlib | Data visualisation |
| Seaborn | Statistical visualisation |
| Jupyter Notebook | Algorithm development and testing |
| HTML | Website structure |
| CSS | Website styling |
| GitHub | Version control and group collaboration |
| GitHub Pages | Website hosting |

## Project Website

The project website will present:

1. Project overview and research objectives
2. Dataset description and selected features
3. Algorithm design and pseudocode
4. Python implementation
5. Data analysis and visualisations
6. Preliminary results and evaluation
7. Group members and contributions

## Limitations

The current approach has several limitations:

- The algorithm uses predefined scoring rules rather than a trained machine-learning model.
- The selected thresholds have not yet been statistically optimised.
- Overall prediction accuracy is relatively high, but failure detection is low.
- Some students who actually failed were not identified as High Risk.
- The dataset does not contain a unique student identifier for confirming duplicate records.
- Correlations between educational factors and grades do not demonstrate causation.
- The availability of attendance information at the intended prediction time needs to be considered.

## Future Improvements

Possible improvements include:

- Testing alternative risk-scoring thresholds
- Reducing the number of missed failures
- Comparing different feature combinations
- Investigating additional educational factors
- Evaluating precision, recall, and other performance measures
- Improving the interpretation of risk categories
- Considering fairness, transparency, and responsible use of educational data

## Group Collaboration

This GitHub repository serves as a shared workspace for **Group 6**.

Team members will collaborate on:

- Dataset analysis
- Algorithm design and pseudocode
- Python implementation
- Data visualisation
- Website development
- Documentation
- Results and findings

All group members are welcome to contribute ideas, review the project files, and suggest improvements.

## Project Status

**Completed**

**website Link:** (https://sribobv15.github.io/Student_Rsik_Assesment_Group-6/)


