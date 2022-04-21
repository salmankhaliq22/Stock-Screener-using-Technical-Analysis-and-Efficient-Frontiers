# Project 1: Stock Screener

The Goal of this project is to screen the individual stocks from the S&P 500 stock list and make an optimized portfolio of stocks with better returns, risk, sharpe ratio and comparitive diversity.

## 01 - Initial Data from yfinance

- Initially we gathered the ticker list from wikipedia
- Using that ticker list we grabbed the data for all the tickers from yahoo finance
- Saved the file on the computer for future use

## 02 - Making a Database of Individual Tickers

- Dropped all the columns with threshold value 3085 i-e all the companies which came to market after 2010-01-01
- dropped all the null values
- Made individual ticker database for later use
- Added percent change and Normalized Adjusted Close columns in the database

## 03 - Picking the Best Performers

- Started out with 443 stocks that are in the S&P that were founded before the year 2011. 
- From these stocks we compared each stocks returns over the S&P return over the exact same time period
- This gave us a ratio of each stocks return over the S&Ps return as a whole
- We then took the top 30% performers to analyze for creating the portfolios. 
- We now had a group of 133 companies to analyze allowing for faster and more accurate analysis in terms of profitability.

## 04 - Portfolio 1 - SMA - PE ratio

### Conditions
- condition_1 = latest_price > moving_average_150 > moving_average_200
- condition_4 = pe_ratio < 40

Picked the stocks meeting the above two conditions

### Optimization
- Optimized the returns based on best sharpe ratio using pyportfolio opt library
- Used EfficientFrontier, risk models and expected returns to optimize the stocks
- Optimized the weights of the stocks for maximum returns using DiscreteAllocation for a $15,000 initial investment

### Result 
- Expected annual return: 26.1%
- Annual volatility: 16.6%
- Sharpe Ratio: 1.46

## 05 - Portfolio 2 - SMA - Low of 52 Week - High of 52 Week - PE ratio

### Conditions
- condition_1 = latest_price > moving_average_150 > moving_average_200
- condition_2 = latest_price >= (1.3 * low_52week)
- condition_3 = latest_price >= (0.75 * high_52week)
- condition_4 = pe_ratio < 40

Picked the stocks meeting the above four conditions

### Optimization
- Optimized the returns based on best sharpe ratio using pyportfolio opt library
- Used EfficientFrontier, risk models and expected returns to optimize the stocks
- Optimized the weights of the stocks for maximum returns using DiscreteAllocation for a $15,000 initial investment

### Result 
- Expected annual return: 28.4%
- Annual volatility: 17.3%
- Sharpe Ratio: 1.53

## 06 - Portfolio 3 - Low of 52 Week - High of 52 Week - PE ratio

### Conditions
- condition_2 = latest_price >= (1.3 * low_52week)
- condition_3 = latest_price >= (0.75 * high_52week)
- condition_4 = pe_ratio < 40

Picked the stocks meeting the above three conditions

### Optimization
- Optimized the returns based on best sharpe ratio using pyportfolio opt library
- Used EfficientFrontier, risk models and expected returns to optimize the stocks
- Optimized the weights of the stocks for maximum returns using DiscreteAllocation for a $15,000 initial investment

### Result 
- Expected annual return: 26.0%
- Annual volatility: 16.5%
- Sharpe Ratio: 1.45

## 07 - Portfolio 4 - SMA - Low of 52 Week - High of 52 Week

### Conditions
- condition_1 = latest_price > moving_average_150 > moving_average_200
- condition_2 = latest_price >= (1.3 * low_52week)
- condition_3 = latest_price >= (0.75 * high_52week)

Picked the stocks meeting the above three conditions

### Optimization
- Optimized the returns based on best sharpe ratio using pyportfolio opt library
- Used EfficientFrontier, risk models and expected returns to optimize the stocks
- Optimized the weights of the stocks for maximum returns using DiscreteAllocation for a $15,000 initial investment

### Result 
- Expected annual return: 27.9%
- Annual volatility: 16.2%
- Sharpe Ratio: 1.60

## How to Run the code

- Clone the repo and run from notebook 01-03 in order and the the remaining notebooks are individual portfolio.
- Run these portfolios as desired.
- Three folders (figures, portfolio, stock_data) are needed to be created in the environment otherwise code will give error

## Any Feedback would be greatly appreciated!
