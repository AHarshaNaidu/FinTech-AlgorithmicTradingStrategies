OVERVIEW:
Craft and implement trading strategies that adeptly navigate market trends, optimizing portfolios for maximum returns while mitigating risks. This project covers a range of techniques, from data manipulation and analysis to the application of popular indicators such as Bollinger Bands and Ichimoku clouds. Additionally, it delves into portfolio optimization using Markowitz's modern portfolio theory and explores the creation of an efficient frontier.

KEY FEATURES::
Data Handling: Leverage the power of Pandas and NumPy for efficient handling and manipulation of large multidimensional arrays.
Visualization: Utilize Matplotlib, Plotly, and Cufflinks for visually analyzing stock prices, returns, and various technical indicators.
Technical Indicators: Implement popular technical indicators such as Bollinger Bands and Ichimoku clouds for enhanced market analysis.
Portfolio Optimization: Apply Harry Markowitz's modern portfolio theory to create efficient portfolios that optimize returns and minimize risk.
Efficient Frontier: Explore and visualize the efficient frontier to identify optimal portfolios based on risk-return trade-offs.
Random Portfolio Generation: Generate and analyze thousands of random portfolios to identify the one with the highest Sharpe Ratio.
Sector Analysis: Explore cumulative returns for stocks within different sectors, aiding in sector-based investment decisions.

GETTING STARTED:
Clone the repository to your local machine.
Install the required dependencies using pip install -r requirements.txt.
Open and run the Jupyter notebooks to explore various aspects of algorithmic trading strategies.
Experiment with different stock tickers, time frames, and portfolio compositions.

PREREQUISITES:
Ensure you have the following libraries installed-

numpy for working with large multidimensional arrays
pandas for data manipulation and analysis
matplotlib for plotting
datetime for handling dates
time for introducing delays
yfinance for fetching stock data
cufflinks and plotly for interactive plotting

pip install numpy pandas matplotlib yfinance cufflinks plotly

CONSTANTS:
PATH = "D:/FinTech/Wilshire_Stocks/"
S_DATE = "2017-02-01"
E_DATE = "2022-12-06"
S_DATE_DT = pd.to_datetime(S_DATE)
E_DATE_DT = pd.to_datetime(E_DATE)

FUNCTIONS:
get_stock_df_from_csv(ticker)
Reads a DataFrame from a CSV file, changes the index to date, and returns it.

add_daily_return_to_df(df)
Adds a 'daily_return' column to the DataFrame, representing the daily return of the stock.

add_cum_return_to_df(df)
Adds a 'cum_return' column to the DataFrame, representing the cumulative return of the stock.

add_bollinger_bands(df)
Adds Bollinger Bands to the DataFrame, including the middle band, upper band, and lower band.

add_Ichimoku(df)
Adds Ichimoku indicators (Conversion Line, Baseline, Leading Span A/B, Lagging Span, Cloud) to the DataFrame.

save_to_csv_from_yahoo(folder, ticker)
Fetches historical closing price data from Yahoo Finance and saves it to a CSV file.

plot_with_boll_bands(df, ticker)
Plots Candlestick chart with Bollinger Bands for a given stock.

get_Ichimoku(df)
Plots Candlestick chart with Ichimoku indicators for a given stock.

merge_df_by_column_name(col_name, sdate, edate, *tickers)
Merges multiple stocks into one DataFrame based on a specified column name.

get_cum_ret_for_stocks(stock_df)
Returns a DataFrame with the cumulative return for a list of stocks.

USAGE:
Example usage for fetching and analyzing stock data:

tickers = get_column_from_csv("D:/FinTech/Wilshire-5000-Stocks.csv", "Ticker")
for ticker in tickers:
    try:
        print("Working on :", ticker)
        new_df = get_stock_df_from_csv(ticker)
        new_df = add_daily_return_to_df(new_df)
        new_df = add_cum_return_to_df(new_df)
        new_df = add_bollinger_bands(new_df)
        new_df = add_Ichimoku(new_df)
        new_df.to_csv(PATH + ticker + '.csv')
    except Exception as ex:
        print(ex)

PORTFOLIO OPTIMIZATION:
Explore Markowitz Portfolio Optimization and Efficient Frontier plotting with functions like get_port_shares, get_port_weighting, get_port_val_by_date, and more. Additionally, the script provides sector-wise analysis and cumulative return calculations.

DISCLAAMIER:
This code is provided for educational purposes only. Use it at your own risk, and make sure to understand the implications of algorithmic trading and financial markets. Always consult with a financial professional before making any investment decisions.

Happy Coing! Happy Trading!!
