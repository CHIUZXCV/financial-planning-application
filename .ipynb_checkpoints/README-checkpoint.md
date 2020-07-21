# Budgeting and Financial Planning Apps

![Financial Planner](Images/financial-planner.png)

## Background

#### Budgeting and financial planning services application. 

This application offers budgeting and financial planning services to customers by generating reports that links to their banking and investment accounts and automatically refreshes the data and charts on login. However, some of the calculations are tricky, To connect the accounts and simulate the retirement investment projections. Plaid API and iexfinance API are used to obtain account transactions and fetch retirement portfolio prices.


 #### Budget Analysis with Plaid

Used the Plaid API to obtain transaction and account data for the budget analysis section of the report.

Clone the repo and Follow the steps outlined in the budget notebook to complete the following:

1. Generate a Plaid access token to access the Developer Sandbox.

2. Use the Access token to fetch account transactions from the sandbox. You should fetch the last 90 days(or number of days you would like) of transactions from the sandbox using the following institution(or any institution):

    ```python
    INSTITUTION_ID = "ins_109508"
    ```

3. Performde basic budget analysis on the sandbox transaction and generat the following plots:

* Spending Categories Pie Chart

  ![Expenses per category](Images/pie-chart.png)

* Spending Per Month Bar Chart

  ![Expenses per month](Images/spending-month.png)

4. Use the API to fetch income data from the sandbox and print the following:

* Last Year's Income Before Tax

* Current Monthly Income

* Projected Year's Income Before Tax
________

#### Retirement Planner

Used the IEX API to fetch historical closing prices for a retirement portfolio and then ran Monte Carlo simulations to project the portfolio performance at 30 years. 

Follow the steps outlined in the budget notebook to complete the following:

##### Monte Carlo Simulation


1. Use the IEX API to fetch historical closing prices for a traditional 60/40 portfolio using the `SPY` and `AGG` tickers to represent the 60% stocks (SPY) and 40% bonds (AGG).

2. Run a Monte Carlo Simulation of 500 runs and 30 years for the 60/40 portfolio and plot the results.

    ![monte carlo](Images/monte-carlo.png)

3. Select the ending cumulative returns from the Monte Carlo simulation and calculate the interval values for a 90% confidence interval.
4. Using the ending cumulative returns, plot a histogram of the results and plot the 90% confidence interval as vertical lines on the histogram.

    ![histogram](Images/histogram.png)

##### Retirement Analysis

Use the Monte Carlo simulation data to answer the following questions:

1. What are the expected cumulative returns at 30 years for the 10th, 50th, and 90th percentiles?

The 10th, 50th, and 90th percentiles as follow

 ```python
    0.01    17.935639
    0.50    49.946016
    0.90    81.103853
 ```

2. Given an initial investment of $20,000, what is the expected return in dollars at the 10th, 50th, and 90th percentiles?

```python
    
    0.01      3.587128e+05
    0.50      9.989203e+05
    0.90      1.622075e+06
  ```

3. Given the current projected annual income from the Plaid analysis, will a 4% withdrawal rate meet or exceed that value at the 10th percentile? Note: This is basically determining if retirement income is equivalent to current income.


#### You will have $25142.65 in retirement income.


4. How would a 50% increase in the initial investment amount affect the 4% retirement withdrawal? In other words, what happens if the initial investment had been bigger?

#### You will have $37713.97 in retirement income.

5. Use the Monte Carlo data and calculate the cumulative returns at the 5%, 50%, and 95% quartiles and plot this data as a line chart to see how the cumulative returns change over the life of the investment.

    ![projected-returns.png](Images/projected-returns.png)
    
    
- - -

### Resources(Hints and Considerations)

[Plaid API Docs](https://plaid.com/docs/)

[IEX Financial API Docs](https://addisonlynch.github.io/iexfinance/stable/)

For the Monte Carlo simulation, start out by running 100 simulations for one year of returns, and when you have the code worked out, run the simulation at 100–500 simulations for 30 years (this takes a long time).


### Most importantly,enjoy the process and celebrate the outcome
