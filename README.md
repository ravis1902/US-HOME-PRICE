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
* Number of new houses supplied - The months' supply is the ratio of new houses for sale to new houses sold. This statistic provides an indication of the size of the new for-sale inventory in relation to the 
  number of new houses currently being sold. 
* Working Population - This the population of people working in U.S.
* Urban Population - he population inhabiting areas that have a greater population density than rural areas in U.S.
* Percentage of population above 65 - Population ages 65 and above as a percentage of the total population, which counts all residents regardless of legal status or citizenship--except for refugees 
* Housing subsidies - the policies given by goverment to make affordability of houses easier
* Number of Households - Household is an occupied housing unit. Householder is a person in whose name the housing unit is rented or owned. This person must be at least 15 years old.


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
  (Unemployment is the only column that is negatively correlated with target also it is tue if unemployment increases. People won't be able to afford houses and demand will decrease
  which can lead to decline in House Prices. CPI and Income showing strong positive correlation with House Price as with increase in both the factors the House Price will also hike in U.S.
  but some pair of predictors are showing strong correlation with each other like subsidy & CPI, per capita GDP & CPI so Ihave drop such columns as it will impact the model accuracy
  ![image](https://github.com/ravis1902/US-HOME-PRICE/assets/121948844/0296e675-1329-4b78-95e5-de741694a073)


- After scaling the data I have split it into train and test set and perform 2 different ML algorithm
  1. In Linear Regression the accuracy comes out to be 81 % from this algorithm. The coefficient of variables are not much of help as the Consumer Price Index is effect not showing good coefficient as with 
     increase in every unit of CPI House Price must also increase but indirectly due to other factors like interest rates, Inflation, increase in supply and demand.
     It's important to note that the relationship between the CPI and house prices is not always straightforward, and local market conditions, demographic trends, and other factors can play a significant role. 
     

  2. I approach other algorithm that is Decision tree Regression and with hat my accuracy comes out to be 90%.
 
     My conclusion is that Decision tree much better approach as compared to Linear Regression

     As per my view there should be some other factors included like:
     * Marriage Rate - (People tend to buy homes after they get married. So, it might have some effect. No data could be found)
     * Tax Rate - (Not suffiecient records)
     * Location - The house which located with low accessibility of services and ammenities like Highway, School, Hospital, shopping   complex have cheaper rate(No such data available for this factor)
     * House Size - Data was only available from 2016 to 2023





