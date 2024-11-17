# Preprocessing Data
In this project, I applied my data wrangling and preprocessing skills to the Anime Dataset 2023 from Kaggle with the goal of cleaning, transforming, and preparing it for analysis. The dataset included user ratings, anime metadata, and user demographics, and I focused on ensuring data quality and consistency throughout. Key tasks involved importing and merging data, handling missing values, transforming variables, and visualizing results to extract meaningful insights. I particularly concentrated on three crucial areas: transforming data for better distribution, handling outliers to avoid skewed analysis, and managing missing values using various techniques. This repository not only demonstrates my approach to solving these challenges but also serves as a helpful resource with R code examples for anyone interested, as well as a reference for my future projects.

## Key Features of the Project
### 1. Data Import & Merging:
- Imported datasets from CSV and Excel files using R libraries (readxl, readr).
- Merged two datasets (anime ratings and user details) to create a comprehensive dataset using left_join.

### 2. Data Cleaning & Preprocessing:
- Data type conversions: Converted columns like dates and categorical variables to their appropriate data types.
- Data tidying: Cleaned and split columns like genre and location to enhance analysis.
- Handling missing values: Used various techniques:
  + Imputed missing values for numerical columns with the median.
  + Filled categorical columns with meaningful defaults.
  + Applied predictive modeling (mice package) for missing date values.

### 3. Data Transformation & Consistency:
- Introduced a new variable, Consistency_Score, to analyze user rating behavior.
- Handled outliers using capping techniques to preserve data integrity while minimizing the impact of extreme values.
- Transformed skewed variables (e.g., score) using mathematical transformations (e.g., square, cube, Box-Cox) to achieve normal distribution for better analysis.

### 4. Visualizations & Analysis:
- Visualized the distribution of ratings, user engagement, and consistency scores using ggplot2.
- Generated boxplots, histograms, and summary statistics to understand data patterns and detect anomalies.
- Analyzed the impact of data transformations on variable distributions.
