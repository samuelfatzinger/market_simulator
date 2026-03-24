# Market Simulator

## Overview

This project implements a simple market simulator that processes trading orders and tracks the value of a portfolio over time. The simulator reads orders from a CSV file, executes trades, and computes portfolio performance metrics.

The resulting portfolio values can be used to evaluate trading strategies using standard financial indicators.

## Features

- Processes BUY and SELL orders from CSV files
- Tracks portfolio value over time
- Computes performance metrics
- Uses adjusted closing prices
- Returns portfolio values as a pandas DataFrame



## Input Format

Orders are provided as a CSV file with the following columns:

| Date | Symbol | Order | Shares |
| :---: | :---: | :---: | :---: | 
| yyyy-mm-dd | e.g. AAPL, GOOG | BUY or SELL | Number of shares |

### Example

| Date | Symbol | Order | Shares |
| :---: | :---: | :---: | :---: | 
| 2008-12-03 | AAPL | BUY |130 |
| 2008-12-08 | AAPL | SELL | 130 |
| 2008-12-05 | IBM | BUY | 50 |

## Usage

Run the simulator:

```bash
python -m marketsim
```

## Output

`compute_portvals()` returns the total value of the portfolio for each trading day using adjusted closing prices. Daily portfolio value is calculated as available cash plus the current value of all held equities. 

`compute_portvals()` returns a DataFrame with one column.

## Performance Metrics

The portfolio can be evaluated using the following metrics:

- Sharpe ratio (assuming 252 trading days per year and a risk-free rate of 0)
- Cumulative return
- Standard deviation of daily returns (of total portfolio)
- Average daily return (of total portfolio)
- Ending portfolio value

## Visualization

Portfolio value can be plotted over the trading period.

## Requirements

- Python
- pandas
