#  IPL Matches — Pandas Data Analysis

## Project Overview

This project demonstrates practical data analysis using the **Pandas** library in Python. The dataset used is `matches.csv`, which contains detailed records of **Indian Premier League (IPL)** cricket matches played from **2008 to 2017**.

The notebook (`pandas_data_analysis_annotated.ipynb`) walks through the dataset step by step, with every code cell accompanied by a clear, plain-English explanation of what is happening, why the technique is important in real-world data analysis, and what it reveals about the IPL data.

---

##  Dataset: IPL Matches (`matches.csv`)

The **Indian Premier League (IPL)** is one of the most popular Twenty20 (T20) cricket tournaments in the world, featuring franchise teams from major Indian cities. The dataset covers **636 matches** across **10 seasons** (2008–2017), with the following **18 columns**:

| Column | Description |
|--------|-------------|
| `id` | Unique match identifier |
| `season` | IPL season year (2008–2017) |
| `city` | City where the match was played |
| `date` | Date of the match |
| `team1` / `team2` | The two competing teams |
| `toss_winner` | Team that won the coin toss |
| `toss_decision` | Toss decision: bat or field |
| `result` | Match result type (normal, tie, etc.) |
| `dl_applied` | Whether Duckworth-Lewis rule was applied |
| `winner` | Winning team |
| `win_by_runs` | Margin of victory in runs (0 if wickets) |
| `win_by_wickets` | Margin of victory in wickets (0 if runs) |
| `player_of_match` | Best performer of the match |
| `venue` | Stadium name |
| `umpire1` / `umpire2` / `umpire3` | Match officials |

**Teams covered:** 14 franchises including Mumbai Indians, Chennai Super Kings, Kolkata Knight Riders, Royal Challengers Bangalore, Rajasthan Royals, and more.

---

##  Pandas Concepts Demonstrated

This notebook covers the following core Pandas skills, progressing from the basics to more advanced operations:

### 1. Data Loading and Import
- `import pandas as pd` — setting up the Pandas environment
- `pd.read_csv()` — loading a CSV file into a DataFrame

### 2. Data Inspection
- `data` / `data.head()` / `data.tail()` — viewing the dataset
- `data.shape` — checking the dimensions (rows × columns)
- `data.info()` — understanding column types and missing value counts
- `data.describe()` — statistical summary of numeric columns

### 3. Column Selection
- `data['column']` — selecting a single column (returns a Series)
- `data[['col1', 'col2']]` — selecting multiple columns (returns a DataFrame)

### 4. Row Selection and Indexing
- `data.iloc[n]` — accessing a row by integer position
- `data.iloc[:, [4,5,10]]` — selecting specific columns by position

### 5. Filtering (Boolean Masking)
- Single condition: `data[data['city'] == 'Hyderabad']`
- Multiple conditions with `&` (AND): combining two masks

### 6. Series Operations
- `value_counts()` — counting frequency of each unique value
- `.index` and `.values` — accessing labels and raw data
- Label-based access: `series['Kings XI Punjab']`

### 7. Sorting
- `sort_values()` on a Series — ascending and descending
- `sort_values()` on a DataFrame — single column, multiple columns
- Mixed sort directions with `ascending=[True, False]`

### 8. Removing Duplicates
- `drop_duplicates(subset=['city'])` — unique rows per column
- `drop_duplicates(keep='last')` — extracting season champions

### 9. Grouping and Aggregation
- `groupby('city').size()` — match count per city
- `groupby('city')['winner'].count()` — non-null count per group

### 10. Index Management
- `set_index('city', inplace=True)` — setting a custom index
- `reset_index()` — reverting to default integer index
- `rename(columns={...})` — renaming columns

### 11. Handling Missing Values
- `dropna(how='all')` — dropping fully empty rows
- `dropna(how='any')` — dropping rows with any NaN
- `dropna(axis=1)` — dropping columns with missing values
- `dropna(subset=['column'])` — targeted missing value removal
- `fillna(value)` — replacing NaN with a specified value

---

##  Key Learnings

By working through this notebook, you will gain:

1. **Confidence with the Pandas workflow** — from loading raw data to cleaning and summarizing it, you will see the complete first-pass exploration a data analyst performs on any new dataset.

2. **Understanding of boolean filtering** — one of the most powerful and frequently used skills in data analysis, letting you ask specific questions like "how many matches were played in Hyderabad after 2010?"

3. **Practical experience with groupby aggregation** — the equivalent of SQL's `GROUP BY`, essential for any kind of reporting, ranking, or comparative analysis.

4. **A solid grasp of missing value handling** — understanding how `dropna()` and `fillna()` work with the `how`, `axis`, and `subset` parameters gives you fine-grained control over data quality.

5. **Appreciation for IPL's most successful teams** — the data reveals that Mumbai Indians (92 wins), Chennai Super Kings (79), and Kolkata Knight Riders (77) are the most dominant franchises in this period, and that Mumbai hosted the most matches (85).

6. **Reusable analytical patterns** — techniques like `drop_duplicates(keep='last')` to find season winners, or wrapping filter logic in a function, are patterns you can apply immediately in your own projects.

---

##  How to Run

1. Clone this repository or download the files.
2. Ensure you have Python and Pandas installed:
   ```bash
   pip install pandas jupyter
   ```
3. Place `matches.csv` in the same directory as the notebook.
4. Open the notebook:
   ```bash
   jupyter notebook pandas_data_analysis_annotated.ipynb
   ```
5. Run cells from top to bottom.

---

##  Repository Structure

Machine-Learning/Other-Techniques/
Pandas/
├── matches.csv                          # IPL dataset
├── pandas_data_analysiss.ipynb # data_analysis notebook
└── README.md                            # This file
```

---

##  Requirements

- Python 3.7+
- pandas >= 1.0
- Jupyter Notebook or JupyterLab (or Google Colab)

---

*Dataset covers IPL seasons 2008–2017. Original analysis performed in Google Colab.*
