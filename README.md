# Seoul-Bike-Sharing-Demand-Prediction-Project
Within this repository, you'll find a comprehensive analysis aimed at predicting the demand for rental bikes on an hourly basis. The objective is to enable a reliable and steady supply of rental bikes, achieved through the implementation of various Regression Machine Learning Algorithms.

![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/e7791703-c204-4df9-a9ee-fd5867f54dd6)

## Introduction
In numerous urban centers, rental bikes have been introduced to elevate the convenience of mobility. Ensuring the timely availability and accessibility of rental bikes to the public is crucial in minimizing waiting times. The primary concern is establishing a consistent and reliable supply of rental bikes throughout the city. Predicting the required bike count for each hour emerges as a pivotal aspect of maintaining this stability.Also it is an environmentally sustainable, convenient and economical way of improving urban mobility.

## Problem Statement
As the demand and user base for bike-sharing systems continue to expand, ensuring a consistent supply of rental bikes to the city may pose a growing challenge. The effectiveness of the bike-sharing system hinges on meeting the needs and expectations of users through high-quality facilities. Consequently, it becomes crucial to guarantee the timely availability and accessibility of rental bikes, minimizing waiting times. Forecasting the required number of bikes and identifying key factors influencing rental bike demand are essential steps in effectively managing the bike-sharing system.

## Project Goal
* Understand the trends in the data and identify key factors affecting the hourly demand for rental bikes.
* Build an appropriate regression model to forecast the number of rental bikes required per hour.

## Dataset Information
The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour and date information.
### <b>Attribute Information: </b>
* **Date** : The date of the day, during 365 days from 01/12/2017 to 30/11/2018, formating in DD/MM/YYYY, type : str, we need to convert into datetime format.

* **Rented Bike Count** : Number of rented bikes per hour which our dependent variable and we need to predict that, type : int

* **Hour**: The hour of the day, starting from 0-23 it's in a digital time format, type : int, we need to convert it into category data type.

* **Temperature(°C)**: Temperature in Celsius, type : Float

* **Humidity(%)**: Humidity in the air in %, type : int

* **Wind speed (m/s)** : Speed of the wind in m/s, type : Float

* **Visibility (10m)**: Visibility in m, type : int

* **Dew point temperature(°C)**: Temperature at the beggining of the day, type : Float

* **Solar Radiation (MJ/m2)**: Sun contribution, type : Float

* **Rainfall(mm)**: Amount of raining in mm, type : Float

* **Snowfall (cm)**: Amount of snowing in cm, type : Float

* **Seasons**: Season of the year, type : str, there are only 4 season's in data .

* **Holiday**: If the day is holiday period or not, type: str

* **Functioning Day**: If the day is a Functioning Day or not, type : str
