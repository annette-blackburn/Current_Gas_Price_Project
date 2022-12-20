# **Gasoline Price Predictor**
## Machine Learning (see gas_oil_LR_twitter_NLP.py)

### Linear Regression (see gas_oil_ML.ipynb)
Two linear regression models were created: one to predict __regular gas prices from crude oil prices__ and the other to predict __diesel prices from crude oil prices__. 


#### Description of Preliminary Data Preprocessing
Starting with historical crude oil data (1983 to 2021) and historical gas and diesel price data (1995 to 2021), the data are cleaned to fit into a linear regression machine learning model and loaded into two dataframes (hist_crude_df and hist_gas_df).
The cleaned gas price dataframe includes all formulations of retail gasoline and diesel prices in a MM/DD/YYYY format with samples from each month starting in January 1995 to January 2021. The cleaned crude oil dataframe is in the same format as the cleaned gas price dataframe: MM/DD/YYYY format with monthly samples from January 1995 to January 2021.
Using current crude oil data (February 2021 to December 2022) and current gas and diesel price data (January 2021 to December 2022), the data are cleaned to line up with the historical dataframes' formatting. The data are loaded into two dataframes (current_crude_df and current_gas_df). Once the four dataframes (historical and current and crude oil and gas) were accurately cleaned, the data were loaded into two dataframes (gas_df and crude_df).

#### Description of Preliminary Feature Engineering and Preliminary Feature Selection
To fit a linear regression model with historical and current crude oil and gas price data (and then fit a model with historical and current crude oil and diesel price data) to establish and explore relationships between the data. 

#### Explanation of Model Choice, including Limitations and Benefits 
This linear regression model is the best model because historically, crude oil prices and gas prices have a linear relationship, so there is no need to complicate the relationship with other, more complex models.

#### Train, Test, Split Description 
The data are split into 80% training and 20% testing.

#### Explanation of Changes in Model Choice 
Not applicable.

#### Description of How the Model Has Been Trained Thus Far and Any Additional Training
After adding AAA current gas price data and MarketWatch's current crude oil prices and data cleaning, this model now includes a function that takes in current gas prices (into the existing linear regression model with past gas prices) and predicts future gas prices.

#### Description of Current Accuracy Score
The current accuracy score is 0.0906 with the current gas and crude oil prices included. Previously, the model's accuracy score was 0.903 (after taking in current gas prices), and before, with just historical crude and gas prices, the accuracy was 0.873). The r-squared for the regular gas model prediction from training data is 0.907 and the r-squared from testing data is 0.873. The r-squared for the diesel model prediction from training data is 0.864 and the r-squared from testing data is 0.821.

Since confusion matrices cannot be done on regressors, neither of these models have them. 

#### How the Model Addresses the Question/Problem the Team is Solving 
This linear regression model will predict both future gas and diesel prices in order to help American customers make more informed decisions about their gas consumption.


### Natural Language Processsing (Sentiment Analysis) (see twitter_NLP.ipynb)

#### Description of Preliminary Data Preprocessing
Using tweets from November 24, 2022 to December 5, 2022, the data are cleaned and subjectivity and polarity score columns are included.

#### Description of Preliminary Feature Engineering and Preliminary Feature Selection
To use natural language processing to characterize the sentiment of current tweets on gas prices (positive, neutral, or negative sentiment, ranging from -1.0 to 1.0).

### Explanation of Model Choice, including Limitations and Benefits

This sentiment analysis NLP model provides a sentiment score for those who tweeted about gas and oil from November 24, 2022 to December 5, 2022. To understand the sentiment of current consumers, current data would need to be added. To include this sentiment analysis in the linear regression machine learning model, we would need more data, organized by month. Due to the limitations of the data and the data preprocessing of the linear regression model, there are only gas and diesel prices by month from January 1995 to January 2021 and February 2022 to December 2022. As a result, adding this sentiment analysis to the other model would only be adding two data points: November and December 2022 tweets.

### Train, Test, Split Description
Since the tweet data are limited to November and December, they cannot be meaningfully added to the linear regression model, so there is no training set or testing set.

### Explanation of Changes in Model Choice & Description of How the Model Has Been Trained Thus Far and Any Additional Training

Based on the formatting of the tweets and gas prices, the model went from attempting to predict current sentiment of gas prices to characterizing the sentiment from the last week in November to the first week in December.

### Description of Current Accuracy Score
Not applicable.

### How the Model Addresses the Question/Problem the Team is Solving

This sentiment analysis natural language processing model will compliment the linear regression model by showcasing general sentiment about current gas prices from tweets.