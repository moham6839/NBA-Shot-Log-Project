# NBA Shot Log Project

## Objective

A focused analysis on what feature or features affect made or missed shot attempts by select NBA players. 

## Overview

* Detailed dataset of NBA shot attempts from the 2014-2015 regular season.
* Conduct a comparative analysis of the top 20 players in the dataset, focusing on shooting percentages.
* Determine the best distance to shoot from that would result in made shots.
* Source: Kaggle

## Data Cleaning/EDA

* Target Variable - Shot Results(Made/Miss)
* Dropped columns that didn't affect whether player made or missed shot.
* Created dummy variables for Location(Home/Away) and top 20 players in dataset.
* Filled in null values in Shot Clock column with median.
* Features included in analysis: Player names, Location, Shot Clock, Shot Distance, Closest Defender Distance, Touch Time, and Dribbles.

## Initial Models Used

* Logistic Regression
* K-Nearest Neighbors
* Decision Tree
* Bagging Tree
* Random Forest
* XG Boost

Among the initial models, Decision Tree and XG Boost performed the best:

## Decision Tree:

![image](https://user-images.githubusercontent.com/77416319/135018466-58bf27cd-4dc9-4ae6-a052-51e24fe789bb.png)

                precision    recall  f1-score   support

           0       1.00      1.00      1.00      7936
           1       1.00      1.00      1.00      6913

    accuracy                           1.00     14849
   macro avg       1.00      1.00      1.00     14849
weighted avg       1.00      1.00      1.00     14849

                precision    recall  f1-score   support

           0       0.58      0.55      0.57      2037
           1       0.49      0.52      0.51      1676

    accuracy                           0.54      3713
   macro avg       0.54      0.54      0.54      3713
weighted avg       0.54      0.54      0.54      3713

## XG Boost:

![image](https://user-images.githubusercontent.com/77416319/135196375-06459d76-db6d-45c4-bb4b-4b4cf57cf376.png)



