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

### Decision Tree(click on image to enlarge):

![image](https://user-images.githubusercontent.com/77416319/135375174-d33581df-a916-467f-8f12-f58f9079a47c.png)

### XG Boost(click on image to enlarge):

![image](https://user-images.githubusercontent.com/77416319/135375231-a7909f6b-8da8-43b6-9e78-11fdf2e71d75.png)

The results show that Shot Distance was the most important feature when determining the outcome of a shot attempt for each model. 

## Final Model:

For the two initial models that had the highest accuracy, I used GridSearch to conduct hyperparameter tuning for each model. XG Boost performed the best, with a max depth of 6. Below are the results:

Grid Search found the following optimal parameters: 
learning_rate: 0.1
max_depth: 6
min_child_weight: 1
n_estimators: 100
subsample: 0.7

Training Accuracy: 68.95%
Validation accuracy: 68.95%

![image](https://user-images.githubusercontent.com/77416319/135382487-c2de19c1-ae09-403a-8d5f-ca39325919de.png)

              precision    recall  f1-score   support

           0       0.67      0.86      0.75      7936
           1       0.76      0.53      0.62      6913

    accuracy                           0.70     14849
   macro avg       0.72      0.69      0.69     14849
weighted avg       0.72      0.70      0.69     14849

              precision    recall  f1-score   support

           0       0.60      0.76      0.67      2037
           1       0.57      0.40      0.47      1676

    accuracy                           0.59      3713
   macro avg       0.59      0.58      0.57      3713
weighted avg       0.59      0.59      0.58      3713

My final model has a training accuracy rate of 70%, while its testing accuracy rate is 59%. The feature importances of the final model indicates once again that shot distance will best determine the outcome of a shot(click on image below to enlarge):

![image](https://user-images.githubusercontent.com/77416319/135382827-8dab3c20-ae97-45d0-8c7f-786c65c9db09.png)

Based on the results from the models that were run, I decided to explore further the relationship between shot distance and shot result:

![image](https://user-images.githubusercontent.com/77416319/135382997-80b19e71-c9c0-458e-af54-2a019a548036.png)

As the image above illustrates, the highest rate of made shots were within about 5 feet of the basket, while the highest rate of missed shots were within about 25 feet. In addition, the highest frequency of attempts were also within 5 feet and 25 feet, with the number of attempts within 25 feet the highest.

## Player Shooting Percentage Breakdown

For the 20 players used in the models, I created a bar plot of percentages of made and missed shots for each player:

![image](https://user-images.githubusercontent.com/77416319/135565357-1295b77e-9198-42df-b2c8-6c5964068c85.png)

Below are the shot distance distribution of 5 players with the highest percentages of made shots:

## Chris Paul

![image](https://user-images.githubusercontent.com/77416319/135569248-b8576603-8712-42aa-84e6-831ab1fdf8df.png)

## Stephen Curry

![image](https://user-images.githubusercontent.com/77416319/135569295-bf9a1b33-459c-416c-a1f7-78871a4d1af6.png)

## Lebron James

![image](https://user-images.githubusercontent.com/77416319/135569326-db17828e-1d00-4fcd-ac1b-8ba8797cd5a9.png)

## Anthony Davis

![image](https://user-images.githubusercontent.com/77416319/135569660-300da5fb-1f10-4fa3-835a-7daccf2e1911.png)

## Nikola Vucevic

![image](https://user-images.githubusercontent.com/77416319/135569698-ac4b989e-2f1b-46df-9753-aa4f9e998816.png)

