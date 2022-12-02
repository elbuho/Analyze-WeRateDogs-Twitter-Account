## Introduction
The target with this project is to Gather Data for diference sources, Cleaning, Analyzing and visualizing the data.
Real-world data rarely comes clean. We have used Python and its libraries, and we got data from a variety of sources and in a variety of formats, assess its quality and tidiness, then cleaned it. 

The dataset that we have  wrangled (analyzing and visualizing) is the tweet archive of Twitter user [@dog\_rates](https://twitter.com/dog_rates), also known as [WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "[they're good dogs Brent](http://knowyourmeme.com/memes/theyre-good-dogs-brent)." WeRateDogs has over 4 million followers and has received international media coverage.

WeRateDogs [downloaded their Twitter archive](https://support.twitter.com/articles/20170160) and sent it to Udacity via email exclusively for use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017. More on this soon.


## Project Steps Overview

The tasks in this project are as follows:

Step 1: Gathering data

Step 2: Assessing data

Step 3: Cleaning data

Step 4: Storing data

Step 5: Analyzing, and visualizing data

Step 6: Reporting

* Data wrangling efforts
* Data analyses and visualizations



### The Data

In this project, you will work on the following three datasets.

**Enhanced Twitter Archive**

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, It has filtered for tweets with ratings only (there are 2356).

#### Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. It's posible to query Twitter's API to gather this valuable data.

#### Image Predictions File

The data have  a table full of image predictions classify breeds of dogs(the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

### The tweet image predictions

This file (`image_predictions.tsv`) is present in each tweet according to a neural network. It is hosted on Udacity's servers and should be downloaded programmatically using the [Requests](https://pypi.org/project/requests/) library and the following URL: [https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad\_image-predictions/image-predictions.tsv](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)

### Additional data from the Twitter API

Gather **each tweet's retweet count** and **favorite ("like") count** at the minimum and any additional data you find interesting. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's [Tweepy](http://www.tweepy.org/) library and store each tweet's entire set of JSON data in a file called `tweet_json.txt` file.

Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) **tweet ID, retweet count, and favorite count**. _Note: do not include your Twitter API keys, secrets, and tokens in your project submission._

## Step 2: Assessing Data

After gathering all three pieces of data, assess them visually and programmatically for quality and tidiness issues. We had to detect and document at least **eight (8) quality issues** and **two (2) tidiness issues** in the "Accessing Data" section in the `wrangle_act.ipynb` Jupyter Notebook.

We needed to use two types of assessment:

-   **Visual assessment:** each piece of gathered data is displayed in the Jupyter Notebook for visual assessment purposes. Once displayed, data can additionally be assessed in an external application (e.g. Excel, text editor).
-   **Programmatic assessment:** pandas' functions and/or methods are used to assess the data.

To meet specifications, the following issues must be assessed.

-   We only wanted original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings and some are retweets.
-   Assessing and cleaning the entire dataset completely would require a lot of time, and is not necessary to practice and demonstrate skills in data wrangling. Therefore, the requirements of this project are only to assess and clean at least 8 quality issues and at least 2 tidiness issues in this dataset.
-   The fact that the rating numerators are greater than the denominators does not need to be cleaned. This [unique rating system](http://knowyourmeme.com/memes/theyre-good-dogs-brent) is a big part of the popularity of WeRateDogs.
-   We didn't need to gather the tweets beyond August 1st, 2017. 

## Step3: Cleaning, Analyzing, and visualizing data
All the Cleaning, analyzing and visualization data process it can be follow in the notebook  wrangle_act.ipynb and we added a wrangle Report (wrangle_report.pdf) with all issues that we found in the data with the descriptión of qualyty and tidiness as weel all the steps to clean the data.

## Step4: Reporting
There is a report (act_report.pdf) as a summary with the most important characteristics that we found in the data.


