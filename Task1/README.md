**1. What are missing values and how do you handle them?**
<br>
Missing values are entries in a dataset that have no data or are null (NaN in Pandas). These can occur due to data entry errors, lack of information, or merging data from multiple sources.

Handling methods:

dropna() – removes rows or columns with missing values.

fillna() – fills missing values with a constant, mean, median, or mode.

Forward/Backward Fill (ffill, bfill).

Domain-specific logic (e.g., replacing with "Unknown").

**2. How do you treat duplicate records?**
<br>
Duplicates can skew data analysis. You can remove them using:

python
Copy code
df.drop_duplicates(inplace=True)
*Always verify:*

Which columns cause duplication

Whether it's safe to drop the duplicates

**3. Difference between dropna() and fillna() in Pandas?**
<br>
Function	Description
dropna()	Removes all rows/columns with null values.
fillna()	Fills missing values with a specified value (mean, median, etc.).

**4. What is outlier treatment and why is it important?**
<br>
Outliers are data points that differ significantly from other observations. They can distort model training and statistics.

Treatment techniques:

IQR Method

Z-Score Method

Capping (e.g., replace outliers with 95th percentile)

Why important?
To ensure accurate, unbiased results in data analysis and machine learning.

**5. Explain the process of standardizing data.**
<br>
Standardization means ensuring consistency across the dataset.

Examples:

Text casing ("India" vs "india" → "India")

Date formats (all in dd-mm-yyyy)

Column names (e.g., lowercase, no spaces)

Units ("min" vs "minutes")

Why?
Improves readability, avoids errors, and helps in grouping/aggregation.

**6. How do you handle inconsistent data formats (e.g., date/time)?**
<br>
Use Pandas' date parser:

python
Copy code
df['date'] = pd.to_datetime(df['date'], errors='coerce')
Set consistent format:

python
Copy code
df['date'] = df['date'].dt.strftime('%d-%m-%Y')

**7. What are common data cleaning challenges?**
<br>
Inconsistent data formats

Missing values

Duplicate records

Typos and noise

Mixed data types

Unstructured columns (e.g., address in one field)

Encoding issues (utf-8, latin1)

**8. How can you check data quality?**
<br>
.isnull().sum() – to find missing data

.duplicated().sum() – to find duplicates

.info() – to check data types

.describe() – for summary stats

Value counts for categorical variables