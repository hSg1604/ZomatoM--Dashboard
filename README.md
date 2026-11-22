# Zomato Restaurant & Food Item Analysis

## Project Overview

This project explores a Zomato restaurant and food-item dataset using Python. It is intended as a beginner-friendly data analysis project and can be extended with exploratory data analysis (EDA), visualizations, and business insights.

The Excel workbook (`zomatoHsg.xlsx`) contains four worksheets. The main analysis dataset is in the **`random_sample`** worksheet.

## Dataset at a Glance

- **Main worksheet:** `random_sample`
- **Rows:** 12,366
- **Useful columns:** 12
- **Restaurants:** 807 distinct restaurant names
- **Cities/locations recorded in the City column:** 17 distinct values
- **Place names:** 322 distinct values
- **Cuisine categories:** 48 distinct values
- **Item names:** 9,382 distinct values

The workbook also contains three other worksheets: `Detail1`, `Detail2`, and `Sheet2`. `Detail1` and `Detail2` contain smaller place-specific detail extracts, while `Sheet2` is titled as a dashboard worksheet.

> **Data note:** The main worksheet has five additional unnamed columns (`Unnamed: 12` to `Unnamed: 16`) that are empty in the inspected records. The 12 named columns are the useful fields for the analysis described here.

## Dataset Columns

| Column | Description |
|---|---|
| `Restaurant Name` | Name of the restaurant |
| `Dining Rating` | Customer rating for dining |
| `Delivery Rating` | Customer rating for delivery |
| `Dining Votes` | Number of dining votes |
| `Delivery Votes` | Number of delivery votes |
| `Cuisine ` | Cuisine/category associated with the food item (the source column name includes a trailing space) |
| `Place Name` | Locality or place name |
| `City` | City/location value recorded in the dataset |
| `Item Name` | Name of the food item |
| `Best Seller` | Item label or tag, such as `BESTSELLER`, `MUST TRY`, or `CHEF'S SPECIAL` |
| `Votes` | Votes recorded for the food item |
| `Prices` | Listed item price |

## Tools and Technologies

- **Python** – analysis and data processing
- **Pandas** – loading, cleaning, and summarizing the dataset
- **Matplotlib / Seaborn** – data visualization
- **Jupyter Notebook** – interactive analysis (if you create or include a notebook)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY-NAME.git
cd YOUR-REPOSITORY-NAME
```

Replace the URL and folder name with your GitHub repository details.

### 2. Install the required libraries

```bash
pip install pandas openpyxl matplotlib seaborn jupyter
```

### 3. Keep the Excel file in the project folder

Place `zomatoHsg.xlsx` in the repository's data folder, or update the file path in your notebook.

### 4. Load the main worksheet

```python
import pandas as pd

df = pd.read_excel("data/zomatoHsg.xlsx", sheet_name="random_sample")

# Remove unused unnamed columns, if present
df = df.loc[:, ~df.columns.astype(str).str.startswith("Unnamed:")]

# Optional: remove the trailing space from the Cuisine column name
df = df.rename(columns={"Cuisine ": "Cuisine"})

print(df.head())
print(df.info())
```

If the Excel file is stored in the repository root instead of a `data` folder, use `pd.read_excel("zomatoHsg.xlsx", sheet_name="random_sample")`.

## Suggested Analysis

The dataset can support the following beginner-level analysis questions:

1. **Restaurant analysis** – Which restaurants have the highest dining and delivery ratings?
2. **Cuisine analysis** – Which cuisine categories appear most frequently?
3. **Location analysis** – Which cities and localities have the most listed records?
4. **Price analysis** – What is the distribution of food-item prices? Which items are relatively expensive or affordable?
5. **Food-item analysis** – Which food items receive the most votes?
6. **Best-seller analysis** – What are the most common item labels?
7. **Rating comparison** – How do dining ratings compare with delivery ratings?
8. **Engagement analysis** – How do dining votes, delivery votes, and item votes vary?

### Recommended Charts

| Analysis | Suggested chart |
|---|---|
| Most common cuisines | Bar chart |
| Restaurants with highest ratings | Sorted horizontal bar chart |
| Number of records by city | Bar chart |
| Food-item price distribution | Histogram or box plot |
| Most-voted food items | Sorted horizontal bar chart |
| Best-seller labels | Count plot or bar chart |
| Dining vs. delivery ratings | Box plot or side-by-side bar chart |
| Price comparison across cuisines | Box plot |
| Relationship between price and votes | Scatter plot |
| Correlation among numeric fields | Correlation heatmap |

## Data Quality Notes

A quick inspection of the `random_sample` worksheet found:

- `Dining Rating` has **3,190** missing values.
- `Delivery Rating` has **136** missing values.
- `Best Seller` has **9,537** missing values. These blanks may mean that no label was recorded; check the source meaning before replacing them.
- There are **254 exact duplicate rows** across the 12 named columns. Review duplicates before removing them, because repeated records may or may not be valid.
- The source column `Cuisine ` has a trailing space in its name. The example code above renames it to `Cuisine`.

Do not automatically replace missing ratings with zero: a missing rating is not the same as a zero rating. Decide how to handle missing values based on the analysis question.

## Suggested Repository Structure

```text
zomato-analysis/
│
├── data/
│   └── zomatoHsg.xlsx
│
├── notebooks/
│   └── zomato_analysis.ipynb
│
├── images/
│   └──                 # Save exported charts here
│
├── README.md
└── requirements.txt
```

A `requirements.txt` file can contain:

```text
pandas
openpyxl
matplotlib
seaborn
jupyter
```

## Project Status

This README describes the workbook structure and possible analysis directions. Add your completed notebook, charts, and findings to the repository as you work through the analysis.

## Future Improvements

- Perform data cleaning and document each cleaning decision.
- Explore ratings, prices, votes, cuisines, and locations.
- Create clear charts with titles and labels.
- Build a summary dashboard.
- Add key findings and business recommendations after completing the analysis.

## Dataset Source

The dataset used in this project is the Excel workbook `zomatoHsg.xlsx` included with the repository. Add the original source or attribution here if the dataset was obtained from an external website or provider.
# ZomatoM--Dashboard
