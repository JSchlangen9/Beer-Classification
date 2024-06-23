# DTSA 5509: Beer ML Project

## Project Overview

For this project, I will be analyzing the public Beer Profile Ratings Data Set from Kaggle (linked below). The goal of this project will be to create a classification model that accurately predicts the type/style of beer based on  some of its characteristics. My intial thought is to utilize a Decision Tree Classifer or an Ensemble/Random Forrest model; however; I will test additional models as needed depednding upon accuracy.


## Beer Profile Ratings Data Set

As previosly mentioned, the dataset for this project was found from Kaggle and includes a variety of attributes about various beers. In ther dataset, there are roughly 3200 beers included, and some key featurs of the beers are: Style, ABV, Alcohol, Taste, and Flavor. After cleaning, I expect to use 'Style' as the response, and there will be 19 predictors that can be tested/used in the model.

Beer profile and ratings data set. Kaggle. (2021, November 18). https://www.kaggle.com/datasets/ruthgn/beer-profile-and-ratings-data-set/data

## Data Cleaning

Initial data cleaning will consist of removing unneeded columns and searching for null/missing/incorrect values in attribute columns. Columns that are not needed for the column include items such as 'Description' and 'Brewery'. Individual samples appear to be clean, and there were not any null values in the dataset. Records with a 'Max IBU' value equal to 0 were removed, because this most likely corresponds to a null value in that sample. This resulted in removing 100 records from the dataset.

Additionally, I manually reclassified the beers to broader categories for purposes of the classification model that I am trying to build. For example, I am not interested in classifying a beer as a 'Mexican Lager', but I am interested in correctly classifying the beer as a 'Lager'. After reclassifying beers into 10 common categories, another 589 records were removed from the dataset, resulting in 2,480 records remaining.

A challenge that I discovered during the data cleaning process was the presence of values equalling 0 that were completely legitimate. In many datasets, records with a 0 value can be excluded because they are either incorrect or highly improbable. With that said, due to the range of beer styles, many of these values could legitimately be 0, and that poses a risk to the validity of the analysis.

## Exploratory Data Analysis

As shown by the violin plot,

## Model Testing & Selection

## Results & Conclusion