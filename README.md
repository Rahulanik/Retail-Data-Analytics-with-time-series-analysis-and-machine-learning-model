# Retail-Data-Analytics-with-time-series-analysis-and-machine-learning-model

# About the dataset
A retail company operate 45 retail stores across multiple regions, with each store consisting of several departments. 
Throughout the year, the company organises several markdown events, particularly in the weeks leading up to major holidays. 
The four most significant holidays are the Super Bowl, Labour Day, Thanksgiving, and Christmas. For evaluation purposes, the weeks that include these 
Holidays are given five times the weight of non-holiday weeks.

One of the primary challenges in modeling retail data is the need to make decisions with limited historical information. 
Major holidays and key events occur only once a year, which restricts the opportunity to evaluate how strategic decisions influence overall performance. 
Additionally, markdowns are known to significantly impact sales, but the difficulty lies in predicting which departments will be affected and to what extent.

Three Separate CSV Data Files have been uploaded.
# Stores
Anonymised information about the 45 stores, indicating the type and size of store 
# Features
1. Store - the store number
2. Temperature - average temperature in the region
3. Fuel_Price - cost of fuel in the region
4. MarkDown1-5 - anonymized data related to promotional markdowns. MarkDown data is only available after Nov 2011, and is not available for all stores all the time.
 Any missing value is marked with an NA.
5.CPI - the consumer price index
6.Unemployment - the unemployment rate
7.IsHoliday - whether the week is a special holiday week
# Sales
1.Store - the store number
2. Dept - the department number
3. Date - the week
4. Weekly_Sales -  sales for the given department in the given store
5. IsHoliday - whether the week is a special holiday week



# The Task
1. Predict the department-wide sales for each store for the following year.
2. Model the effects of markdowns on holiday weeks.
3. Provide recommended actions based on the insights drawn, with prioritization placed on largest business impact
