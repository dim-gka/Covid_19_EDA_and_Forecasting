# Covid_19_EDA_and_Forecasting

Power BI Dashboard: https://app.powerbi.com/view?r=eyJrIjoiNTA2NzE1MGEtMmYxMS00ZWI5LWJkNGYtNjUwNGU3NWU3ZjY3IiwidCI6IjBkZmQwNWIzLTdlYjEtNDAyZi1iYzM4LWJkZDU2NmQ3OGExMSIsImMiOjh9&pageName=ReportSection



The COVID-19 Dataset is provided by Our World in Data, and it is updated daily, including data on confirmed cases, deaths and testing, while also demographics and social measures about each country. In addition, a full codebook is available with a description and source for each variable in the dataset.
The first thing was to examine the dataset structure and find the “quality” of the data (e.g., presence of missing data, invalid values etc.). In some features correlated with vaccinations and deaths, there are more missing values in the first year of the pandemic (2020), which is not something not expected in the early stages. The Dataset consists of 67 features, which are not all valuable to the performed analysis. After careful inspection, the valuable features are grouped in categories (Location and Date, Covid Cases, Vaccinations Rate, Demographics, Medical and Life Quality).

Some of the selected features had missing values, that needed to be filled. This is something to be expected as not all countries provide daily data, especially the least developed ones. There are several techniques available, but in the current case the Interpolation method was selected to be applied on the features. Interpolation is the process of using known data values to estimate unknown data values, and on its simplest forms is the linear interpolation. It is important to note that we make an approximate assumption that the covid-19 follows a linear pattern.
Performing interpolation in other columns with very high percentage of missing values, like "new_tests_per_thousand" or "people_vaccinated_per_hundred", may result in unreliable data that are not reflecting the reality.  Also, these features are expected to have many missing values, as vaccines and tests came at a later stage of the covid outbreak.

Regarding the prediction task
ARIMA models provide another approach to time series forecasting. Exponential smoothing and ARIMA models are the two most widely used approaches to time series forecasting and provide complementary approaches to the problem. While exponential smoothing models are based on a description of the trend and seasonality in the data, ARIMA models aim to describe the autocorrelations in the data. In the current project, the SARIMA model was selected, which is an ARIMA model with a seasonal component, that better describes the current dataset, due to the seasonal nature of diseases. The findings are presented in the Power BI Dashboard.


Files
    covid_data_cleaned3.part1 & covid_data_cleaned3.part2   is the generated .csv from Data Cleansing.ipynb  
    combined_country_data.csv  is the file generated from Covid_Prediction.ipynb
