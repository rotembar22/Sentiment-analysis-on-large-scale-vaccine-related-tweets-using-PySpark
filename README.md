# Sentiment analysis on large-scale vaccine-related tweets using PySpark

![Seer Logo](https://cdn.stackblogger.com/wp-content/uploads/2019/08/twitter-api.jpg)

## Quick Links

  - [Overview](#overview)
  - [Data Collection](#data-collection)
  - [Preprocess](#preprocess)
  - [Sentiment Score](#sentiment-score)
  - [Code Implementation](#code-implementation)  
  - [Analysis Results](#analysis-results)


# Overview

This project aims to present sentiment analysis on vaccines-related tweets collected by Twitter API V2 with academic research access. Firstly, I collected about one million tweets in the period starting when COVID19 spread out up to the end of 2020. Since the task was performed on a large-scale dataset, I used Spark for programming data parallelism and google cloud platform (GCP) for cloud computing. 
The sentiment analysis was done using TextBlob, a library for NLP tasks. TextBlob uses a pre-trained model containing a dictionary, where each word is ranked with a semantic value. The result obtained is the average semantic value in each tweet.

Some of the inquiries that were extracted:
 - Average sentiment score for each day
 - Average sentiment score for each country
 - Sentiment score for positive/negative/natural label by day(avg)
 - Tweets count in each country
 - Tweets count by day(avg)
 - Likes count for positive/negative tweets
 - Average sentiment score for Moderna or Pfizer
 - Users analysis- how many user tweets, avg +std


# Data Collection

I wrote a step-by-step tutorial on creating an automated Twitter data collection script using academic research access. Here is the link for the medium post:

[Creating an Automated Twitter Data Collection Script using Academic Research Access (API V2)](https://medium.com/@rotem_bar/creating-an-automated-twitter-data-collection-script-using-academic-research-access-api-v2-aaacb419e123 "Creating an Automated Twitter Data Collection Script using Academic Research Access (API V2)")

I wrote a step-by-step tutorial on creating an automated Twitter data collection script using academic research access. Here is the link for the medium post:

**Details about the collected data:**

Twitter API: Academic research URL
  * Up to 10M tweets for each mount
  * 500 tweets for each request
  * 50 requests / 15 minutes


Fields: 
- tweet
- author id
- created at
- geo


Location: USA
Time range: 20/03/2021- 31/12/2021
Key words: vaccines, vaccine, vaccination, Vaccinated, pfizer, Moderna

Total tweets collected: 730K

# Preprocess

Here is the text preprosess I made, 
1. Remove non ASCII characters (remove emoji)
2. Fixed abbreviation such as:
      * thats -> that is
      * im -> I am
      * wth - > what the hell
      * wont -> will not
3. Convert to lowercase
4. Remove hyperlinks
5. Remove @mentions
6. Remove punctuation
7. Remove numeric 'words’
8. Remove non a-z 0-9 characters and words shorter than 1 characters


# Sentiment Score

There are several techniques how to evaluate to address the sentiment analysis task. The most straightforward is using a dictionary that ranks each word with the level of sentiment. There are several tool kits that use this kind of dictionary, so I decided to use TextBlob.  TextBlob uses the popular NLTK library, while the input contains a single sentence, and the output is polarity and subjectivity. The polarity score lies between (-1 to 1), where -1 identifies the most negative words such as ‘disgusting’, ‘awful’, and ‘pathetic’, and 1 identifies the most positive words like ‘excellent’, and ‘best’. 

Therefore I defined the “sentiment label” as follows:
<br>	* Negative : [-1, -0.1]
<br>	* Natural : [-0.1, 0.1]
<br>	* Positive : [-0.1, 1]
  
  


# Code Implementation

[Jupyter notebook](https://github.com/rotembaruch/Product-Recommendation-System/blob/main/Product%20Recommendation%20System.ipynb "Jupyter notebook")

# Analysis Results



