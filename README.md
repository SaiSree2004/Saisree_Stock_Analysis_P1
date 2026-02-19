# Stock Analysis - P1 (Data Engineering Project)

## Project Overview

This project is an end-to-end ETL (Extract, Transform, Load) based stock data analysis project.
The main goal of this project is to take raw historical stock data, clean and transform it using business rules, store the processed data in a MySQL database, and perform analysis to understand stock performance and trends.

The datasets used in this project are:

* AAPL (Apple)
* GOOG (Google)
* MSFT (Microsoft)

All three datasets are combined into a single cleaned table for easier comparison and analysis.

---

## ETL Pipeline Flow

The project follows a structured ETL process:

Raw CSV Files (AAPL, GOOG, MSFT)
→ Data Extraction using Pandas
→ Data Cleaning and Transformation
→ Feature Engineering (daily_return, trend)
→ Load Clean Data into MySQL (stock_prices table)
→ SQL Validation and Data Visualization

This pipeline converts raw and unclean data into a structured and analysis-ready dataset.

---

## Data Transformation & Business Rules

During the transformation phase, the following steps were applied to maintain data quality:

### Missing Value Handling

* Missing close_price values were filled using the median close price of each stock
* Missing volume values were replaced with 0
* Missing high_price values were corrected using max(open_price, close_price)
* Missing low_price values were corrected using min(open_price, close_price)

### Data Quality Checks

* Ensured high_price is always greater than or equal to open_price and close_price
* Ensured low_price is always less than or equal to open_price and close_price
* Removed duplicate records during preprocessing

### Feature Engineering

* Calculated daily_return for each stock
* Created a trend column:

  * UP (positive return)
  * DOWN (negative return)
  * NO_CHANGE (zero return)

---

## Analysis & Insights

After cleaning and loading the data, the following analysis was performed:

* Identified the best performing stock based on average daily returns
* Measured stock volatility using standard deviation of returns
* Analyzed the relationship between trading volume and price movement
* Compared UP vs DOWN trend ratio for each company
* Detected abnormal volume spike days
* Visualized daily closing price trends for AAPL, GOOG, and MSFT

These insights help in understanding stock behavior and performance patterns.

---

## Project Structure

Saisree_Stock_Analysis_P1/

* Stock_Analysis_P1.ipynb  → Main notebook (ETL + Analysis + Visualization)
* aapl_stock_prices.csv    → Raw Apple dataset
* goog_stock_prices.csv    → Raw Google dataset
* msft_stock_prices.csv    → Raw Microsoft dataset
* README.md                → Project documentation

---

## Technologies Used

* Python (Pandas, NumPy, Matplotlib)
* MySQL
* SQLAlchemy
* Jupyter Notebook
* Git & GitHub

---

## What I Learned

Through this project, I learned how to build a complete ETL pipeline using Python and MySQL.
I gained practical experience in data cleaning, handling missing values, applying business rules, and transforming raw datasets into a structured format.

I also learned how to integrate Python with MySQL, validate data using SQL queries, and perform basic technical analysis such as trend classification, volatility analysis, and data visualization.

Overall, this project improved my understanding of data engineering concepts and real-world data preprocessing.
