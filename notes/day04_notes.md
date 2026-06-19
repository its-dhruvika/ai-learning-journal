# Day 04 — Pandas DataFrames and Exploratory Data Analysis

## What I Learned

Today I learned the fundamentals of Pandas, the primary library used for data manipulation and analysis in Python. I explored how to load, inspect, and analyze tabular data using DataFrames.

### Series vs DataFrame

* A **Series** is a one-dimensional labeled array.
* A **DataFrame** is a two-dimensional table consisting of rows and columns.

### Essential Pandas Functions

```python
import pandas as pd

df = pd.read_csv("city_day.csv")
```

* `head()` — View the first few rows
* `tail()` — View the last few rows
* `info()` — Inspect columns, data types, and missing values
* `describe()` — Generate summary statistics
* `shape` — Get the number of rows and columns
* `dtypes` — Check data types
* `value_counts()` — Count unique values
* `isnull().sum()` — Count missing values

### Key Insights

* Real-world datasets often contain missing values.
* Understanding data structure is the first step before model building.
* Exploratory Data Analysis (EDA) helps identify trends and anomalies.

## Dataset

Dataset used: **Air Quality Data in India (Kaggle)**

File explored:

```text
city_day.csv
```

## EDA Questions

### 1. Which city has the highest average AQI?

```python
df.groupby("City")["AQI"].mean().idxmax()
```

### 2. How many rows have missing PM2.5 values?

```python
df["PM2.5"].isnull().sum()
```

### 3. What is the AQI trend over years?

```python
df.groupby(df["Date"].dt.year)["AQI"].mean()
```

### 4. Which month has the worst air quality?

```python
df.groupby(df["Date"].dt.month)["AQI"].mean().idxmax()
```

### 5. How many cities are in the dataset?

```python
df["City"].nunique()
```

## Three Things That Confused Me

1. The difference between attributes and methods in Pandas.
2. When to use `groupby()`.
3. Handling missing values effectively.

## Three Things That Clicked

1. DataFrames behave like spreadsheets with programming capabilities.
2. Most analyses can be done using a few powerful Pandas functions.
3. EDA is about asking questions and answering them with data.

## Files Created

* `day04_pandas_aqi_eda.ipynb`
* `day04_notes.md`

## Resources

* Pandas 10 Minutes to Getting Started: https://pandas.pydata.org/docs/user_guide/10min.html
* Pandas Cheat Sheet: https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf
* Air Quality Data in India: https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india
