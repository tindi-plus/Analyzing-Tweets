# Analyzing-Tweets
<img src="https://cdn.pixabay.com/photo/2015/01/02/20/14/smartphone-586944_1280.jpg">

## Introduction
This is a program for analyzing tweets to form opinions about the stock market. A user can specify the stock to analyze and the program will mine data from Twitter about the stock. The program will analyze the data mined and determine if it is a good time to buy the stock or not. 

## Installations
This program requires the tweepy library which is a python library for accessing Twitter API. Tweepy can be installed using the following command on a windows terminal: ***pip install tweepy***. Pip will get the library from Pypi and install it for you. Tweepy is a robust python library for accessing Twitter API. You can read more about tweepy [here](https://pypi.org/project/tweepy/). Preprocessor is used to clean tweets. Preprocessor is a library for processing files in python. It can handle a lot of file sizes. To install preprocessor, run the follwing command on your windows command prompt: ***pip install preprocessor***. To learn more about the preprocessor project, visit [pypi](https://pypi.org/project/preprocessor/). TextBlob is a python natural language proccessing library. Install it with: ***pip isntall textblob***. Learn more about textblob [here](https://pypi.org/project/textblob/).
The module keys.py contains only the Twitter API keys which are obtained when you register on developers.twitter.com. 

## Description
Analyzing-tweets is a program that mines twitter for data about a stock and does anlysis on the data to determine if the it is a good time to buy the stock or not. It uses sentiment analysis to determine if the public's view of the company is currently positive or negative. If the sentiment is positive, it recommends buying, however, when the sentiment is negative, it does not recommend buying. The sequence of steps to achieve this feat is as follows:
* Authenticate with Twitter API and create a Twitter API object which will be required each time you acesss Twitter.
* Create a search query using the cursor object. The seach query specifies the company you would like to mine data about. 
* Extract the tweet texts from all the tweets that are mined. 
* Clean the tweet texts using preprocessor.
* Pass on the cleaned tweet text to textblob for further processing
* Textblob is a NLP library capable of doing sentiment analysis on text. Its sentiment method evaluates the sentiment of the text and returns a sentiment object with a polarity that ranges from +1 to -1. Polarities greater than 0 are positive while polarities lower than 0 are negative. A dictionary keeps count of positive tweets and negative tweets. 
* If the number of negative tweets is greater than the number of positive tweets, the stock is not recommended, and if the number of positive tweets is greater than the number of negative tweets, the stock is recommended. 
