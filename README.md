# Stock Analysis - P1 (Data Engineering Project)

## Project Overview
This project is focused on analyzing historical stock market data using an end-to-end ETL (Extract, Transform, Load) process. The main aim of the project is to clean raw stock datasets, apply defined business rules, store the processed data in a MySQL database, and perform technical analysis using visualizations and statistical methods.  
The datasets used in this project include stock data of AAPL, GOOG, and MSFT, which are combined into a single cleaned table for better analysis and comparison of stock performance and trends.

---

## Business Rules Implemented
During the transformation phase, the following business rules were applied to ensure data quality and consistency:

1. Missing Value Treatment:
   - Missing close_price values were replaced with the median close price for each stock.
   - Missing volume values were replaced with 0.
   - Missing high_price values were corrected using max(open_price, close_price).
   - Missing low_price values were corrected using min(open_price, close_price).

2. Price Sanity Checks:
   - Ensured that high_price is always greater than or equal to open_price and close_price.
   - Ensured that low_price is always less than or equal to open_price and close_price.
   - Any incorrect values were automatically adjusted during preprocessing.

3. Trend Classification:
   - daily_return > 0 → UP
   - daily_return < 0 → DOWN
   - daily_return = 0 → NO_CHANGE

---

## ETL Pipeline Flow
The project follows a structured ETL pipeline to process the stock data:

Raw CSV Files (AAPL, GOOG, MSFT)  
        ↓  
Data Extraction using Pandas  
        ↓  
Data Transformation:
- Handling missing values  
- Removing duplicate records  
- Applying business rules  
- Feature engineering (daily_return, trend)  
        ↓  
Loading Clean Data into MySQL (stock_prices table)  
        ↓  
SQL Validation and Data Visualization using Matplotlib  

This pipeline converts raw and unclean data into a structured and analysis-ready dataset.

---

## Business Insights Generated
After performing the analysis on the cleaned dataset, the following insights were obtained:
- Best performing stock based on average daily returns
- Identification of highest volatility stock using standard deviation of returns
- Relationship between trading volume and price movement
- UP vs DOWN trend ratio for each company
- Detection of abnormal volume spike days
- Visualization of daily closing price trends for each stock (AAPL, GOOG, MSFT)

These insights help in understanding stock behavior, performance patterns, and market trends.

---

## Project Structure
Saisree_Stock_Analysis_P1/
│
├── Stock_Analysis_P1.ipynb      # Main Notebook (ETL + Analysis + Visualization)
├── aapl_stock_prices.csv        # Apple stock dataset (raw data)
├── goog_stock_prices.csv        # Google stock dataset (raw data)
├── msft_stock_prices.csv        # Microsoft stock dataset (raw data)
└── README.md                   # Project documentation

The notebook contains the complete ETL pipeline, MySQL integration, and technical analysis workflow.

---

## Technologies Used
- Python (Pandas, NumPy, Matplotlib)
- MySQL (for storing cleaned stock data)
- SQLAlchemy (for database connection)
- Jupyter Notebook (for development and analysis)
- GitHub (for version control and project submission)

---

## What I Learned
Through this project, I gained hands-on experience in building a complete ETL pipeline using Python and MySQL. I learned how to clean real-world datasets, handle missing values, apply business rules, and transform raw data into a structured format suitable for analysis.  
I also understood how to integrate Python with MySQL, validate loaded data using SQL queries, and perform technical analysis such as trend classification, volatility analysis, and moving averages.  
Overall, this project improved my understanding of data engineering concepts, data preprocessing, database loading, and visualization of financial data.
