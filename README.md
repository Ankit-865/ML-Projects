# Insurance Cost Prediction using Machine Learning

## Project Overview

This project focuses on analyzing and predicting medical insurance charges based on customer demographic and health-related attributes. The dataset contains information such as age, gender, BMI, number of children, smoking status, region, and insurance charges.

The project covers the complete Machine Learning workflow including:

* Exploratory Data Analysis (EDA)
* Data Cleaning and Preprocessing
* Feature Engineering
* Statistical Feature Selection
* Data Scaling
* Correlation Analysis

---
## Dataset Information

The dataset contains **1338 records** and **7 features**.

### Features

| Feature  | Description                               |
| -------- | ----------------------------------------- |
| age      | Age of the individual                     |
| sex      | Gender (Male/Female)                      |
| bmi      | Body Mass Index                           |
| children | Number of dependents covered by insurance |
| smoker   | Smoking status                            |
| region   | Residential region                        |
| charges  | Medical insurance cost (Target Variable)  |

---

## Exploratory Data Analysis (EDA)

Performed the following analyses:

* Dataset shape and structure analysis
* Statistical summary using `describe()`
* Missing value detection
* Distribution analysis using histograms
* Outlier detection using boxplots
* Category distribution using count plots
* Correlation heatmap

### Key Findings

* No missing values found.
* Dataset contains one duplicate record.
* Smokers tend to have significantly higher insurance charges.
* Age and BMI show positive correlation with insurance costs.

---

## Data Cleaning & Preprocessing

### Steps Performed

1. Removed duplicate records.
2. Encoded categorical variables:

   * Male → 0
   * Female → 1
   * Non-Smoker → 0
   * Smoker → 1
3. Renamed columns for better readability:

   * sex → is_female
   * smoker → is_smoker
4. Applied One-Hot Encoding on:

   * Region
5. Standardized numerical features:

   * Age
   * BMI
   * Children

---

## Feature Engineering

### BMI Category Creation

Created a new feature called **BMI Category**:

| BMI Range   | Category    |
| ----------- | ----------- |
| < 18.5      | Underweight |
| 18.5 - 24.9 | Normal      |
| 25 - 29.9   | Overweight  |
| > 30        | Obese       |

The categorical feature was converted using One-Hot Encoding.

---

## Feature Selection

### Pearson Correlation Analysis

Correlation was calculated between input features and insurance charges.

#### Top Correlated Features

| Feature            | Correlation |
| ------------------ | ----------- |
| is_smoker          | 0.787       |
| age                | 0.298       |
| bmi_category_Obese | 0.200       |
| bmi                | 0.196       |

### Chi-Square Test

Categorical features were evaluated using the Chi-Square statistical test.

#### Selected Features

* is_smoker
* is_female
* region_southeast
* bmi_category_Obese

---

## Final Feature Set

The final dataset includes:

* age
* is_female
* bmi
* children
* is_smoker
* region_southeast
* bmi_category_Obese
* charges (Target)

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Scikit-Learn
* Jupyter Notebook

---

## Project Structure

```text
ML-Projects/
│
├── MLwork.ipynb
├── insurance.csv
├── README.md
└── .gitignore
```

---

## Future Improvements

* Train and compare multiple regression models.
* Hyperparameter tuning.
* Model evaluation using RMSE, MAE, and R² Score.
* Deploy the model using Streamlit or Flask.
* Build a web-based insurance cost prediction application.

---

## Author

**Ankit Namdev**

GitHub: https://github.com/Ankit-865
