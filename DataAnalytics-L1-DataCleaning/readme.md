# Airbnb Data Cleaning and Preprocessing

## Project Overview

This project focuses on cleaning and preprocessing the New York City Airbnb Open Data dataset using Python and Pandas. The objective is to prepare raw data for analysis by handling missing values, checking duplicate records, standardizing data, and removing outliers.

## Dataset Information

The dataset contains Airbnb listings in New York City with information such as:

* Listing ID
* Listing Name
* Host Information
* Neighbourhood Details
* Room Type
* Price
* Number of Reviews
* Availability
* Review Information

### Original Dataset Shape

```text
(48895, 16)
```

## Technologies Used

* Python
* Pandas
* NumPy
* Jupyter Notebook / VS Code

## Data Cleaning Steps Performed

### 1. Data Inspection

The dataset was explored using:

```python
df.head()
df.info()
df.describe()
```

### 2. Missing Value Analysis

Missing values were identified using:

```python
df.isnull().sum()
```

Missing values found:

| Column      | Missing Values |
| ----------- | -------------: |
| name        |             16 |
| host_name   |             21 |
| last_review |          10052 |

### 3. Missing Value Treatment

* Missing values in `name` were replaced with `"Unknown"`.
* Missing values in `host_name` were replaced with `"Unknown"`.
* Missing values in `last_review` were handled appropriately after date conversion.

### 4. Duplicate Record Check

Duplicate records were checked using:

```python
df.duplicated().sum()
```

Result:

```text
0 Duplicate Records Found
```

### 5. Date Conversion

The `last_review` column was converted to datetime format:

```python
pd.to_datetime()
```

### 6. Text Standardization

Text columns were cleaned using string operations:

```python
.str.strip()
```

### 7. Outlier Detection and Removal

The Interquartile Range (IQR) method was used to detect price outliers.

Number of Outliers Detected:

```text
2972
```

Outliers were removed to improve data quality.

## Final Dataset Shape

```text
(45923, 16)
```

## Key Outcomes

* Successfully handled missing values.
* Verified that no duplicate records existed.
* Converted date columns into proper datetime format.
* Standardized text-based columns.
* Detected and removed 2,972 outliers.
* Prepared a clean dataset for further analysis and machine learning.

## Conclusion

The Airbnb NYC dataset was successfully cleaned and preprocessed. The final dataset is more reliable, consistent, and suitable for exploratory data analysis, visualization, and predictive modeling tasks.

## Author

**Rudransh Mishra**

B.Tech CSE (Data Science)

Oasis Infobyte Data Analytics Internship
