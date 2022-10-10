<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.276 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Mon Oct 10 2022 12:22:35 GMT-0700 (PDT)
* Source doc: Unbenanntes Dokument
----->



# Prediction of Call Volume for Seattle Fire Department

Dispatching emergency calls in a city is challenging: There are large variations over a year and therefore deciding how many dispatchers are on duty every day is a challenging task. Here, I sought to create a model based on the emergency data from the city of Seattle ([https://data.seattle.gov/Public-Safety/Seattle-Real-Time-Fire-911-Calls/kzjm-xkqj](https://data.seattle.gov/Public-Safety/Seattle-Real-Time-Fire-911-Calls/kzjm-xkqj)), that predicts the call daily call volume of the city. For this task I decided to use XGBoost, which is a regularizing gradient boosting framework. Furthermore, I decided to use some additional data to increase the accuracy of the model. I reasoned that weather is an important feature when it comes to predicting 911 calls, since weather conditions can have an effect on traffic, accidents and health of the citizens. All these are major drivers of 911 calls. 

I divided the pipeline into 3 jupyter notebooks:



1. Preprocessing: Here I performed some preprocessing steps, including combining the 911 call data and the weather data, as well as, feature engineering. I also included some visualizations of the dataset. Note: I also included the preprocessed data in the ‘data’ folder under the name ‘combined_data_20221010’
2. training_and_test: Here I performed the actual modeling using XGBoost. I used cross-validation and a grid search approach to avoid overfitting and find the best set of hyperparameters, respectively. I achieved an RMSE of 29.39 and an mean absolute percentage error of 7.73 %
3. prediction: Here I performed the actual prediction of the 911 call volume into the future. For this I needed to include weather forecast data since weather data was of great importance for the model. For this I used the

    [https://www.weatherbit.io/api/weather-forecast-16-day](https://www.weatherbit.io/api/weather-forecast-16-day) api (it's free) to get the weather forecast of the next 10 days and use it as a feature for the prediction.
