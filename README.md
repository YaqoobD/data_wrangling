## Introduction

Real-world data rarely comes clean. Using Python and its libraries, you will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. You will document your wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL.

The dataset that you will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for you to use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017. More on this soon.
![Screenshot 2022-04-30 at 18 09 43](https://user-images.githubusercontent.com/52135942/166113345-b45411ad-8df6-442a-8157-93ca0da7015a.png)

## Data Wrangling
The data wrangling project was very challenging, and I learned a lot about the data gathering process and the Twitter API.

## Data Gathering
I gathered data from three different sources for this data analysis. WeRateDogs gave Udacity exclusive access to their Twitter archive for this project in the form of a csv file.

The tweet image predictions, i.e., what breed of dog (or another object, animal, etc.) is present in each tweet. This file (image_predictions.tsv) is hosted on Udacity's servers and should be downloaded programmatically using the Requests library and the following URL:
https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_imagepredictions/image-predictions.tsv.

This archive contains basic tweet data (tweet ID, timestamp, text, etc.) . I queried the Twitter API for each tweet's JSON data using the Python’s Tweepy library I stored each tweet’s entire set of JSON data, which I would later use to analyze the tweet’s retweet and favorite (i.e. “like”) counts.

## Data Assessing:

The data assessing was divided into two-part Quality and Tidiness Issues.

### Quality Issues:

As I have investigated the dataset I have fine lots of quality issues, that I must correct before
making our analysis and visualization.

• As per the project requirements; only original ratings (no retweets) that have images should be included.
• Columns of retweeted_status_id and its related data have entries which not part of our analysis.
• Inaccurate data in name 'a' represented 55 times.
• Inaccurate data in rating_nominator and df_denominator.
• Null values reprsened as "None" in columns doggo, floofer, pupper, puppo.
• Invalid dtype in timestamp represented as object type.
• Column tweet_id represented as int64 across all data set.
• Columns of predictions have lables represented as letters.
• Column 'p1_dog' have 543 false prediction, p2_dog have 522 false prediction, p3_dog have 576 false prediction.
• Column 'p1' have invalid data like(china_cabinet, shield, orange, walking_stick,...etc).
• Column 'p2' have invalid data like(ice_lolly, Japanese_spaniel, china_cabinet,necklace,...etc).
• Column 'p3' have invalid data like(kimono, cab, axolotl, passenger_car, tripod,grocery_store,...etc).

### Tidiness Issues:
• Tidiness issue that had been taken care of were as follows:
• Variable dog stages have four columns. df_2:
• Variable prediction have three columns. df_3:
• Table df3_clean have same observation unit that in df1_clean.
• Column name id in stead of tweet_i.

## Data Cleaning

All cleaning was done programmatically, firstly I have made copies from the data frames to keep our original dataset unmodified. After each issue was defined, solution was coded and tested, and then data was stored as requested in a file name twitter_achive_master.csv and then I have taken all the insights using python pandas library and for the viz I have used
matplotlib.
