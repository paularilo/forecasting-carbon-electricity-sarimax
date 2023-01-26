**Forecasting electricity carbon intensity using SARIMAX**

**Overview**
* Where does the electricity I use come from?
* How much of my country's electricity consumption comes from renewable energies?
* When in the day is it "cleaner" to charge my electric car? 

In the middle of the current energetic crisis, these questions acquire unprecedented relevance. Here, we used time series modelling to **forecast the hourly carbon intensity of electricity up to 48 hours ahead**.

The data used here was retrieved from **electricitymap.org** (https://electricitymap.org). Electricitymap provides real-time visualizations about the origin of the electricity consumed across 50+ countries. In particular, it provides an hourly view of the carbon intensity of electricity in grams of CO2-equivalent per kWh electricity consumed (gCO2e/kWh).

These kind of rich, multifaceted data allows us to calculate forecasts taking into account multiple factors such as the season, the weather conditions, imports from other countries or exogenous variables (e.g., last forecasts).

**Procedure**
* Language: Python 3
* The dataset: 6 years of gCO2e/kWh data from France with hourly resolution. Retrieved with API.
* Modelling: SARIMAX (Seasonal Auto-Regressive Integrated Moving Average with eXogenous factors). Arima model with seasonality and last predictions as exogenous (imposed) features.
* Evaluation: The model is evaluated using mean absolute percentage error from sklearn. 

**Applicability** <br>
With the appropriate gCO2e/kWh data, this code can be used to inform the individuals and companies of a certain region and time on when it is best (or cleaner) to consume electricity. For instance, according to the electrictymaps wepbage, "Google uses Electricity Maps' forecast data to shift the timing of compute tasks running on their hyperscale data centers to times when low-carbon power sources, like wind and solar, are most plentiful." 
