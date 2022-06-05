# Australian Elections Twitter Data Sentiment Analysis
 
## Table of Contents
- [Australian Elections Twitter Data Sentiment Analysis](#australian-elections-twitter-data-sentiment-analysis)
  - [Table of Contents](#table-of-contents)
  - [Project Description](#project-description)
  - [Data](#data)
  - [Data Exploration](#data-exploration)
  - [Training Sentiment Analyicer](#training-sentiment-analyicer)
  - [Preprocessing](#preprocessing)
  - [Data Analysis](#data-analysis)


## Project Description
**Big Goal:** Use tools in NLP, specifically sentiment analysis, to understand the 2019 Australian election. We train a model that predicts the sentiment on a given twitter. Using this model we label the Australian Election tweets as positive or negative. Using our prediction we attempt to predict the political affiliation on Twitter users based on how their sentiment evolved across time.


## Data
The data we will use can be found [here](https://www.kaggle.com/datasets/taniaj/australian-election-2019-tweets). In the link it describes the sources of the data. The [data](Data/auspol2019.csv) contains:
* **created_at**: Date and time of tweet creation
* **id**: Unique ID of the tweet
* **full_text**: Full tweet text
* **retweet_count**: Number of retweets
* **favorite_count**: Number of likes
* **user_id**: User ID of tweet creator
* **user_name**: Username of tweet creator
* **userscreenname**: Screen name of tweet creator
* **user_description**: Description on tweet creator's profile
* **user_location**: Location given on tweet creator's profile
* **usercreatedat**: Date the tweet creator joined Twitter

Additionally, there is a second [data file](Data/location_geocode.csv) containing geolocation information about the tweets.

## Data Exploration
The relevant notebook is [this](DataExploration.ipynb). We try to understand basic properties of the Australian Tweets data set and perform a first round of cleaning. We obtain [this](Data/CleanedData.csv) cleaned data set.

## Training Sentiment Analyicer
We train a sentiment text predictor. We use a [dataset](TrainingModel/Data/200-thousand-tweets.csv) containing +200 000 tweets labeled 'positive' (4) or 'negative' (0). In the [SentimentAnalyzer](TrainingModel/SentimentAnalyzer.ipynb)  we study different classification models and select the best performing sentiment classifier. After selecting the best performing model, we train the model with the entire data set and create sentiment labels for the Australian Election Tweets obtaining [this file](Data/our_labels.csv).

## Preprocessing
We prepare the data to be analyzed. We process the text of the tweets in different ways, we use stemming, tokenization, delete of special character, etc. We also normalize and organize other entries of the data so that we can analyze in an easier way later. 

## Data Analysis
In the [DataVisualization](DataVisualization.ipynb) and [DataVisualization_v2](DataVisualization_v2.ipynb) notebooks we study our results and attempt to predict different questions using the labels that we obtained from our sentiment analyzer model.


