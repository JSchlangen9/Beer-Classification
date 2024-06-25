# DTSA 5509: Beer ML Project

## Project Overview

For this project, I will be analyzing the public Beer Profile Ratings Data Set from Kaggle (linked below). The goal of this project will be to create a classification model that accurately predicts the type/style of beer based on  some of its characteristics. My intial thought is to utilize an Ensemble/Random Forest model or a Support Vector Classifier; however, I will test additional models as needed depending upon accuracy.


## Beer Profile Ratings Data Set

As previosly mentioned, the dataset for this project was found from Kaggle and includes a variety of attributes about various beers. In the dataset, there are roughly 3200 beers included, and some key features of the beers are: Style, ABV, Alcohol, Taste, and Flavor. After cleaning, I expect to use 'Style' as the response, and there will be 19 predictors that can be tested/used in the model.

Beer profile and ratings data set. Kaggle. (2021, November 18). https://www.kaggle.com/datasets/ruthgn/beer-profile-and-ratings-data-set/data

## Data Cleaning

Initial data cleaning will consist of removing unneeded columns and searching for null/missing/incorrect values in attribute columns. Columns that are not needed for the column include items such as 'Description' and 'Brewery'. Individual samples appear to be clean, and there were not any null values in the dataset. Records with a 'Max IBU' value equal to 0 were removed, because this most likely corresponds to a null value in that sample. This resulted in removing 100 records from the dataset.

Additionally, I manually reclassified the beers to broader categories for purposes of the classification model that I am trying to build. For example, I am not interested in classifying a beer as a 'Mexican Lager', but I am interested in correctly classifying the beer as a 'Lager'. After reclassifying beers into 10 common categories, another 589 records were removed from the dataset, resulting in 2,480 records remaining.

A challenge that I discovered during the data cleaning process was the presence of values equalling 0 that were completely legitimate. In many datasets, records with a 0 value can be excluded because they are either incorrect or highly improbable. With that said, due to the range of beer styles, many of these values could legitimately be 0, and that poses a risk to the validity of the analysis.

## Exploratory Data Analysis

As shown by the violin plot, the flavor attributes largely appear to be normally distributed; however there are long tails in the positive direction for certain attributes. For example, the 'Sour' attribute has a large positive tail due to the fact that this is a 'Style' of beer, as well as the 'Bitter' attribute which tends to be associated with IPA's and other flavorful beers.

After analyzing the review attributes, these do not appear to be helpful in the classification of the style of a beer. Review scores are largely independent of the style of beer, and therefore, these predictors are more likely to confuse the model. As a result, they will be removed from the pool of predictors that will be used to classify the beers.

According to the correlation heatmaps, I observed some strong correlations which make sense given domain knowledge. For example, there is a strong correlation between 'Body' and 'Malty' attributes, as well as 'Bitter' and 'Hoppy' attributes. This is exciting to see because hops tend to give beer a bitter flavor, and body/malty traits are somewhat synonymous as well.

## Model Testing & Selection

I initially tested base models using the support vector classifier and random forest packages without adjusting hyperparameters. By doing this, I quickly identified that the random forest model was better suited for the task at hand, and proceeded to diving deeper into the random forest model.

Through testing and iteration, I adjusted the hyperparameters for number of estimators, and the number of features to be included in the model. By doing this, I observed an average 2% increase in the performance of the model, and the random forest model is roughly 85% accurate.

As shown in the feature importance plot, the 3 most important features in the model are 'Min IBU', 'Max IBU', and 'Body'. This ties back to observations from the exploratory data analysis, as well as my domain knowledge. International Bitterness Unit (IBU) is largely a measure of a beer's hoppiness/bitterness, and Body is one of the strongest defining characteristics of a beer's taste/profile. 

## Results & Conclusion

In terms of results, I am very satisified with the random forest classification model that I built, and the scores/metrics calculated are in agreement with that claim. Accuracy topped out at roughly 85%, while completeness and homegeneity scores were 73% and 72% respectively. The lower completeness and homegeneity scores tell me that beer styles tend to exist on a spectrum, and that the lines between categories are often blurred. For these reasons, a classification model with 10 different choices and 85% accuracy is incredible.

The display of the confusion matrix shows 2 things clearly: Ale/Lager are the most popular types of beer in the dataset, and Bock is the most incorrectly classified style of beer. The model did quite well at distinguishing Ales and Lagers; however, it struggled with the Bock style which can often be described as similar to an Ale or a dark Lager. Again, the accuracy score will show this case as an incorrect prediction, when in the real world it could be considered subjectively correct.

For future testing, I would find it valuable to narrow down the number of beer styles that a model would try to predict. As previously mentioned, the model that I built classified a beer into 1 of 10 categories, which is very difficult to do when beers exist on a spectrum of styles. A model could be built with higher accuracy if it only had to fit beers into a group of 5 or less categories.