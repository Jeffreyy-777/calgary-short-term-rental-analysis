# Short-Term Rental Licence Analysis – Calgary

A data analysis notebook exploring short-term rental licensing trends in Calgary using open municipal data.

> **Note:** The City of Calgary updates this dataset daily. This analysis was originally based on a snapshot taken on **June 23, 2026**. If you download a more recent version, the numbers will differ — but the notebook is written to adapt automatically (see below).

## Dataset

**Source:** [City of Calgary Open Data – Short Term Rentals](https://data.calgary.ca/)  
**File:** `data/Short_Term_Rentals.csv`

The dataset includes short-term rental licence records with the following fields:

| Column | Description |
|---|---|
| Business Licence Number | Unique licence identifier |
| Business ID | Business registration ID |
| Address | Property address |
| Business Licence Type | Primary vs. non-primary residence |
| Type of Residence | Property type (apartment, house, etc.) |
| Licenced Date | Date the licence was issued |
| Licenced Expiry Date | Date the licence expires |
| Status Description | Current status (Licensed, Expired, Closed, etc.) |
| latitude / longitude | Geographic coordinates |

## Setup

1. Clone this repository
2. Download the latest dataset from the City of Calgary Open Data portal and save it as:
   ```
   data/Short_Term_Rentals.csv
   ```
3. Install dependencies:
   ```bash
   pip install pandas matplotlib
   ```
4. Open and run `Short_Term_Rentals_Analysis.ipynb`

## What the Notebook Covers

### Reusable Functions

The notebook defines a set of helper functions for cleaning and querying the dataset:

| Function | Description |
|---|---|
| `clean_dates(df)` | Converts date columns to datetime format |
| `add_year_column(df)` | Extracts the licence year for filtering |
| `filter_by_year(df, year)` | Filters records by licence year |
| `filter_by_status(df, status)` | Filters by licence status |
| `count_by_column(df, column)` | Counts value frequencies in any column |
| `plot_bar(df, column, title)` | Generates a horizontal bar chart |
| `show_kpis(df)` | Prints key summary statistics |

### Questions Answered

| # | Question |
|---|---|
| 1 | How many licences were issued in the two most recent years? |
| 2 | How many licences are Active vs. Expired vs. Closed? |
| 3 | Which type of residence is most commonly used for short-term rentals? |
| 4 | Are there more primary-residence or non-primary-residence rentals? |
| 5 | What percentage of rentals have expired without renewal? |

### Works with Any Date's Data

The notebook automatically detects the two most recent years present in the dataset, so Q1, the KPI examples, and year-based filters will always reflect the current data — no manual updates needed when you refresh the CSV.

## Key Findings (Snapshot: June 23, 2026)

- **4,076 total listings** across all years
- **88.1% are currently active** (Licensed)
- **Legally registered suites** are the most common residence type
- **Non-primary residences** slightly outnumber primary residences (52.8% vs. 47.2%)
- **5.6%** of licences have expired without renewal

## Tech Stack

- Python 3
- pandas
- matplotlib
- Jupyter Notebook
