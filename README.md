# Task 1: Data Cleaning and Preprocessing
## Elevate Labs Data Analyst Internship

### Objective
Clean and prepare a raw dataset with missing values, outliers, and inconsistent formats.

### Dataset
**Customer Personality Analysis** from Kaggle  
Raw shape: 2240 rows × 29 columns

### Tools Used
- Python (Pandas, NumPy)
- Jupyter Notebook (VS Code)

### Issues Found & Fixed

| Issue | Action Taken |
|-------|-------------|
| 24 missing values in `Income` | Filled with median value |
| `Dt_Customer` stored as string | Converted to datetime64 |
| `Marital_Status` had 'Alone', 'Absurd', 'YOLO' | Mapped to 'Single' / 'Other' |
| Column names in mixed case | Lowercased all column names |
| `Z_CostContact` & `Z_Revenue` were constant columns | Dropped (no analytical value) |
| `Year_Birth` = 1893 (130+ yr old customer) | Removed as outlier |
| `Income` = 666,666 (data entry error) | Removed as outlier |

### New Features Added
- `age` → derived from `year_birth`
- `total_spending` → sum of all product spending columns

### Summary
| | Before | After |
|--|--------|-------|
| Rows | 2240 | 2236 |
| Columns | 29 | 29 |
| Missing Values | 24 | 0 |
| Outliers | 4 | 0 |

### Files
- `task1_data_cleaning.ipynb` — Full cleaning notebook
- `marketing_campaign.csv` — Raw dataset
- `customer_personality_cleaned.csv` — Cleaned dataset
