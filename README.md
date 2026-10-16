# Data Preprocessing Techniques Using Python

## Overview

Data preprocessing is an important step in the Machine Learning workflow. Real-world datasets often contain missing values, inconsistent data types, unnecessary columns, and categorical features that need to be transformed before they can be used effectively.

This project demonstrates fundamental data preprocessing techniques using Python, Pandas, and Scikit-learn on a weather-related dataset.

The goal is to understand how to inspect raw data, handle missing values, transform data types, and encode categorical variables before proceeding to model development.

## Objectives

* Understand the structure and characteristics of a dataset.
* Identify missing values and examine data quality.
* Remove unnecessary columns.
* Handle missing values using group-based mean imputation and row removal.
* Convert columns to appropriate data types.
* Apply Label Encoding to categorical labels.
* Apply One-Hot Encoding using Pandas and Scikit-learn.
* Understand the importance of data preprocessing in Machine Learning.

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Jupyter Notebook

## Dataset

The project uses a weather-related dataset loaded from `environmental_data.csv`.

The original dataset contains 158 rows and 10 columns.

The columns include:

* `Ozone`
* `Solar.R`
* `Wind`
* `Temp C`
* `Month`
* `Day`
* `Year`
* `Temp`
* `Weather`
* `Unnamed: 0`

The dataset includes numerical and categorical features, making it useful for demonstrating common data preprocessing operations.

**Note:** The dataset file must be included in the repository for the notebook to run. If the dataset cannot be redistributed, provide instructions for obtaining it from its original source.

## Project Workflow

### 1. Importing Libraries and Loading Data

Imported Pandas and the encoding classes from Scikit-learn. Loaded the CSV dataset into a Pandas DataFrame.

### 2. Data Understanding

Explored the dataset using:

* `shape`
* `describe()`
* `dtypes`
* `unique()`
* `value_counts()`

These operations help understand the dataset's dimensions, statistical properties, data types, and categorical values.

### 3. Data Cleaning

Removed the unnecessary `Unnamed: 0` and `Temp C` columns.

Examined missing values using `isna().sum()`.

The `Ozone` column was removed because approximately 24% of its values were missing.

Missing values in `Solar.R` were handled using group-based mean imputation based on the `Weather` category. Rows that still contained missing values were subsequently removed.

### 4. Data Type Conversion

Standardized the values in the `Month` column and converted the column to an integer data type.

This helps ensure that the column contains consistent numerical values.

### 5. Label Encoding

Applied Scikit-learn's `LabelEncoder` to transform the categorical `Weather` labels into numerical values.

This demonstrates how categorical labels can be represented numerically.

### 6. One-Hot Encoding Using Pandas

Used `pd.get_dummies()` to transform the `Weather` column into separate binary columns:

* `Weather_C`
* `Weather_PS`
* `Weather_S`

Each column represents a weather category.

### 7. One-Hot Encoding Using Scikit-learn

Used `OneHotEncoder()` to encode the `Weather` feature.

Converted the resulting sparse matrix into a Pandas DataFrame using `toarray()` and `get_feature_names_out()` for easier inspection.

## Key Learnings

Through this project, I explored:

* Dataset inspection and exploratory data analysis.
* Missing-value detection and handling.
* Column removal and data cleaning.
* Data type conversion.
* Categorical feature encoding.
* Differences between Label Encoding and One-Hot Encoding.
* The role of data preprocessing in Machine Learning workflows.

## Repository Structure

```text
data-preprocessing-techniques/
│
├── Data_pre.ipynb
├── environmental_data.csv
└── README.md
```

The CSV file should be included only when redistribution is permitted.

## How to Run This Project

1. Clone or download this repository.

2. Install Python if it is not already installed.

3. Install the required libraries:

   ```bash
   pip install pandas scikit-learn jupyter
   ```

4. Open the project directory.

5. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

6. Open `Data_pre.ipynb`.

7. Ensure that `environmental_data.csv` is in the expected location.

8. Run the notebook cells sequentially.

## Future Improvements

* Compare different missing-value imputation strategies.
* Add numerical feature scaling using StandardScaler, MinMaxScaler, and RobustScaler.
* Combine encoded categorical features with the remaining numerical features.
* Build a reusable preprocessing pipeline using Scikit-learn.
* Prepare the processed data for a Machine Learning model.

## Author

**Sanjai**

B.Tech Student | Artificial Intelligence and Data Science

Interested in Python, Data Analysis, Machine Learning, and Data Science.

---

*This project is part of my hands-on journey to strengthen my Python and Machine Learning skills through practical projects.*
