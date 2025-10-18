# SQL Exploratory Data Analysis (EDA): Global Layoffs

## Project Overview
This project performs an **Exploratory Data Analysis (EDA)** on the cleaned Global Layoffs data, identifying trends, patterns, and key insights related to company closures and workforce reductions across different industries and time periods. The goal is to provide a complete picture of the market conditions during this timeframe.

## Dataset
* **Source:** Layoffs Data (Cleaned in the prior `SQL-Data-Cleaning-Layoffs` project).
* **Data in Repository:** `MySQL Exploratory Data Analysis project.sql`

## Key Analysis Performed
The analysis in the attached SQL script is divided into three sections: Simple Queries, Aggregation Queries, and Advanced Ranking/Window Queries.

### 1. Simple Descriptive Analysis
* **Maximum Impact:** Identified the largest single layoffs and the companies that laid off **100%** of their staff.
* **Funding Context:** Filtered the 100% layoff companies by `funds_raised_millions` to see which highly-funded companies failed.
* **Temporal Scope:** Determined the minimum and maximum dates in the dataset to confirm the time frame covered.

### 2. Aggregation Analysis (GROUP BY)
* **Top Companies:** Ranked companies by the **total number of employees laid off** over the entire period.
* **Industry Impact:** Aggregated the total layoffs by `industry` to see which sectors were hit hardest (e.g., Retail, Consumer, Finance).
* **Location Analysis:** Grouped data by `country` and `stage` (e.g., Post-IPO, Startup) to understand where and when layoffs were concentrated.

### 3. Advanced Time-Series Analysis
* **Yearly Top Performers:** Used **Window Functions (`DENSE_RANK()`, `PARTITION BY`)** to identify the **Top 3** companies with the most layoffs **for each individual year** (2020, 2021, 2022, 2023).
* **Rolling Total of Layoffs:** Created a **Common Table Expression (CTE)** and used a `SUM` Window Function to calculate the **month-over-month cumulative total** of all layoffs, visualizing the market slowdown over time.

## Tech Stack
* **SQL (MySQL dialect):** Primary tool for querying and analysis.
* **Key Functions Used:** `GROUP BY`, `ORDER BY`, `MAX()`, `MIN()`, `SUM()`, `YEAR()`, `SUBSTRING()`, `DENSE_RANK()`, `PARTITION BY`, `Common Table Expressions (CTEs)`.

