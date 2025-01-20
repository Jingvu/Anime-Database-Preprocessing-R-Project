# Preprocessing Data
In this project, I applied my data wrangling and preprocessing skills to the Anime Dataset 2023 from Kaggle with the goal of cleaning, transforming, and preparing it for analysis. The dataset included user ratings, anime metadata, and user demographics, and I focused on ensuring data quality and consistency throughout. Key tasks involved importing and merging data, handling missing values, handling outliers, transforming variables, and visualizing results to extract meaningful insights. I particularly concentrated on three crucial areas: transforming data for better distribution, handling outliers to avoid skewed analysis, and managing missing values using various techniques. This repository not only demonstrates my approach to solving these challenges but also serves as a helpful resource with R code examples for anyone interested, as well as a reference for my future projects.

## Key Features of the Project
### 1. Data Import & Merging:
- Importing datasets from CSV and Excel files using R libraries.
- Merging two datasets (anime ratings and user details) to create a comprehensive dataset.

### 2. Data Cleaning & Preprocessing:
- Data type conversions: Converted columns like dates and categorical variables to their appropriate data types.
- Data tidying: Cleaned up columns with untidy and non-standard entries
  + The genre column contained multiple values separated by commas, listing all genres within a single cell.
  + The location column, which combined both city and country information and has non-standard country names.
- Handling missing values: Used various techniques:
  + Imputing missing values for numerical columns with the median.
  + Filling categorical columns with meaningful defaults.
  + Applying predictive modeling (mice package) for missing date values.
- Detecting & handling special value (infinite, NaN).
- Identifying potential data entry errors.

### 3. Handling Outliers:
- Detecting outliers
- Handling outliers using capping techniques to preserve data integrity while minimizing the impact of extreme values.

### 4. Data Transformation:
- Applied various mathematical transformations (square, cube, Box-Cox, log, log10, square root, cube root, reciprocal and reciprocal square) to make their distributions closer to normal, improving the accuracy of subsequent analyses.

## The Principle
### 1. Handling Outliers
#### a. Why?
Outliers can:
- Raise error variance
- Weaken the power of statistical tests
- Bias model parameter estimate\
However, outliers aren’t always removed. In some cases, like anomaly or fraud detection, outliers can provide valuable insights and should be investigated further.

#### b. There are two main types of outliers:
- **Univariate outliers**: involve a single variable and are identified within the distribution of that variable (can be detected by boxplot or distance based methods for normally distributed data)
- **Multivariate outliers**: involve multiple variables and are identified within the multidimensional distribution (can be detected by boxplot, scatter plot for a given pair of variables, The mahalanobis distance or QQ plot)

#### c. Common causes of outliers:
- **Data Entry Errors** (Ex: Entering "1000" instead of "100" for a salary value)
- **Measurement Errors**: made due to faulty measurement instruments (Ex: A thermometer recording a body temperature of 100°C)
- **Experimental Errors**: made during data extraction, experiment planning or execution (Ex: Inconsistent watering skews plant growth in a biology experiment)
- **Intentional Errors**: caused by underreporting or overreporting often in self-reported data (Ex: Respondents in a health survey overreport their daily exercise routines)
- **Data Processing Errors**: made during the integration or manipulation of data from multiple sources (Ex: Merging two datasets where one records height in cm and the other in inch)
- **Sampling Errors**: caused by non-representative sample (Ex: under 30 observations in the sample)

#### d. Handling Outliers
- **Excluding/Deleting**: if outliers are caused by data entry or processing errors or if there are very few outliers
- **Imputing**: if the outlier is due to a data entry/processing error (mean/median/specified value)
- **Capping**: replacing outliers with the nearest non-outlier values when extreme values are valid variations in the data, not errors
- **Transforming and binning values**: natural logarithm of a value reduces the variation
caused by outliers

### 2. Handling Missing Values
- Replace missing values with a constant defined
- Fill missing values using the mean, median or mode
- Apply predictive models to impute missing data, such as regression analysis, multiple imputation, random forests, nearest neighbors or methods like last observation carried forward/next observation carried backward. R offer packages such as mice, missForest, and impute for this purpose.
