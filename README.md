# Draft_Prediction_Project

https://deepzissou.github.io/Draft_Prediction_Project/

## Overview
The focus of this project was to use Python to develop Machine Learning Models that use historical NCAA player stats to predict if a player is likely to play Basketball professionally.

Player stats were gathered via web-scraping and amounted to approximately 109 thousand unique records.

Several different Machine Learning models were trained and tested using the gathered data, with a Random Forest Classifier Model showing the best results. 

[![webpagesample](/PNGs/bb_scrnsht.png)](https://kellnergp.github.io/Draft_Prediction_Project/)

## Tools Used

Python

BeautifulSoup

Scikit-learn

PostgreSQL

## Data Collection – Finding Big Data
Web-scraping code was used to scrape data from the site Sports Reference https://www.sports-reference.com/.  The code was specified to pull data for eleven key player stat parameters: 
* ### fgapg = Field goal attempts per game
* ### fgpct = Field goal percent
* ### fgpg = Field goals per game
* ### ftapg = Free throw attempts per game
* ### ftpct = Free throw percent
* ### ftpg = Free throws per game
* ### games = Total Games Played over the course of NCAA career
* ### height = Player height in inches
* ### pfpg = Personal fouls per game
* ### ptspg = Points per game
* ### sospg = Strength of schedule
* ### trbpg = Total rebounds per game

## Data Preprocessing
Data was prepared using postgres SQL and pandas.  An “is_pro” column was added to assign players with a known outcome of either 1 = played professionally or 0 = no professional statistics.  The height column was converted to centimeters and rows containing NAN values were dropped.  The dataframe was then randomly split into two dataframes “train” and “test”.

## Model Training
The “train” dataframe was used to train our model.  After assessing different models, the Random Forest Classifier model was chosen to train the data.  RFC allowed for multiple feature inputs to be utilized without reducing our accuracy.

## Model Test
The “test” dataset was used to test the predictability of our model.  The known outcomes and names were removed and the player stats were coded as the input.  The model was coded to predict the “is_pro” status.
#### See train_test_predict-gkmod.ipynb for full train and test coding.

## Results
The outputs of the model were combined with the known results into a dataframe and saved to the file randomForest_model_results.csv.
## Our model resulted with a 96.7% prediction accuracy.

