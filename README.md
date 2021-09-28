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
* Bagged Tree
* Random Forest
* XG Boost

Among the initial models, Decision Tree and XG Boost performed the best:

## Decision Tree:

![image](https://user-images.githubusercontent.com/77416319/135018466-58bf27cd-4dc9-4ae6-a052-51e24fe789bb.png)



