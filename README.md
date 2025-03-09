# NYC Airbnb Data Cleaning & Outlier Removal
## Project Overview
This project focuses on cleaning and preprocessing the AB_NYC_2019 dataset, including handling missing values, identifying and removing outliers, and preparing the data for further analysis. 
Various outlier detection methods—Z-score, IQR, and Percentile methods were tested to determine the most effective approach.

## Dataset
- **Name:** AB_NYC_2019 CLEANING DATA.csv
- **Size:** 48,895 entries, 16 columns
- **Data Types:** Mixed (Integer, Float, String)

## Preprocessing
 **1. Handling Missing Values:**

Columns with Missing Values:
- name (16 missing) → Replaced with "Unknown"
- host_name (21 missing) → Replaced with "Not Available"
- reviews_per_month (10,052 missing) → Replaced with median value
- last_review (10,052 missing) → Replaced with "No Review"
 
 **2. Checking for Duplicates:**
No duplicate rows were found in the dataset.


 **3. Outlier Detection & Removal**
To ensure data quality, outliers were identified and removed from highly skewed numerical columns (price, minimum_nights, number_of_reviews, reviews_per_month, calculated_host_listings_count).

## Outlier Detection Methods Tested:
**i. Z-score Method:**  Removed values beyond 3 standard deviations from the mean.

- Result: Some extreme outliers remained after capping.

**ii. Interquartile Range (IQR) Method:**

Result: Most effective method for this dataset.


**iii. Percentile Method (1st & 99th Percentile):** 

Replaced values outside this range.
- Result: Not as effective as IQR.


## Final Approach: 
The IQR method was chosen as the best approach for removing outliers. Capped outliers in all skewed columns. New dataset (df_capped) is ready for further analysis.

**Data Visualization** 
- Boxplots were used to inspect outliers before and after removal.
- Histograms showed distribution changes after data cleaning.

**Final Processed Data**

Final DataFrame (df_capped): Outliers have been handled using IQR.
Skewness was reduced, improving the dataset quality.

## Next Steps
Use the cleaned dataset (df_capped) for further EDA (Exploratory Data Analysis).
Develop predictive models for price analysis or Airbnb listing trends.
Explore geospatial analysis using location-based features.
How to Use This Repository
