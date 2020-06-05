# Bike-Sharing-Demand-Analysis
A quick overview and insights into predicting the demand and supply of bike share pooling by building a network from scratch

## Overview

Bike Sharing is a simple pooling up concept to reduce pollution based on demands of bikes in a given area that allows multiple groups of people to share and reuse the same set of bikes automated through kiosks where a user can hold a membership and pay the rent as per the requirements basis.

## Data Understanding

The following fields are present in the dataset:

- instant: Sequential order of instances
- dteday: Date of the given ride
- season: 1, 2, 3, 4 for each season corresponding to spring, summer, autumn, winter
- yr: year
- mnth: month
- hr: hour
- holiday: 0 for working day and 1 for a holiday
- weekday: 0 to 6 for each day from Sunday to Saturday
- workingday: 0 for holiday and 1 for working day
- weathersit:<br/>
    1: Clear, Few clouds, Partly cloudy, Partly cloudy<br/>
    2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist<br/>
    3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds<br/>
    4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog<br/>
- temp: Temperature in Celsius
- atemp: "Feel" temperature in Celsius
- hum - relative humidity
- windspeed - wind speed
- casual - number of non-registered user rentals initiated
- registered - number of registered user rentals initiated
- cnt - number of total rentals (Dependent Variable)

The data is skewed in terms of distribution despite removal of outliers to a certain degree with the following plots indicating the nature of data towards right skewness before and after outlier treatment.

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/reg_plot_%26_prob_plot.png)<br/>

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/skewness.png)<br/>

## Libraries Used

- numpy
- seaborn
- matplotlib.pyplot
- missingno
- scipy

## Motivation

- Build a neural network with forward and backward pass from scratch using only numpy
- Studying the real time application of sharing bikes during week and weekends with seasonal changes in festive times
- Determining the time period of increasing the number of bikes in the area to maximize profits and resource utilization

## Files in the repository

- Data: It contains two csv files whose features are combined into hour.csv for convenience to use
- assets: Contains all output images
- network.py: The neural network class built from scratch in numpy as a separate file
- model.ipynb: The data exploration, and model building with evaluation metrics

## Analysis Summary

We build a neural network model from scratch using numpy only for the given data

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/neural_network.png)<br/>



- When is the peak hours for the demand of bike sharing?

The timing between 7 AM to 8 AM and 5 PM to 6 PM has a sudden rise in ridership which indicates that the morning office going hours and the returning office hours are densely populated and hence, users especially the registered users highly correlated with the timings are most actively using the share pooling.

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/outlier_analysis.png)<br/>

- What are the chances of the casual users to become registered users?

The casual users have a probability of 0.51 to become registered users evident from their correlation which indicates a positive increasing relationship. This also indicates that the rider business is going well with a 50% chance of getting premium users and thus can be enhanced further if we target the particular months where increased ridership can be viewed.

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/correlation.png)<br/>


- Which season has the lowest ridership?

Spring tends to have the lowest possible median and consequently less ridership which indicates that pleasant weather discourages the users to make use of bike sharing and demand decreases. The demand seems particularly high in the fall and the summers which is also interpretable because higher temperatures tends to make people frustrated, but the fall has maximum ridership which also indicates that in summers, people prefer cars or AC Buses over bikes owing to cool environment and greater convenience.

- Which time period is ideal for increasing the supply of bikes?

The time period from december 22 to new year eve seems to have typical higher surge in demand of bikes which was not completely captured by the neural network and hence, we can use this time period to optimize the number of bikes available in order to expand the user base. However, giving more offers to the existing user base ie registered users is more ideal since this is a temporary surge in demand and hence the chances that the casual users become premium susbscribers is low but with more offers to registered users, it will attract the casual users to convert to premium users.

![alt-text](https://raw.githubusercontent.com/vgaurav3011/Bike-Sharing-Demand-Analysis/master/assets/final.png)<br/>

## Summary

- December 22 to New Year is the time period where demand surges all of a sudden
- Spring has the lowest ridership while Fall has the highest ridership among all seasons
- The peak demand is for working office goers in the weekdays from 7-8 AM and 5-6 PM

## Acknowledgements
- Kaggle
- Udacity
- Andrew Trask Blog
- Grokking Deep Learning
