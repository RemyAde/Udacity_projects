# Wrangling Report

The wrangling efforts carried out include:
1. Data Gathering
2. Data Assessing
3. Data Cleaning

__Data Gathering Process:__
1. Gathering of the Udacity’s WeRateDogs twitter archive:
The process involved manually downloading the provided WeRateDogs twitter archive provided by Udacity via the link: [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv)
It contained useful information such as the tweet_id, tweet/text, dog stage, numerator and denominator rating. It was the easiest of all the gathering processes. The downloaded data was a csv document and so was passed directly into a pandas data frame using the pd.read_csv() method. The created data frame was named tweets_df.

2. Gathering of the twitter archive using API:
This process involved downloading the data programmatically using the `tweepy` library in python to access twitter’s API and download the entire archive containing only tweet_ids contained the previously downloaded data (tweets_df). This data contained all the columns in the previous archive as well as more useful information such as retweet_count and favorite_count.
The downloaded data was written into a tweet_json.txt file, since the data was of json type, each record was json dumped into a new line. The columns; created_at, id, retweet_count and favorite_count now made up a new pandas data frame using pd.read_json(). This data frame was called retweets_df.

3. Gathering of Image Predictions:
This process involved using python’s `request` library to download the image_prediction dataset from Udacity, the collected data was written into a Tab-Separated-File (tsv), a data frame was made from this data using pandas read_tsv() method and was named image_preds. The dataset can be gotten [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)

__Data Assessing Process:__
1. Assessing of tweets_df:
Both visual and programmatic inspection of this data were carried out.
The visual inspection showed flaws with the data such as stop words like a & the found in the dog’s name column, nulls represented as None in dog’s name column and nulls represented as None in doggo, floofer, pupper & puppo columns.
Programmatic inspection discovered issues such as pandas object datatype for timestamp column instead of datetime datatype, information about retweets found in the data frame and rating_denominator column had values less than 10 and some inaccurate values like 11.

2. Assessing image_preds:
Visual and Programmatic inspection yielded issues such as:
• Inconsistent alphabets case use in p1, p2 and p3 columns
• p1_dog, p2_dog and p3_dog all having values as False which means invalid dog image
• Only the highest value in either p1_conf or p2_conf or p3_conf with a dog value of True is required as a column. (All other p simply serve as noise)

3. Assessing of retweets_df:
Visual and Programmatic inspection were done. Issues observed were the mislabeled column name id instead of tweet_id and irrelevance of created_at column (same information is represented as timestamp in tweets_df)

__Cleaning Process:__
1. Cleaning of tweets_df:
This involved:
• Changing of timestamp column to datetime object
• Dropping off of retweet rows and columns
• Replacing of stop words in name column to NaN values
• Replacing of None values to NaN values in name column
• Replacing of None values to NaN values in doggo, floofer, pupper and puppo columns
• Replacing of inaccurate values to 10 in rating_denominator column
• Removing of redundant text column

2. Cleaning of retweets_df:
This involved:
• Renaming id column to tweet_id
• Dropping of created_at column

3. Cleaning of image_preds:
This involved:
• Using of small case for all p1, p2 & p3 values
• Dropping off of records which had all p1_dog, p2_dog & p3_dog values as False
• Making new column called dog_type to contain values of most confident dog prediction
• Dropping off of all p columns