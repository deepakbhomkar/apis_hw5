# Homework 5 APIs

## Part 1 - Personal Finance Planner

This is a personal finance planner application that will allow employees of credit union to visualize their savings composed by investments in shares and cryptocurrencies to assess if they have enough money as an emergency fund.

The following assumptions have been made:

* The average household income for each member of the credit union is $12,000.
* Every union member has a savings portfolio composed of cryptocurrencies, stocks and bonds:
    * Assume the following amount of crypto assets: 1.2 BTC and 5.3 ETH.
    * Assume the following amount of shares in stocks and bonds: 50 SPY (stocks) and 200 AGG (bonds).

The following operations have been performed to determine the savings health of the employees

* Calculate the value of crypto assets and shares:
    * Use https://api.alternative.me to get current crypto share prices and calculate the value based on the quantity of crypto shares
    * Use alpaca_trade_api to get current closing share price and calculate the valkue based on the quantity of shares

* Calculate total value of crypto and shares and compare with the emergency fund available.

Based on this employee emergency fund of 60,000.00 USD gives a resut that the employee has enough funds in the emergency fund for a safe retirement


## Part 2 - Retirement Planning

The tool is a retirement planning tool that will project the portfolio performance after n number of years and calculate the portfolio returns based on an initial investment amount

The following approach was taken to forecast the portfolio returns:
* Use Alpaca API to get fetch the closing prices for last 5 years
* Forecast was executed for 30 years. n=30
* Configure and execute Monte Carlo Simulation of 500 runs and 30 years for the 40/60 portfolio of shares to get the cumulative returns

    ![Simulation Plot for 30 years](MC_thirtyyears_sim_plot.png)
    ![Distribution of Cumulative Returns across Simuations](MC_thirtyyears_dist_plot.png)

    *       Given an initial investment of `$20,000`, there is a `95%` chance that an initial investment of `$20,000` in the portfolio over the next 30 years will end within in the range of `$65448.17` and `$687742.61`

* The same process was repeated for n=5 and n= 10 years projection and the following results were observed:

    ![](MC_fiveyears_sim_plot.png)
    ![](MC_fiveyears_dist_plot.png)

    *       There is a `95%` chance that an initial investment of `$60,000` in the portfolio over the next 5 years will end within in the range of `$55178.17` and `$150024.04`

    ![](MC_tenyears_sim_plot.png)
    ![](MC_thirtyyears_dist_plot.png)

    *        There is a `95%` chance that an initial investment of `$60,000` in the portfolio over the next 10 years will end within in the range of `$55178.17` and `$150024.04`