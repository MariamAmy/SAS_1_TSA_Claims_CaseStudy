# TSA Claims Data Analysis

## Overview
This project performs data cleaning, preparation, and analysis on TSA claims data from 2002 to 2017. The goal is to provide insights into claim types, claim sites, dispositions, and close amounts for different states, as well as identify potential date issues. The analysis is exported as a PDF report, which includes visualizations and statistical summaries.

## Project Steps

### 1. **Importing Data**
The raw dataset, `TSAClaims2002_2017.csv`, is imported into SAS. The dataset contains information about TSA claims, including claim number, claim site, claim type, disposition, and close amount.

### 2. **Data Cleaning**
- **Duplicates**: Duplicate rows are removed.
- **Sorting**: The data is sorted by `Incident_Date`.
- **Missing or Invalid Values**: Columns such as `Claim_Site`, `Airport_Name`, `Airport_Code`, `Disposition`, and `Claim_Type` are cleaned to handle missing or invalid values.
- **State Formatting**: State values are converted to uppercase and state names are formatted to proper case.
- **Date Issues**: A new column `Date_Issues` is created to flag records with date inconsistencies (e.g., claims outside the 2002-2017 range or invalid dates).

### 3. **Data Transformation**
- Permanent labels and formats are added for better readability.
- The `County` and `City` columns are dropped.
  
### 4. **Frequency Analysis and Visualization**
- A frequency analysis is performed for columns such as `Claim_Site`, `Disposition`, `Claim_Type`, and `Date_Issues`.
- Claims are analyzed by `Incident_Date`, with visualizations for the distribution of claims over the years.

### 5. **State-Specific Analysis**
For each state (e.g., Texas and California), the following analyses are conducted:
- Frequency analysis of `Claim_Type`, `Claim_Site`, and `Disposition`.
- Descriptive statistics for `Close_Amount`, including mean, minimum, maximum, and sum.

### 6. **Exporting the Report**
The analysis results are exported to a PDF report using ODS. The report contains:
- Overview of date issues.
- Claims by year.
- State-specific analysis for selected states, including claim types, claim sites, disposition, and close amount statistics.

### 7. **Customization**
Users can dynamically input a state value by modifying the `SelectedState` and `SelectedState2` macro variables to analyze claims for specific states.

## Required Software
- SAS (Base, Advanced, and Visual Analytics)

## Files in the Project
- `TSAClaims2002_2017.csv`: Raw dataset of TSA claims.
- `ClaimsReport.pdf`: Generated PDF report containing the analysis and visualizations.
- SAS script for data cleaning, transformation, and analysis.

## How to Use
1. Import the dataset into your SAS environment.
2. Run the provided SAS code to clean and analyze the data.
3. Modify the `SelectedState` and `SelectedState2` macro variables to specify the states for analysis.
4. The output will be saved in a PDF file (`ClaimsReport.pdf`) that summarizes the results.

## Conclusion
This project helps in identifying trends, issues, and summaries related to TSA claims, which could be useful for further analysis or reporting.
