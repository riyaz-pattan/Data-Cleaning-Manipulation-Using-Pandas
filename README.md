# Data Cleaning and Manipulation

## Overview
This repository contains a Jupyter Notebook (`Data_Cleaning&Manipuation.ipynb`) that showcases practical techniques and functions in Python using pandas for data cleaning and manipulation. It is an essential guide for data preprocessing, preparing datasets for analysis, and building machine learning pipelines.

---

## Features
- **Handling Missing Data**: Strategies to manage missing values (filling, dropping, imputing).
- **String Manipulation**: Extracting, splitting, and transforming string data.
- **Column Operations**: Adding, modifying, or calculating new columns.
---


## Key Topics Covered

### Handling Missing Data
- Fill missing values:
  ```python
  df['Column'] = df['Column'].fillna(df['Column'].mean())
  ```
- Drop rows with missing values:
  ```python
  df = df.dropna(subset=['Column'])
  ```

### String Manipulation
- Remove unwanted characters:
  ```python
  df['Salary'] = df['Salary'].str.replace('$', '').str.replace('k', '').astype(float) * 1000
  ```
- Split strings into multiple columns:
  ```python
  df[['First_Name', 'Last_Name']] = df['Full_Name'].str.split(' ', 1, expand=True)
  ```
  ---
  ## Type Conversion:
  - Changing data type
    ```python
    df['l_Salary']=df['l_Salary'].str.replace('k','')
    df['h_Salary']=df['h_Salary'].str.replace('k','')
    df['l_Salary']=df['l_Salary'].astype(int)
    df['h_Salary']=df['h_Salary'].astype(int)
    df['h_Salary'].info()
    ```
  ---

### Column Operations
- Calculate average salary:
  ```python
  df['Avg_Salary'] = (df['l_Salary'] + df['h_Salary']) / 2
  ```
- Create a column based on conditions:
  ```python
  df['Easy Apply'] = df['Easy Apply'].apply(lambda x: 'TRUE' if x == 'TRUE' else 'FALSE')
  ```
---

## Contributing
Contributions are welcome! Feel free to fork this repository, make improvements, and submit a pull request. For major changes, please open an issue first to discuss your ideas.

---


## Acknowledgments
- [pandas Documentation](https://pandas.pydata.org/docs/)


