# Task 1: Data Cleaning and Preprocessing

### Project Overview
This project is part of a **Data Analyst Internship**.  
The goal of this task is to clean and preprocess a raw retail sales dataset that contains missing values, inconsistent formats, and other data quality issues.

### Dataset
- **Name**: Retail Store Sales
- **Source**: Provided dataset (`retail_store_sales.csv`)
- **Original Shape**: 12,575 rows × 11 columns

### Tools Used
- Python
- Pandas

### Steps Performed

1. **Loaded the dataset**
2. **Explored the data** (shape, data types)
3. **Checked missing values**
4. **Checked and removed duplicate rows**
5. **Renamed column headers** to lowercase + snake_case
6. **Converted** `transaction_date` to datetime format
7. **Handled missing values**:
   - Filled `discount_applied` with `False`
   - Filled `item` with `"Unknown"`
   - Recalculated missing `total_spent` values
   - Dropped rows with remaining missing critical values
8. **Fixed data types** (`quantity` → integer)
9. **Standardized text values** (Title Case)
10. **Saved the cleaned dataset**

### Cleaning Summary

| Issue                        | Action Taken                          | Result          |
|-----------------------------|---------------------------------------|-----------------|
| Missing Values              | Filled / Recalculated / Dropped       | 0 missing       |
| Duplicate Rows              | Checked                               | 0 duplicates    |
| Column Names                | Converted to snake_case               | Clean names     |
| Date Format                 | Converted to datetime                 | Fixed           |
| Data Types                  | Quantity converted to int             | Corrected       |
| Text Inconsistency         | Standardized using Title Case         | Cleaned         |

### Final Cleaned Dataset
- **File**: `retail_store_sales_cleaned.csv`
- **Shape**: 11,362 rows × 11 columns
- **Missing Values**: 0

### How to Run
1. Open the Jupyter Notebook: `task1_Data Cleaning and Preprocessing.ipynb`
2. Make sure the original CSV file is in the same folder or update the path
3. Run all cells

### Files Included
- `task1_Data Cleaning and Preprocessing.ipynb` → Main cleaning notebook
- `retail_store_sales.csv` → Original raw dataset
- `retail_store_sales_cleaned.csv` → Cleaned dataset
- `README.md` → This file

### Author : Towsifa Towa
Data Analyst Intern
