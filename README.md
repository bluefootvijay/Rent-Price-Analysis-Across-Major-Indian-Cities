# Rent Price Analysis - Major Indian Cities

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%20|%20Seaborn%20|%20Matplotlib-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Project Overview
The rental housing market in India is diverse, with significant price variations across different metropolitan cities. This project analyzes a dataset of nearly 5,000 rental listings to understand the key factors influencing rent prices.

By cleaning, processing, and visualizing the data, this analysis provides insights into how **location (City), property size, furnishing status, and tenant preference** impact the monthly rent.

---

## Table of Contents
- [Project Overview](#-project-overview)
- [Business Questions](#-business-questions)
- [Data Dictionary](#-data-dictionary)
- [Analysis Workflow](#-analysis-workflow)
- [Key Insights](#-key-insights)
- [Recommendations](#-recommendations)
- [Technologies Used](#-technologies-used)

---

## Business Questions
1.  **City-wise Disparity:** Which is the most expensive city to live in? How does it compare to the most affordable one?
2.  **Size Impact:** Does a larger area always guarantee a higher rent, or do location dynamics play a bigger role?
3.  **Furnishing Premium:** How much extra rent does a "Fully Furnished" apartment command compared to an "Unfurnished" one?
4.  **Tenant Preferences:** Do landlords price their properties differently for Bachelors vs. Families?

---

## Data Dictionary
The dataset (`House_Rent_Dataset.csv`) contains 4,700+ records with the following features:

* **Posted On:** Date the listing was posted.
* **BHK:** Number of Bedrooms, Hall, and Kitchen.
* **Rent:** Monthly rent in INR (Target Variable).
* **Size:** Size of the property in Square Feet.
* **Floor:** Detailed floor information (e.g., "Ground out of 2").
* **Area Type:** Super Area, Carpet Area, or Built Area.
* **City:** Location (Mumbai, Bangalore, Chennai, Delhi, Hyderabad, Kolkata).
* **Furnishing Status:** Furnished, Semi-Furnished, Unfurnished.
* **Tenant Preferred:** Bachelors, Family, or Both.
* **Bathroom:** Number of bathrooms.

---

## Analysis Workflow

### 1. Data Preprocessing & Feature Engineering
* **Floor Extraction:** Deconstructed the `Floor` column to extract numerical features: `Current Floor` and `Total Building Floors`. Handled non-numeric values (e.g., 'Ground' = 0, 'Basement' = -1).
* **Area Standardization:** Standardized the `Size` column by converting 'Carpet Area' and 'Built Area' into a uniform 'Super Area' metric for fair comparison.
* **Outlier Removal:** Applied the **IQR (Interquartile Range)** method to remove outliers in `Rent` and `Size` columns, ensuring extreme values (like luxury penthouses) didn't skew the general analysis.

### 2. Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Used histograms and boxplots to study the distribution of Rent, Size, and BHK across the dataset.
* **Bivariate Analysis:**
    * **FacetGrid Scatterplots:** Analyzed the `Rent` vs. `Size` correlation individually for each city.
    * **Boxplots:** Compared Rent distribution across Categorical variables like `Furnishing Status` and `Tenant Preferred`.

---

## Key Insights

### 1. City-wise Price Trends 🏙️
* **Mumbai** is the most expensive city with a median rent of ~₹35,000 and high variability. Even smaller apartments command high premiums here.
* **Kolkata** is the most affordable, with a median rent of ~₹8,000 and a very consistent price range.
* **Delhi's Anomaly:** Delhi shows a unique cluster of very small units (<350 sq ft) commanding incredibly high rents, likely due to micro-apartments in prime zones.

### 2. Impact of Furnishing 🛋️
* **The "Mumbai Premium":** In Mumbai, furnishing status significantly impacts rent (Median jumps from ₹32k for Unfurnished to ₹42k for Furnished).
* **Neutral Market:** In Kolkata, furnishing status has almost **no impact** on the median rent, suggesting tenants there prioritize basic affordability over amenities.

### 3. Tenant Preferences 👨‍👩‍👧‍👦
* **Family vs. Bachelor:** In Delhi and Mumbai, landlords often price "Family" preferred units higher. In other IT hubs like Bangalore and Hyderabad, the pricing is more uniform, reflecting a high demand from the migrant working population (bachelors).

### 4. Size & Configuration
* **Hyderabad** offers the most spacious homes (Median ~1,150 sq ft).
* **Delhi** offers the smallest homes (Median ~500 sq ft), yet rents remain competitive with Bangalore and Chennai, highlighting a high price-per-sq-ft.

---

## Recommendations

1.  **For Renters:**
    * **Budget Seekers:** Consider Kolkata or the outskirts of Hyderabad for the best space-to-price ratio.
    * **In Mumbai:** If you are on a budget, opt for "Unfurnished" or "Semi-Furnished" as the premium for "Furnished" is steep.

2.  **For Property Owners:**
    * **In Mumbai/Delhi:** Investing in furnishing your property yields a high return on investment (ROI) in terms of increased rent.
    * **In Kolkata:** Focus on keeping the base rent competitive rather than spending heavily on furnishing, as the market doesn't pay a premium for it.

3.  **Investment Strategy:**
    * **Hyderabad** appears to be a balanced market with larger homes and moderate rents, making it attractive for long-term residential investments.

---

## Technologies Used
* **Python** (Pandas, NumPy)
* **Data Visualization** (Seaborn, Matplotlib)
* **Data Cleaning** (String manipulation, Outlier detection)
