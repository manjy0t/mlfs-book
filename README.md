# **Air Quality Prediction for Nishitokyoshi,Shimohoya, Japan**

This project is part of Lab 1 of the ID2223 Scalable Machine Learning and Deep Learning course course. The main aim of the project is to forecast air quality (PM2.5 levels) for the next 7 days using historical and forecasted weather data, along with historical air quality data. Here are the steps to achieve this:
## 1. Backfill Feature Pipeline:
   - Download over a year of historical weather data and air quality data from external sources (such as Open-Meteo and the AQICN platform).
   - Load the air quality data into a CSV file and access the weather data via an API. Then, register both datasets as two Feature Groups in Hopsworks: one for weather data and one for air quality data.
## 2. Daily Data Pipeline:
   - Create a scheduled daily pipeline that downloads the previous day's weather data and air quality data, and forecasts air quality for the next 7 days.
   - Update the corresponding Feature Groups in Hopsworks.
   - Use GitHub Actions to automate the daily execution of this pipeline.
## 3. Training Pipeline:
   - Select the relevant features from the Feature Groups to create a Feature View.
   - Train an XGBoost model to predict air quality (PM2.5 levels) using the selected features.
   - Register the trained model with Hopsworks for future use.
## 4. Batch Inference Pipeline and Dashboard:
   - Develop a batch inference pipeline that downloads the registered model from Hopsworks.
   - Use the model to predict air quality for the next 7-10 days and display the predictions in a dashboard.
## 5. Additional Feature:
    - Enhance the model by adding a new feature: lagged air quality values for the previous 1-3 days.

