# Stock Analysis - P1 (Data Engineering Project)

## Project Overview
This project focuses on analyzing historical stock market data of multiple companies using an end-to-end ETL (Extract, Transform, Load) pipeline. The main objective is to clean raw stock datasets, apply business rules, store the processed data in MySQL, and perform technical analysis such as trend analysis, volatility detection, and price visualization.  
The project uses stock datasets of AAPL, GOOG, and MSFT to identify patterns, performance trends, and key financial insights through data engineering and visualization techniques.

---

## Business Rules Implemented
The following business rules were applied during the data transformation phase:

1. Missing Value Treatment:
   - close_price values were replaced using median close price per stock
   - volume missing values were replaced with 0
   - high_price was corrected using max(open_price, close_price)
   - low_price was corrected using min(open_price, close_price)

2. Price Sanity Checks:
   - Ensured high_price ≥ open_price and close_price
   - Ensured low_price ≤ open_price and close_price
   - Any violations were automatically corrected during preprocessing

3. Trend Classification:
   - daily_return > 0 → UP
   - daily_return < 0 → DOWN
   - daily_return = 0 → NO_CHANGE

---

## ETL Pipeline Flow
The project follows a structured ETL pipeline:

CSV Files (Raw Stock Data)  
        ↓  
Python (Pandas) – Data Cleaning & Transformation  
- Handling missing values  
- Removing duplicates  
- Applying business rules  
        ↓  
MySQL Database (Clean Table: stock_prices)  
        ↓  
SQL Validation + Data Visualization (Matplotlib)

This pipeline ensures that raw data is converted into a clean and analysis-ready dataset.

---

## Business Insights Generated
Through the analysis of cleaned stock data, the following insights were generated:
- Identification of best performing stock based on average daily returns
- Detection of highest volatility stock using standard deviation of returns
- Analysis of volume vs price movement correlation
- Trend ratio analysis (UP, DOWN, NO_CHANGE) for each company
- Identification of abnormal volume spike days
- Visualization of daily closing price trends for each stock

These insights help in understanding stock behavior and market trends.

---


<img width="914" height="305" alt="image" src="https://github.com/user-attachments/assets/a9b02b3d-ac86-4d6e-9b00-82c02e0b94ad" />


---

## Technologies Used
- Python (Pandas, NumPy, Matplotlib)
- MySQL (Database for storing cleaned data)
- SQLAlchemy (Database connection)
- Jupyter Notebook (Development environment)
- GitHub (Version control and project submission)

---

## What I Learned
Through this project, I gained practical experience in building a real-world ETL pipeline using Python and MySQL. I learned how to clean and preprocess raw datasets, implement business rules, and perform structured data analysis.  
Additionally, I understood how to integrate MySQL with Python, validate data using SQL queries, and create meaningful visualizations for stock trend analysis.  
This project also improved my understanding of data engineering concepts such as data transformation, database loading, and analytical reporting using financial datasets.
