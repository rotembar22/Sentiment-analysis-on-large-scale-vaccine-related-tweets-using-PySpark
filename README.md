# Sentiment analysis on large-scale vaccine-related tweets using PySpark

![Seer Logo](https://cdn.stackblogger.com/wp-content/uploads/2019/08/twitter-api.jpg)


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
