
### Data Wrangling and Analyze Project

> Data wrangling is an essential part of data analysis. It involves fetching a dataset, analyzing for errors in the dataset and cleaning the dataset. The goal of data wrangling is to make the dataset as accurate as possible for further analysis and reports.

In the "Wrangle and Analyze project", I utilize the three steps of data wrangling to analyze and clean the "WeRateDogs" dataset. The three steps of data wrangling:

 - Gathering
 - Assessing
 - Cleaning

#### Gathering

In the data gathering steps I downloaded the datasets from three different sources.

> The first dataset source "twitter_archive_enhanced" was downloaded manually from Udacity lesson resource page on the Data Analysis Nanodegree Track and read into the dataframe twitter_archive using the pd.read_csv statement. It contains tweet data for 5000+ tweets from WeRateDogs twitter page. This dataset is incomplete and does not have all the datas we need to fully understand the WeRateDogs datas.

> The second dataset was downloaded using the HTTP Requests library and read into the dataframe image_df. This dataset contains image predictions of the various dog breeds.

> The third dataset source "tweet_json.txt" was downloaded by querying Twitter and using Tweepy library and read line by line into the dataframe tweet_df. This dataset contains various information about the tweets of WeRateDogs such as the date each tweet was created, number of likes/favourite_count per tweets, number of retweets and many other useful information of the twitter page.

#### Assessing

After gathering the datas and storing into three separate dataframes. The dataframe was assessed and analyzed to learn about its properties: Number of columns, number of records, missing columns and rows, invalid datas and the datatypes of columns.

From my analysis if of the datasets several quality and tidiness issues was observed.
Quality Issues

On the twitter_archive dataframe, the following issues was observed:

 - Erroneous datatype(in_reply_to_user_id, in_reply_to_status_id, timestamp, rating_numerator, rating_denominator).
 - Retain original ratings(no retweet) that have images.
 - Remove columns not needed for analysis.
 - Some rating_numerator and rating_denominator values are invalid

On the image dataframe, the following issues was observed:

 - Some records has no image.
 - Multi name dog breed are separated with an underscore instead of spaces.
 - Non-uniform case in p names(some names begin with upper case others in lower case).

On the tweet dataframe, the following issue was observed:

 - Erroneous datatype(tweet_created).

#### Tidiness Issues

 - Four variables in Four columns(doggo, floofer, pupper, puppo)
 - tweet and image tables should be merge with the twitter archive table.

### Cleaning

Cleaning is the final step of the data wrangling process. It involves fixing both tidiness and quality issues observed in the assessed phase of the data wrangling process.

> The three datasets to be cleaned was first copied(into twitter_archive_clean, image_clean, tweet_clean) to preserved the original contents. The cleaning was segmented into three stage: Define, Code and Test.
Data tidiness Issues fixed

> The four variables splitted into four columns (doggo, floofer, pupper and puppo) was extracted from the text column on the twitter_archive_clean and rearranged into a new column in the twitter_archive_clean dataframe call dog_stage
The three dataframes twitter_archive__clean, image_clean and tweet_clean dataframe was merged into one dataframe twitter_archive_clean.

#### Data quality Issues fixed

 - The erroneous datatypes (tweet_created, timestamp, rating_numerator, rating_denominator, dog_stage) was converted into the correct datatypes
 - The original tweets was kept and the retweets was filtered out from the twitter_archive_clean dataframe.
 - Columns not needed for analysis was dropped.
 - Invalid data: The original ratings was extracted from the text and separated into rating_numerator and rating_denominator columns.
 - Records with no images was dropped.
 - Multiname separator underscore/hypen was replaced with space.
 - Dog breed name format was changed so each name in the column begins with an uppercase character.

### Save Data

> The clean dataset was saved in the dataframe twitter_archive_master.
