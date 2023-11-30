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

## Technical Overview
### Exploratory Data Analysis (EDA)
![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/2e2c438b-fa04-45ab-bc89-23e81c9714ee)
![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/fb055246-f581-48d5-a185-879217bf9c96)
![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/5ebf09cf-6656-4bae-b851-0c2af27ab057)
![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/a8656345-ed36-4d6e-9635-96870945e838)

**Summary**
1. Generally people use rented bikes during their working hour from 7am to 9am and 5pm to 9pm.

2. The demand of the rented bike is high in May, June, July, August, September as compare to other months.these months are comes inside the summer season.

3. In the week days(Peak Time: 7 am to 9 am, 5 pm to 9 pm) the demand of the bike higher because of the office.

4. On weekend days, the demand of rented bikes are very low specially in the morning hour but from 4 pm to 8 pm the demand slightly increases.

5. Peoples use rented bikes mostly on functioning day.

6. Highest rented bike : in summer season(peak time: 7am-9am and 5pm-9pm), lowest rented bike : in winter season, highest rented bike on holidays : in May-June month, lowest rented bike on holidays : in December-January-February month

7. The use of rented bike is highest when there is no holiday(peak time: 2pm-8pm)

![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/1032ae9e-afd9-43f7-b641-f23f4c1ccd76)

8. From the above plot we see that people like to ride bikes when it is pretty hot around 25°C average.
9. We can see from the above plot that the demand of rented bike is uniformly distributed despite of wind speed but when the speed of wind was 7 m/s then the demand of bike also increase that clearly means peoples love to ride bikes when its little windy.
10. from the above plot we see that, the amount of rented bikes is huge, when there is solar radiation. when there is increase in solar radiation, there is increase in rented bike.
11. we can see from above plot, when there is no rain, rented bike count is huge, but when there is rain, we can see increase in bike rented only at certain points, maybe it is when people are going to home from office on weekdays. but otherwise,there is no huge spike in the rented bike.
12. We can see from the plot that, on the y-axis, the amount of rented bike is very low When we have more than 4 cm of snow, the bike rents is much lower

![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/9903bb48-a7c7-494e-af5f-64c3991098bf)

13. From the above regression plot of all numerical features we see that the columns Temperature, Wind_speed, Solar_Radiation Snowfall are positively relation to the target variable.which means the rented bike count increases with increase of these features.
14. Rainfall, Snowfall, Humidity these features are negatively related with the target variable which means the rented bike count decreases when these features increase.

### **Feature Selection**
![image](https://github.com/roy-rajarshi-27/Seoul-Bike-Sharing-Demand-Prediction-Project/assets/126455566/b39641fe-154b-4cb0-8b6b-9162df16836f)

We can observe on the heatmap that on the target variable line the most positively correlated variables to the bike rent are :

* the temperature
* the dew point temperature
* the solar radiation
* Hour

And most negatively correlated variables are:

* Humidity
* Rainfall
* weekdays or weekends

from above correlation map, we can see that, there is high correlation between 'Dew Point Temperature' and Temperature. here we are featuring the best suitable model,sp we have to drop either one of the feature i.e. either Temperature or Dew Point Temperature.

### **Modelling**
Different Models which are used in the Project:
* Linear Regression
* Ridge Regression
* Decision Tree Regressor with GridSearchCV
* Random Forest
* Gradient Boosting Regressor
* Gradient Boosting with GridSearchCV
* XGBoost with RandomisedSearchCV

**Results Table of different Models**
| Model_Name                                | R^2 of train datset | Adjusted R^2 of train datset | R^2 of test datset | Adjusted R^2 of test datset |
|-------------------------------------------|---------------------|------------------------------|--------------------|-----------------------------|
| Linear Regression                         | 80.4%               | 79.9%                        | 80.5%              | 80%                         |
| Ridge Regression                          | 80%                 | 79%                          | 80.5%              | 80%                         |
| Decision Tree with GridSearchCV           | 94%                 | 93.9%                        | 85.4%              | 85%                         |
| Random Forest                             | 98.9%               | 98.8%                        | 91.3%              | 91%                         |
| Gradient Boosting                         | 86.3%               | 85.9%                        | 84.6%              | 84.1%                       |
| Gradient Boosting with GridSearchCV       | 95.4%               | 95.1%                        | 91.5%              | 91.2%                       |
| XgBoost Regressor with RandomisedSearchCV | 97%                 | 96.9%                        | 91.7%              | 91.5%                       |

**Conclusion**
* No overfitting is seen.

* Random forest Regressor, Gradient Boosting gridsearchcv, XgBoost Regressor with RandomizedSearchCV gives the highest R2 score.

* Feature Importance value for Random Forest, Gradient Boosting, XgBoost are different.

* We can deploy Random Forest, Gradient Boosting with GridSearchCV, XgBoost with RandomizedSearchCV model.
