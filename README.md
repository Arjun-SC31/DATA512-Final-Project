# Project Part 4

## Project Goals:

Estimate the impact wildfires and the air quality have on the economic situation in Cheyenne, WY. Provide insights for the future.

## Terms of Use, License:

EPA AQI API:
The API has the following limits imposed on request size:

Length of time. All services (except Monitor) must have the end date (edate field) be in the same year as the begin date (bdate field).
Number of parameters. Most services allow for the selection of multiple parameter codes (param field). A maximum of 5 parameter codes may be listed in a single request.
Please adhere to the following when using the API.

Limit the size of queries. Our database contains billions of values and you may request more than you intend. If you are unsure of the amount of data, start small and work your way up. We request that you limit queries to 1,000,000 rows of data each. You can use the "observation count" field on the annualData service to determine how much data exists for a time-parameter-geography combination. If you have any questions or need advice, please contact us.
Limit the frequency of queries. Our system can process a limited load. If scripting requests, please wait for one request to complete before submitting another and do not make more than 10 requests per minute. Also, we request a pause of 5 seconds between requests and adjust accordingly for response time and size.
If you violate these terms, we may disable your account without notice (but we will be in contact via the email address provided).


## Data Sources: 

1. Combined Wildland fire datasets for the United States and Certain Territories: https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81

2. EPA Air Quality System API: https://aqs.epa.gov/aqsweb/documents/data_api.html

3. Federal Reserve Bank of St.Louis: https://fred.stlouisfed.org/



## API Documentation:

1. Pandas: https://pandas.pydata.org/docs/index.html

2. Matplotlib: https://matplotlib.org/stable/

3. Requests: https://requests.readthedocs.io/en/latest/

5. EPA: https://aqs.epa.gov/aqsweb/documents/data_api.html

6. Scikit-Learn: https://scikit-learn.org/stable/

7. Statsmodels: https://www.statsmodels.org/stable/index.html


## Procedure to Obtain EPA AQI API Access:

Before you can use the API you need to request a key. You will use an email address to make the request. The EPA then sends a confirmation email link and a 'key' that you use for all other requests.

You only need to sign-up once, unless you want to invalidate your current key (by getting a new key) or you lose your key.

Once you have a key, the next thing is to get information about the different types of air quality monitoring (sensors) and the different places where we might find air quality stations. The monitoring system is complex and changes all the time. The EPA implementation allows an API user to find changes to monitoring sites and sensors by making requests - maybe monthly, or daily. This API approach is probably better than having the EPA publish documentation that may be out of date as soon as it hits a web page.

The EPA AQS API has limits on some call parameters. Specifically, when we request data for sensors we can only specify a maximum of 5 different sensor values to return. This means we cannot get all of the Air Quality Index parameters in one request for data. We have to break it up.


## How to use this project:

1. Run all cells in "Common Analysis.ipynb" in the order that they appear.

2. Run all cells in "AQI_Data_Acquisition.ipynb" in the order that they appear.
	Note: Replace the EPA AQI API credentials with your own email and access token.

3. Run all cells in "Forecasting_and_Visuals.ipynb" in the order that they appear.

4. Run all cells in "Future_Insights.ipynb" in the order that they appear
5. 
## Intermediate Files Created Chronologically:

1. 'data_with_distance.csv'

2. "start_end_dates_file.csv" 

3. "Final_States_Data.csv" 

4. "Final_Data.csv"

5. "Fire_Season_Data.csv"

6. 'fire_season_estimates.csv'

7. "particulate_pollutant_data.json"

8. "gaseous_pollutant_data.json"

9. "gaseous_aqi.csv"

10. "particulate_aqi.csv"

11. "final_aqi_each_year.csv"

## Files used for analysis

1. "final_analysis_data.csv" consists of the EPA AQI values for Cheyenne, WY. It also contains some useful information about Cheyenne, WY obtained from the Federal Reserve Bank of St. Louis
   (FRED), that has been included into it from the data collected from FRED. The data in this file is used for much of the time-series analysis and model building done in "Future_Insights.ipynb"
   
## Issues worth considering:

2. Issues with API timing out:

The text below is quoted directly from EPA AQI API documentation

The API has the following limits imposed on request size:

Length of time. All services (except Monitor) must have the end date (edate field) be in the same year as the begin date (bdate field).
Number of parameters. Most services allow for the selection of multiple parameter codes (param field). A maximum of 5 parameter codes may be listed in a single request.
Please adhere to the following when using the API.

Limit the size of queries. Our database contains billions of values and you may request more than you intend. If you are unsure of the amount of data, start small and work your way up. We request that you limit queries to 1,000,000 rows of data each. You can use the "observation count" field on the annualData service to determine how much data exists for a time-parameter-geography combination. If you have any questions or need advice, please contact us.
Limit the frequency of queries. Our system can process a limited load. If scripting requests, please wait for one request to complete before submitting another and do not make more than 10 requests per minute. Also, we request a pause of 5 seconds between requests and adjust accordingly for response time and size.
