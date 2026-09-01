# Data Cleaning and Preprocessing – Retail Store Sales Dataset

## Overview
This repository contains my submission for **Task 1: Data Cleaning and Preprocessing** as part of the Data Analyst Internship at DataX Labs.  
The objective is to clean and prepare a raw retail sales dataset for further analysis. All cleaning steps are implemented in a Jupyter Notebook using Python and Pandas.

## Dataset
- **File:** `retail_store_sales.csv`  
- **Rows:** 12,575  
- **Columns:** 11  
  - `Transaction ID` (object)  
  - `Customer ID` (object)  
  - `Category` (object)  
  - `Item` (object)  
  - `Price Per Unit` (float)  
  - `Quantity` (float)  
  - `Total Spent` (float)  
  - `Payment Method` (object)  
  - `Location` (object)  
  - `Transaction Date` (object)  
  - `Discount Applied` (object)  

### Initial Issues Detected
- Missing values in `Item`, `Price Per Unit`, `Quantity`, `Total Spent`, and `Discount Applied`.
- Inconsistent text formatting (e.g., `In-store` vs `In-Store`, `Digital Wallet` vs `digital wallet`).
- Incorrect data types (date as string, discount as string, quantity as float).
- No full duplicate rows were found.


## Cleaning Steps Performed

| Step | Description |
|------|-------------|
| **1. Data Exploration** | Checked shape, data types, missing values (count & percentage), and duplicates. |
| **2. Column Renaming** | Converted column names to lowercase with underscores (e.g., `Transaction ID` → `transaction_id`) for consistency. |
| **3. Date Conversion** | Converted `transaction_date` to `datetime64[ns]` for proper date handling. |
| **4. Missing Value Handling** | • `discount_applied`: filled with `False` and cast to boolean. <br> • `item`: filled with `"Unknown"`. <br> • `total_spent`: recalculated using `price_per_unit * quantity` where possible (via a boolean mask). <br> • Dropped remaining rows with missing `price_per_unit`, `quantity`, or `total_spent` (critical numeric fields). |
| **5. Data Type Fixes** | • `quantity` converted to integer. <br> • `discount_applied` converted to boolean. |
| **6. Text Standardization** | Stripped whitespace and applied title case to `category`, `payment_method`, and `location` for uniformity. |
| **7. Final Validation** | Confirmed no missing values remain and all columns have appropriate data types. |


## Technologies Used
- **Python 3**
- **Pandas**
- **Jupyter Notebook**


## How to Reproduce

1. Clone this repository.
2. Place the raw dataset (`retail_store_sales.csv`) in the same directory as the notebook.
3. Open `task1_Data Cleaning and Preprocessing(1).ipynb` in Jupyter Notebook or JupyterLab.
4. Run all cells sequentially.
5. The cleaned dataset will be saved as `retail_store_sales_cleaned.csv`.


## Output
- **Cleaned dataset:** `retail_store_sales_cleaned.csv`  
- **Final shape:** 11,362 rows × 11 columns  
- All missing values handled, data types corrected, text standardized, and duplicates removed.


## Summary of Changes

| Issue                          | Action Taken |
|--------------------------------|--------------|
| Missing `discount_applied`     | Filled with `False` and cast to boolean. |
| Missing `item`                 | Filled with `"Unknown"`. |
| Missing `total_spent`          | Recalculated from `price_per_unit * quantity` where possible. |
| Remaining missing numeric      | Dropped rows (critical for analysis). |
| Inconsistent column names      | Renamed to lowercase with underscores. |
| Incorrect date type            | Converted to `datetime64[ns]`. |
| Incorrect quantity type        | Converted `float` to `int`. |
| Inconsistent text formatting   | Stripped whitespace and applied `title()` to categorical columns. |
| Duplicate rows                 | No duplicates found; `drop_duplicates()` applied as safeguard. |


## Author
**Towsifa Towa**  
Data Analyst Intern at DataX Labs


## License
This project is for educational purposes only.
