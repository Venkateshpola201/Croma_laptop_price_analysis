# Croma Laptop Price Analysis

Exploratory data analysis and interactive Power BI dashboard analyzing 284 laptop listings scraped from Croma.com, uncovering pricing patterns across brands, RAM/storage configurations, and processor types.

## Overview

Analyzed 284 Croma laptop listings to identify pricing patterns by brand, RAM/storage, and processor. Found that 16GB RAM is now the market standard (not a premium tier), AMD Ryzen configurations offer roughly ₹35K better average value than Intel equivalents, and identified the top "price-per-GB-RAM" laptops across brands and budgets. Built an interactive Power BI dashboard with a dedicated Value Finder page for budget-based laptop comparison.

## Key Findings

- **16GB RAM is the market standard** — roughly two-thirds of listings, not a premium differentiator anymore
- **AMD Ryzen is the value play** — Intel-equipped laptops average ~₹35K more, largely due to product-tier mix
- **Brand premium is uneven** — ASUS spans both budget (Vivobook) and ultra-premium (ROG Strix, up to ₹5L) segments
- **RAM and storage explain ~46% of price variance** (R² from a ~0.68 correlation) — brand and processor tier drive the rest
- **HP and budget ASUS models** offer the best price-per-GB-RAM value among 16GB+ configurations

## Tech Stack

- **Python** (pandas, NumPy, matplotlib, seaborn) — data cleaning and EDA
- **Power BI** (DAX, Power Query) — interactive dashboard
- **Jupyter Notebook** — analysis documentation

## Repository Structure

```
croma-laptop-price-analysis/
│
├── data/
│   ├── croma_laptops_raw.xls        # original scraped data
│   └── croma_laptops_clean.csv      # cleaned dataset
│
├── notebooks/
│   └── Croma_Laptop_EDA.ipynb       # full EDA with charts
│
├── dashboard/
│   ├── Croma_Laptop_Dashboard.pbix  # Power BI file
│   └── screenshots/                 # dashboard page exports (PNG)
│
├── docs/
│   └── PowerBI_Build_Guide.md       # dashboard build documentation
│
└── README.md
```

## Data Cleaning

The raw scraped data required standard real-world cleanup:
- Standardized inconsistent brand casing (`ASUS`/`Asus`/`asus` → `ASUS`)
- Parsed price from currency-formatted text (`"₹ 72,990.00"`) into numeric values
- Removed 20 duplicate listings and 1 blank row
- Handled missing values in Processor/Generation (common for Apple/Qualcomm chips) and SSD (median imputation)
- Engineered a `Processor_Brand` feature and a `Price_per_GB_RAM` value metric

## Dashboard

The Power BI dashboard has 4 pages:
1. **Overview** — market snapshot, KPIs, price-by-brand
2. **Brand Deep-Dive** — RAM/SSD vs price scatter, filterable by brand
3. **Value Finder** — best price-per-spec laptops by budget band
4. **Processor Analysis** — Intel vs AMD vs Apple Silicon price comparison

*(Add dashboard screenshots here once exported)*

## How to Reproduce

1. Clone this repo
2. Run `notebooks/Croma_Laptop_EDA.ipynb` to regenerate the cleaned dataset and charts
3. Open `dashboard/Croma_Laptop_Dashboard.pbix` in Power BI Desktop, refresh the data source path if needed

## Author

**Venkatesh Pola**
[LinkedIn](https://linkedin.com/in/venkateshpola) · [GitHub](https://github.com/Venkateshpola201) · [Portfolio](#)
