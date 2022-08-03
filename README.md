# WeRate-Dogs
## Project Motivation
## Context
Your goal: wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. The Twitter archive is great, but it only contains very basic tweet information. Additional gathering, then assessing and cleaning is required for "Wow!"-worthy analyses and visualizations.

## The Data
In this project, you will work on the following three datasets.

## Enhanced Twitter Archive
The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, I have filtered for tweets with ratings only (there are 2356).

## Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But you, because you have the WeRateDogs Twitter archive and specifically the tweet IDs within it, can gather this data for all 5000+. And guess what? You're going to query Twitter's API to gather this valuable data.

## Image Predictions File

One more cool thing: I ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs*. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

## Step 1: Gathering Data
In this step, you will gather all three pieces of data as described below in the "Data Gathering" section in the wrangle_act.ipynb notebook.

**Note**: the methods required to gather each data are different.

## The WeRateDogs Twitter archive
I am giving this file to you, so imagine it as a file on hand.
Download this file manually by clicking the following link: <a href = "https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv">twitter_archive_enhanced.csv</a>. Once it is downloaded, upload it and read the data into a pandas DataFrame.

## The tweet image predictions
This file `(image_predictions.tsv)` is present in each tweet according to a neural network. It is hosted on Udacity's servers and should be downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv

## Additional data from the Twitter API
Gather each tweet's retweet count and favorite ("like") count at the minimum and any additional data you find interesting. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file.

Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count. Note: do not include your Twitter API keys, secrets, and tokens in your project submission

## Step 2: Assessing Data
After gathering all three pieces of data, assess them visually and programmatically for quality and tidiness issues. Detect and document at least eight (8) quality issues and two (2) tidiness issues in the "Accessing Data" section in the wrangle_act.ipynb Jupyter Notebook.

You need to use two types of assessment:

Visual assessment: each piece of gathered data is displayed in the Jupyter Notebook for visual assessment purposes. Once displayed, data can additionally be assessed in an external application (e.g. Excel, text editor).
Programmatic assessment: pandas' functions and/or methods are used to assess the data.
To meet specifications, the following issues must be assessed.

- You only want original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings and some are retweets.
- Assessing and cleaning the entire dataset completely would require a lot of time, and is not necessary to practice and demonstrate your skills in data wrangling. Therefore, the requirements of this project are only to assess and clean at least 8 quality issues and at least 2 tidiness issues in this dataset.
- The fact that the rating numerators are greater than the denominators does not need to be cleaned. This <a href = "http://knowyourmeme.com/memes/theyre-good-dogs-brent">unique rating system</a> is a big part of the popularity of WeRateDogs.
- You do not need to gather the tweets beyond August 1st, 2017. You can, but note that you won't be able to gather the image predictions for these tweets since you don't have access to the algorithm used.

## Step 3: Cleaning Data
Clean all of the issues you documented while assessing. Perform this cleaning in the "Cleaning Data" section in the `wrangle_act.ipynb`.

Make sure you complete the following items in this step.

- Before you perform the cleaning, you will make a copy of the original data.
- During cleaning, use the define-code-test framework and clearly document it.
- Cleaning includes merging individual pieces of data according to the rules of tidy data. The result should be a high-quality and tidy master pandas DataFrame (or DataFrames, if appropriate).

## Step 4: Storing Data
In the "Storing Data" section in the `wrangle_act.ipynb` notebook, store the cleaned master DataFrame in a CSV file with the main one named `twitter_archive_master.csv`. If additional files exist because multiple tables are required for tidiness, name these files appropriately. Additionally, you may store the cleaned data in a SQLite database (which is to be submitted as well if you do).

## Step 5: Analyzing and Visualizing Data
In the Analyzing and Visualizing Data section in your `wrangle_act.ipynb` Jupyter Notebook, analyze and visualize your wrangled data.

- You must produce at least **three (3) insights and one (1) visualization**.
- You must clearly document the piece of assessed and cleaned (if necessary) data used to make each analysis and visualization.

## Step 6: Reporting
Create a **300-600 word written report** called `wrangle_report.pdf` or `wrangle_report.html` that briefly describes your wrangling efforts. This is to be framed as an internal document.

Create a **250-word-minimum written report** called `act_report.pdf` or `act_report.html` that communicates all the insights and displays the visualization(s) produced from your wrangled data. This is to be framed as an external document, like a blog post or magazine article, for example.

Both of these documents can be created in separate Jupyter Notebooks using the <a href = "http://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html">Markdown functionality</a> of Jupyter Notebooks, then downloading those notebooks as PDF files or HTML files (see image below). If you want to write a report this way, there are two Jupyter Notebook files, named "wrangle_report" and "act_report" for you in the workspace. You might prefer to use a word processor like Google Docs or Microsoft Word, however.
