<h1 align="center"> Extracting US Treasury Saving I-bond rates </h1>

<br>

## Objective

&nbsp;&nbsp;&nbsp; This project extracts the Savings I-bond rates from the United States Treasury with a python package called Selenium. The goal is to extract,transform, and load historical rates into a database.

The chart below depicts what is extracted from [Treasury Direct](https://www.treasurydirect.gov/savings-bonds/i-bonds/). Aninterative chart is this [repository's Github page](https://hilsdsg3.github.io/savings_i_bond_rates/).



- [Extract Historical Saving I-bond rates](#helpful_cmd_line_commands)
- [Utilize the Selenium package](#interacting_postgres)
- [Extract the bond rates through html code](#improvements)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
<br>

## Summary

&nbsp;&nbsp;&nbsp; US Treasury Saving I-bonds are safe investments backed by the full faith and credit of the United States governement. The I-bonds are issued by the United States Treasury. The I-bond is abbreviated for Intrest and the bond rates are adjusted two times a year (May 1st, November 1st). You can purchase up to $10,000 worth of I-bonds in a calendar year. Intrest gained from the I-bond is added to the value twice a year. The are a few mre rules and regulations here at [Treasury Direct](https://www.treasurydirect.gov/savings-bonds/i-bonds/).

&nbsp;&nbsp;&nbsp; The project stemmed from a lack of having ready access to the current and historic rates of I-bonds in my cloud database which is used for the portfolio calulations.

&nbsp;&nbsp;&nbsp; For the project I am able to obtain the Fixed and Inflation portion of the bond rate and the Composite. This is achieved by scraping the [Historical bond rates](https://www.treasurydirect.gov/savings-bonds/i-bonds/i-bonds-interest-rates/) using the Selenium package and [regex formulas](https://regex101.com/).

&nbsp;&nbsp;&nbsp; The resulting static chart is the following or interactively on my [github.page](https://hilsdsg3.github.io/savings_i_bond_rates/). 

![Savings I-bond rate chart](https://github.com/hilsdsg3/savings_i_bond_rates/blob/main/docs/chart.png)

The Compsite equation is derived from the Fixed and Inflation rate but not linearily.

$$\text{Composite rate = fixed rate + (2 * semi-annual inflation rate) + fixed rate * semi-annual inflation rate}$$