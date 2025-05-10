# Data Cleaning with SQL

This project focuses on cleaning a dataset of company layoffs for further analysis. The work was done entirely in SQL using a step-by-step process to address common data quality issues.

---

## Dataset Overview

The original dataset, stored in a table named `layoffs`, contains company layoff data including fields like company name, industry, number of employees laid off, funding details, and more.

---

## Cleaning Steps

### 1. Remove Duplicates
- Duplicates were identified using `ROW_NUMBER()` over relevant columns.

### 2. Standardize Data
- Whitespace removed using `TRIM()`.
- Inconsistent values standardized (e.g., `Crypto Currency` → `Crypto`).
- Country names unified (e.g., removing trailing periods).
- Dates converted to proper `DATE` format using `STR_TO_DATE()`.

### 3. Handle Null and Blank Values
- Blank fields were converted to `NULL`.
- Missing industries were filled by joining on rows from the same company/location.
- Unfillable rows were identified and reviewed manually.

### 4. Remove Unnecessary Data
- Rows with both `total_laid_off` and `percentage_laid_off` as `NULL` were deleted.
- Temporary columns like `row_num` used for deduplication were dropped.

---

## Acknowledgments

This project was completed by following a [YouTube tutorial by Alex the Analyst]([https://www.youtube.com/watch?v=2lYZc2jJt2A](https://www.youtube.com/watch?v=OT1RErkfLNQ&t=10860s&ab_channel=AlexTheAnalyst)).
