# Sell4All — Data Exploration with Python

This project was created as part of the **Artificial Intelligence Development** program at YouCode. The goal was to get comfortable with data exploration and cleaning using Python, before moving on to building actual recommendation features.

## What's this about?

Sell4All is an online second-hand clothing store that's been running for about six months. They want to add AI-powered product recommendations for their users, based on things like country, age, gender, spending habits, and purchase history.

But before jumping into that, we needed to properly understand and clean up the customer data they had. So that's what this project focuses on — exploring the dataset (`dataset-sell4all.csv`) using Pandas and Matplotlib in a Jupyter notebook.

## How I approached it

### Day 1 — August 14, 2026
- Set up the environment with Miniconda, Jupyter, Pandas, and Matplotlib
- Loaded the CSV file into a Pandas DataFrame
- Checked out the first few rows (`df.head()`) to get a feel for the data
- Ran `df.info()` to understand the structure, data types, and missing values

### Day 2 — August 15, 2026
- Calculated mean and median for `Age` and `Customer spendings`
- Took a stab at the bonus: median age per country using `groupby`
- Made a bar chart to show total spending per country (Matplotlib)
- Cleaned things up: removed rows where spending was under €10, then dropped duplicates
- Saved the cleaned data into a new CSV (`dataset-sell4all-clean.csv`), keeping only the columns that seemed relevant: `Country`, `Age`, `Gender`, `Customer spendings`

### Day 3 — August 16, 2026
- Tweaked a few things and made sure the Python version was correctly noted
- Wrote up this README and got everything onto GitHub

## What's included

- [x] Reading the CSV with Pandas
- [x] Showing the first 5 rows
- [x] Explaining the dataset structure (rows, columns, data types) in plain Markdown
- [x] Mean and median for `Age` and `Customer spendings`
- [x] Bonus: median age broken down by country
- [x] Bar chart for total spendings by country
- [x] Cleaning: filtering out spendings under €10 and removing duplicates
- [x] Exporting the cleaned CSV with selected columns

## A few bumps along the way

- **Unnecessary columns** — The original dataset had personal info like `Name`, `Email`, `Phone Number`, and `Address`. I didn't want to mess with the raw data, so I kept them in the original file but excluded them from the cleaned version I exported.
- **Aggregation for the chart** — I went with total spending per country (`groupby('Country').sum()`) instead of average, since it felt more useful to see the overall economic weight of each country, even if customer counts varied.
- **Cleaning order** — I filtered out low spenders first, then removed duplicates. Seemed more logical to get rid of irrelevant rows before dealing with redundancy.

## How to run this thing

### What you'll need

- [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Python 3.x
- Jupyter Notebook
- `pandas`, `matplotlib`

### Setting it up

```bash
conda create -n sell4all python=3.13
conda activate sell4all
pip install pandas matplotlib jupyter
