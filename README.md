# ps239T-final-project

Project Read Me - Jennifer Frehn

## Short Description

Give a short, 1-2 paragraph description of your project. Focus on the code, not the theoretical / substantive / academic side of things. 

For this project, I use Twitter's API to collect and examine social media data. My main interest was in producing descriptive analysis of the differences in responses to tweets by male and female U.S. senators. 

Most of my data visualizations and analyses are within the scope of traditional sentiment analysis, but Facebook's reactions feature allows me to scrape and visualize reactions data as well. Although Facebook reactions are certainly not a direct match for sentiment analysis, these reactions provide some analytical leverage--especially in the post-election season as we grapple with how the public perceived each candidate, and how different strategic decisions, thematic appeals, and thematic campaign platforms contributed to the election results.

My Twitterscrape R code allowed me to track daily sentiment fluctuations toward each candidate on Twitter for the two weeks leading up to the election. Each day, I would collect the latest 4,000 tweets aimed at each candidate, and plot the sentiment outcome (-3 to 3) on a simple plot. The opinion lexicon I used to distinguish the sentiment of different words can be found at:

## Dependencies

The software my code depends on and version numbers:

1. R, version 3.4.3
2. R Studio, Version 1.1.414


## Files

This provides a list of all files contained in the repo, along with a brief description of each one:

### Data

1. RSD files of of original tweets collected: The below RSD files contain the data collected from the first and second round of tweet gathering through Twitter's API. Each represents tweets that were sent in response to tweets from the senators. Each dataset contains five variables: 1) *created_at*: the date and timestamp of the tweet, 2) *screen_name*: the screen name of the tweet author, 3) *text*: the text of the tweet, 4) *reply_to_screen_name*: the twitter handle for the person the tweet was sent as a reply to, and 5) *plaintext*: the text of the tweet in plain text. 
    - bs_to_df1.rds - Tweets sent in response to tweets by @BernieSanders (round 1)
    - ew_to_df1.rds - Tweets sent in response to tweets by @SenWarren (round 1)
    - cb_to_df1.rds - Tweets sent in response to tweets by @CoryBooker (round 1)
    - kh_to_df1.rds - Tweets sent in response to tweets by @KamalaHarris (round 1)
    - cs_to_df1.rds - Tweets sent in response to tweets by @SenSchumer (round 1)
    - kg_to_df1.rds - Tweets sent in response to tweets by @SenGillibrand (round 1)
    - bs_to_df2.rds - Tweets sent in response to tweets by @BernieSanders (round 2)
    - ew_to_df2.rds - Tweets sent in response to tweets by @SenWarren (round 2)
    - cb_to_df2.rds - Tweets sent in response to tweets by @CoryBooker (round 2)
    - kh_to_df2.rds - Tweets sent in response to tweets by @KamalaHarris (round 2)
    - cs_to_df2.rds - Tweets sent in response to tweets by @SenSchumer (round 2)
    - kg_to_df2.rds - Tweets sent in response to tweets by @SenGillibrand (round 2)


2. CSV files of cleaned and combined tweets: The below CSV files combine cleaned and combined data for the files described above. There is one additional variable, *newplaintext*, which has the same text as the *plaintext* variable, but has removed the first word from every tweet, which in this case is the twitter handle of the tweet subject (ie, "@BernieSanders" for tweets sent to Bernie Sanders). Additionally, these datasets removed repetitive tweets that came from a tweet advocacy blast campaign.   
    - all_f.csv: Combined file for females. Contains tweets from round 1 and 2 for @SenWarren, @KamalaHarris and @SenGillibrand. 
    - all_m.csv: Combined file for males. Contains tweets from round 1 and 2 for @BernieSanders, @CoryBooker and @SenSchumer.  

3. Rdata files for structural topic models: The below Rdata files are the saved models for structural topic modeling. Each has 15 topics and was run to convergence. 
    - stm15_f.Rdata: Structural topic model for tweets sent to female senators
    - stm15_m.Rdata: Structural topic model for tweets sent to male senators


### Code

1. 01_collect-nyt.py: Collects data from New York Times API and exports data to the file nyt.csv
2. 02_merge-data.R: Loads, cleans, and merges the raw Polity and NYT datasets into the Analysis Dataset.
2. 03_analysis.R: Conducts descriptive analysis of the data, producing the tables and visualizations found in the Results directory.

### Results

1. coverage-over-time.jpeg: Graphs the number of articles about each region over time.
2. regression-table.txt: Summarizes the results of OLS regression, modelling *nyt* on a number of covariates.

## More Information

Include any other details you think your user might need to reproduce your results. You may also include other information such as your contact information, credits, etc.
