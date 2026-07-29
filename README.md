# Retail Store Sales — Exploratory Data Analysis 🛒

Exploratory data analysis of a retail store transactions dataset (~12,500 records, 2022–2025) using Python and pandas. The project covers data cleaning of deliberately "dirty" data, sales exploration, and customer profiling.

**Dataset:** [Retail Store Sales (Dirty)](https://www.kaggle.com/datasets/ahmedmohamed2003/retail-store-sales-dirty-for-data-cleaning)  
**Tools:** Python, pandas, matplotlib, seaborn (Google Colab)



---

## Project Structure

1. **Data Overview** — shape, dtypes, missing values, unique value counts, duplicate checks
2. **Data Cleaning** — arithmetic recovery of missing values, type conversion, handling nulls
3. **Univariate Analysis** — category distribution, descriptive statistics
4. **Bivariate Analysis** — revenue by category, payment method cross-tabs
5. **Customer Analysis** — top spenders, per-customer aggregates
6. **Time Series Analysis** — monthly revenue trend, month × category heatmap

---

## Key Steps & Highlights

### Data Cleaning — Recovering Instead of Dropping
`Price Per Unit`, `Quantity`, and `Total Spent` are linked by the rule  
**`Total Spent = Price Per Unit × Quantity`**.

Where one value was missing but the other two were present, the missing value was **calculated arithmetically** rather than dropped — recovering **609 rows** that would otherwise be lost. Rows missing both `Quantity` and `Total Spent` were dropped, as revenue cannot be reconstructed without them.

### Thoughtful Type Handling
`Discount Applied` was converted to a **nullable boolean** (`BooleanDtype`) instead of plain `bool`, to preserve missing values — which represent "unknown" rather than "no discount". This distinction matters for any discount-based analysis.

---

## Key Findings

- **Category distribution is nearly uniform** (~1,500 transactions each) — a clear signature of synthetic data. Real retail data is typically skewed toward a few dominant categories.
- **All 25 customers have a similar number of transactions** (440–520 range), again reflecting the synthetic nature of the dataset rather than real customer behavior.
- **No true duplicates** were found — each transaction is unique across all fields.
- The **month × category heatmap** shows no strong seasonality, consistent with a generated dataset.

---

## Skills Demonstrated

- Data cleaning & missing value recovery (`isna`, `notna`, `.loc` masking)
- `groupby` + named aggregation
- `pd.crosstab` for categorical relationships
- Descriptive statistics (`describe`, distributions)
- Data visualization (`matplotlib`, `seaborn` — bar charts, histograms, heatmaps)
- Working with datetime and `Period` types
- Nullable dtypes (`BooleanDtype`)

---

