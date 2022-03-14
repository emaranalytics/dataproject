## OVERVIEW

In this project, we're gonna predict the auction sale price for a piece of heavy equipment to create a "blue book" for bulldozers. The project is inspired by kaggle competition which we have to find out: 
<blockquote>how well can we predict the future sale price of a bulldozer, given its characteristics and previous examples of how much similar bulldozers have been sold for?</blockquote>

![image](https://user-images.githubusercontent.com/66315773/158114235-e5c24d59-5727-45b1-8007-a421f1be7f05.png)

## PROJECT'S KEY CONCEPTS

#### 1. Data
The data is downloaded from the Kaggle Bluebook for Bulldozers competition: https://www.kaggle.com/c/bluebook-for-bulldozers/data

There are 3 main datasets:

* `Train.csv` is the training set, which contains data through the end of 2011.
* `Valid.csv` is the validation set, which contains data from January 1, 2012 - April 30, 2012 You make predictions on this set throughout the majority of the competition. Your score on this set is used to create the public leaderboard.
* `Test.csv` is the test set, which won't be released until the last week of the competition. It contains data from May 1, 2012 - November 2012. Your score on the test set determines your final rank for the competition.

#### 2. Evaluation
The evaluation metric for this competition is the RMSLE (root mean squared log error) between the actual and predicted auction prices.
For more on the evaluation of this project check: https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation

**Note:** The goal for most regression evaluation metrics is to minimize the error. For example, our goal for this project will be to build a machine learning model which minimises RMSLE.

#### 3. Features
Kaggle provides a data dictionary detailing all of the features of the dataset. You can view this data dictionary on Google Sheets: https://docs.google.com/spreadsheets/d/18ly-bLR8sbDJLITkWG7ozKm8l3RyieQ2Fpgix-beSYI/edit?usp=sharing

#### 4. Explanatory Data Analysis
![image](https://user-images.githubusercontent.com/66315773/158114950-52d0a062-2783-405d-9957-362d05da31dd.png)

#### 5. Data Preprocesing
![image](https://user-images.githubusercontent.com/66315773/158115232-850285dd-4640-4bc6-8c69-eaa407789582.png)

#### 6. Modelling
![image](https://user-images.githubusercontent.com/66315773/158115411-eb91fb0a-c8d1-478c-9fbd-067e9ca0b689.png)

#### 7. Splitting Data Into Train/Validation Sets
![image](https://user-images.githubusercontent.com/66315773/158115568-d3026979-b6f8-4a4f-9dc2-d9a7a8d0a067.png)

#### 8. Building An evaluation Function
![image](https://user-images.githubusercontent.com/66315773/158115667-19f82c6b-9178-437a-bc07-400b840ef3dc.png)

#### 9. Tuning Hyperparameters
![image](https://user-images.githubusercontent.com/66315773/158115790-8db87261-58b6-482c-ac03-6aad1cf0d611.png)

#### 10. Train A Model With The Best Hyperparamters
![image](https://user-images.githubusercontent.com/66315773/158115903-cebfd52b-099e-4660-928b-9fd7bcb2b488.png)

#### 11. Make Predictions On Test Data
![image](https://user-images.githubusercontent.com/66315773/158116026-4e75fdf1-9ecb-4b9d-814d-b51f10da0a55.png)

#### 12. Feature Importance
![image](https://user-images.githubusercontent.com/66315773/158116097-4c48da40-5bd6-4c56-9f50-971c5ccdeadc.png)






