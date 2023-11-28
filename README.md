# US-HOME-PRICE

**Task** - Using publically available data for the national factors that impact supply and demand of homes in US, build a model to study the effect of these variables on home prices.

The following variables are chosen for the study-

* Unemployment Rate -  This column depits that number of unemployed people in the US. 
* Per Capita GDP - It is an economic metric that breaks down a country's economic output per person.
* Median Household Income - This is a important factor that comes under the economic factors affecting housing market is related to economic growth. If
  average income for people in US rises then demand for house also rises which leads to increase in home price
* Construction Prices - This is an index for Construction price for houses in US over the last 20 years.
* CPI - The Consumer Price Index (CPI) is a measure that examines the average change in prices paid by consumers for goods and services over the last 20 years
* Interest Rates - Interest rates influence the monthly payment value for mortgages. A high-interest rate would increase mortgage costs and reduce the demand for a house to be purchased
* Number of new houses supplied - 
* Working Population - 
* Urban Population - p
* Percentage of population above 65 - 
* Housing subsidies - 
* Number of Households - 


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

This one variable Per Capita GDP has quartely data and five other variables like (Urban Population, Old Population, Income, Subsidy and Number of Household) has yearly.
Rest other variables has monthly data for last 20 years.

The data has been prepared by merging this variable on the basis of dates. The Nan values in the Per Capita GDP imputed through Interpolation method.

# EDA
- Univariate Analysis to check the distribution of columns.
  House Price Index and Construction Price are higly skewed as shown in figure below
![download](https://github.com/ravis1902/US-HOME-PRICE/assets/121948844/2f1f3b78-7b29-4a4e-bf0b-3addb609316c)


- Checking outlier through boxplot visualization.
  CSUSHPISA, unemployed, construction price have outliers which has been fixed using IQR method to remove outliers
  ![download](https://github.com/ravis1902/US-HOME-PRICE/assets/121948844/f6757ee0-833e-4b5a-9a98-0437b4cea4fa)

- Checking null values and imputing those Nan values with mean of the column
- Using Correlation matrix to check the strength of the each predictors with the target variable
- ![image](https://github.com/ravis1902/US-HOME-PRICE/assets/121948844/0296e675-1329-4b78-95e5-de741694a073)







