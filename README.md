# US-HOME-PRICE

**Task** - Using publically available data for the national factors that impact supply and demand of homes in US, build a model to study the effect of these variables on home prices.

The following variables are chosen for the study-

* Unemployment Rate -  This column depits that number of unemployed people in the US. 
* Per Capita GDP - 
* Median Household Income
* Construction Prices
* CPI
* Interest Rates
* Number of new houses supplied
* Working Population
* Urban Population
* Percentage of population above 65
* Housing subsidies
* Number of Households


Data Source - Most of the data has been gathered from https://fred.stlouisfed.org/

**Target Variable**
* Case Shiller - https://fred.stlouisfed.org/series/CSUSHPISA

**Predictor Variable**
* Unemployment Rate -  [Unemployment Rate (UNRATE) | FRED | St. Louis Fed (stlouisfed.org)](https://fred.stlouisfed.org/series/UNRATE)
* Per Capita GDP - [Real gross domestic product per capita (A939RX0Q048SBEA) | FRED | St. Louis Fed (stlouisfed.org)](https://fred.stlouisfed.org/series/A939RX0Q048SBEA)
* Median Household Income - [Real Disposable Personal Income (DSPIC96) | FRED | St. Louis Fed (stlouisfed.org)](https://fred.stlouisfed.org/series/DSPIC96)
* Construction Prices -  [https://fred.stlouisfed.org/series/WPUSI012011](https://fred.stlouisfed.org/series/WPUSI012011)
* CPI - [https://fred.stlouisfed.org/series/CPIAUCSL](https://fred.stlouisfed.org/series/CPIAUCSL)
* Interest Rates - https://fred.stlouisfed.org/series/DFF
* Number of new houses supplied - [https://fred.stlouisfed.org/series/MSACSR](https://fred.stlouisfed.org/series/MSACSR)
* Working Population - [Working Age Population: Aged 15-64: All Persons for United States (LFWA64TTUSM647S) | FRED | St. Louis Fed (stlouisfed.org)](https://fred.stlouisfed.org/series/LFWA64TTUSM647S)
* Urban Population - https://data.worldbank.org/indicator/SP.URB.TOTL.IN.ZS?end=2021&locations=US&start=2001
* Percentage of population above 65 - https://fred.stlouisfed.org/series/SPPOP65UPTOZSUSA
* Housing subsidies - https://fred.stlouisfed.org/series/L312051A027NBEA
* Number of Households - https://fred.stlouisfed.org/series/TTLHH

This one variable Per Capita GDP has quartely data and five other variables like (Urban Population, Old Population, Income, Subsidy, Number of Household) has yearly.
Rest other variables has monthly data for last 20 years.

The data has been prpared by merging this variable on the basis of dates. The five columns has been combined on year which I find the most appropriate method.
The Nan values in the Per Capita GDP imputed through Interpolation method




