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

According to the model, the training data had 100% accuracy, while the testing data had 54% accuracy, which indicates there is overfitting.

## XG Boost:

![image](https://user-images.githubusercontent.com/77416319/135196375-06459d76-db6d-45c4-bb4b-4b4cf57cf376.png)

              precision    recall  f1-score   support

           0       0.76      0.87      0.81      7936
           1       0.83      0.68      0.75      6913

    accuracy                           0.79     14849
   macro avg       0.79      0.78      0.78     14849
weighted avg       0.79      0.79      0.78     14849

              precision    recall  f1-score   support

           0       0.60      0.69      0.64      2037
           1       0.54      0.44      0.48      1676

    accuracy                           0.58      3713
   macro avg       0.57      0.57      0.56      3713
weighted avg       0.57      0.58      0.57      3713

As the results of the model show, the training data had 79% accuracy, while the testing data had 58% accuracy. While it recalled missed shots at a 69% rate, its recall rate for made shots was only 44%, meaning that there was a high rate of made baskets incorrectly labeled as missed shots in the testing data.  

## Feature Importances:

For the two models I selected, I created a function that ranked the importance of each feature used in the model:

### Decision Tree:



### XG Boost:

![image](https://user-images.githubusercontent.com/77416319/135374350-5d3575d5-75f9-49fd-98a3-0da295b6c34e.png)

The results show that Shot Distance was the most important feature when determining the outcome of a shot attempt.



