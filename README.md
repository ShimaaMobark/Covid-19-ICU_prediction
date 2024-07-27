![image](https://github.com/user-attachments/assets/4758d954-b429-4c3d-a9ca-b6e406c2db87)

# Predicting COVID-19 ICU Admissions

**Author:** Shimaa Hamadelnel  
**Date:** 07/26/2024

## Introduction

Brazil has been one of the countries most affected by the COVID-19 pandemic, with more than 16 million confirmed cases and 454,429 confirmed deaths as of May 26, 2021. The country faced significant challenges due to a strained hospital capacity.

A data science team from a top-tier hospital in Brazil released a dataset on Kaggle, inviting solutions from the public to reduce strain on ICU beds. The objective is to develop a machine learning model to predict if a patient with a confirmed COVID-19 case will require admission to the ICU.

## Objective

This report presents an analysis of ICU admissions with a focus on predictive modeling and machine learning techniques to forecast patient admissions, identify trends, and provide actionable insights to improve healthcare outcomes.

## Data Collection

The dataset is publicly available on Kaggle. It includes patient demographics, admission reasons, length of stay, and outcomes. Key variables in the dataset are age, gender, medical history, and ICU admission.

## Exploratory Data Analysis (EDA)

### Steps

1. **Understand the Data:**
   - **Load the Data:** Use `pd.read_excel` to load the data.
   - **Inspect Data Types and Summary Statistics:** Use `df.info()` and `df.describe()` to understand data types and summary statistics.
   - **Check for Missing Values:** Use `df.isnull().sum()` to identify missing values.

2. **Identify Trends and Patterns:**
   - **Distribution of Target Variable:** Analyze ICU admissions to understand class balance.
   - **Correlation Analysis:** Use `df.corr()` and visualize with a heatmap.
   - **Feature Analysis:** Explore individual feature distributions.

3. **Visualize Key Insights:**
   - **Histograms:** For continuous variables.
   - **Box Plots:** To identify outliers.
   - **Bar Charts:** Frequency of categorical features.
   - **Pie Charts:** Distribution of numerical features.

## Analysis and Findings

### Descriptive Analysis

1. **Patient Visit Identifier**
   - 385 unique values, each patient is represented by 5 rows.

2. **Age Above 65**
   - Mean: 0.47
   - Standard Deviation: 0.50

3. **Disease Grouping**
   - Disease Grouping 1: Mean = 0.11
   - Disease Grouping 2: Mean = 0.03
   - Disease Grouping 3: Mean = 0.10
   - Disease Grouping 4: Mean = 0.02
   - Disease Grouping 5: Mean = 0.13
   - Disease Grouping 6: Mean = 0.05

4. **Health Conditions**
   - HTN: Mean = 0.21
   - Immunocompromised: Mean = 0.16

5. **Laboratory Metrics**
   - Albumin (Median, Mean, Min, Max): Average = 0.53, Standard Deviation = 0.15
   - Albumin Difference: Mean = -1.00

6. **Blood Gas and Chemistry Metrics**
   - Most metrics have mean values around -0.9 to 0.3.

7. **Blood Cell Counts**
   - Leukocytes, Lymphocytes, Neutrophiles: Median values around -0.74 to -0.71.

8. **Gas Exchange Metrics**
   - P02 and PC02: Mean values consistently around -0.78.

9. **Lactate**
   - Median, Mean, Min, Max: Values around 0.27 to 1.00 with high standard deviation.

### Summary
- **Total Admissions:** 1410 non-ICU and 515 ICU admissions.
- **Admission Reasons:** Respiratory failure, sepsis, postoperative complications.
- **Demographic Distribution:** Nearly half are over 65, balanced gender distribution.
- **Disease and Health Conditions:** Certain conditions and disease groupings are more prevalent.

## Preprocess the Data

### Objective

Machine learning techniques including Random Forest, Decision Trees, and SVC were applied to analyze ICU admission data.

### Steps

1. **Handle Missing Values:**
   - Imputation: Fill missing values using mean or median.

2. **Encode Categorical Variables:**
   - One-Hot Encoding: For categorical variables like GENDER and WINDOW.
   - Label Encoding: For ordinal features if needed.

3. **Normalize/Scale Numerical Variables:**
   - Standardization/Normalization: Use MinMaxScaler to fit between -1 and 1.

4. **Split the Data:**
   - Training and Testing Sets: 80-20 split using `train_test_split`.

## Develop ML Models

### Objective

Train and evaluate machine learning models.

### Steps

1. **Train Models:**
   - Random Forest: Initial model with 93% accuracy.
   - After preprocessing: Random Forest 86%, SVM 72%, Logistic Regression 85%.

2. **Evaluate Models:**
   - Metrics: Accuracy, precision, recall, F1-score.
   - Analyze performance and check for overfitting.
   - Feature Importance and Hyperparameter Tuning.

## Machine Learning Insights

- **Trend Analysis:** Patterns in ICU admissions based on demographics and conditions.
- **Key Factors:** Random Forest model with 93% accuracy indicates high reliability in predicting ICU admission.

## Conclusion

- **Random Forest:** Achieved the highest accuracy (93%) and is most suitable for this classification task due to its ability to handle numerous features and provide feature importance.

## Recommendations for Future Projects

1. **Evaluate Preprocessing Methods:** Test and compare imputation and encoding techniques.
2. **Implement Cross-Validation:** Use cross-validation to evaluate preprocessing strategies.
3. **Optimize Hyperparameters:** Systematically explore and optimize hyperparameters.

