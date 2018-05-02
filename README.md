# ps239T-final-project

## Description

For this project, I examined social media data. My main interest was in producing descriptive analysis of the differences in users' responses to tweets by male and female U.S. senators. First I used Twitter's API to collect tweets that were sent as replies to 6 senators (3 female and 3 male). I then preprocessed these tweets and conducted text analysis on them. First, I looked at simple frequencies as well as word associations between groups. Next, I conducted structural topic modeling and examined topic quality, topic proportions, topic correlation, and the effect of a covariate on a topic. I also created visualizations of the topics with word clouds and simple topic images. 


## Dependencies

The software my code depends on and version numbers:

1. R, version 3.4.3
2. R Studio, Version 1.1.414


## Files

This provides a list of all files contained in the repo, along with a brief description of each one:

### Data

1. **RSD files of of original tweets collected**: The below RSD files contain the data collected from the first and second round of tweet gathering through Twitter's API. Each represents tweets that were sent in response to tweets from the senators. Each dataset contains five variables: 1) *created_at*: the date and timestamp of the tweet, 2) *screen_name*: the screen name of the tweet author, 3) *text*: the text of the tweet, 4) *reply_to_screen_name*: the twitter handle for the person the tweet was sent as a reply to, and 5) *plaintext*: the text of the tweet in plain text. 
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


2. **CSV files of cleaned and combined tweets**: The below CSV files combine cleaned and combined data for the files described above. There is one additional variable, *newplaintext*, which has the same text as the *plaintext* variable, but has removed the first word from every tweet, which in this case is the twitter handle of the tweet subject (ie, "@BernieSanders" for tweets sent to Bernie Sanders). Additionally, these datasets removed repetitive tweets that came from a tweet advocacy blast campaign.   
    - all_f.csv: Combined file for females. Contains tweets from round 1 and 2 for @SenWarren, @KamalaHarris and @SenGillibrand. 
    - all_m.csv: Combined file for males. Contains tweets from round 1 and 2 for @BernieSanders, @CoryBooker and @SenSchumer.  

3. **Rdata files for structural topic models**: The below Rdata files are the saved models for structural topic modeling. Each has 15 topics and was run to convergence. 
    - stm15_f.Rdata: Structural topic model for tweets sent to female senators
    - stm15_m.Rdata: Structural topic model for tweets sent to male senators


### Code

1. 01_ScrapingTwitter.Rmd: Collects data from the Twitter API, cleans and merges the data, and exports the data to the files all_f.csv and all_m.csv. 
2. 02_Preprocessing_and_Analysis.Rmd: Loads, preprocesses and conducts descriptive text analysis on the datasets all_f.csv and all_m.csv. Produces visualizations, found in the Results directory. 
3. 03_Structural_Topic_Modeling.Rmd: Loads, preprocesses and conducts descriptive structural topic modeling text analysis on the datasets all_f.csv and all_m.csv. Produces visualizations, found in the Results directory.

### Results

1. word-associations.md: Table showing results for words associated with "you" for tweets sent to male and female senators. 
2. female_freq_graph.png: Graph showing the most frequent words sent to female senators. 
3. male_freq_graph.png: Graph showing the most frequent words sent to male senators
4. topic_quality_f.pdf: Graph showing the quality of each topic of tweets for female senators. The x axis shows how coherent a topic is, and the y axis shows exclusivity.
5. topic_quality_m.pdf: Graph showing the quality of each topic of tweets for male senators. The x axis shows how coherent a topic is, and the y axis shows exclusivity.
6. F Topics 1_7.pdf: Image of key words from topics 1-7 of tweets sent to female senators.
7. F Topics 8_15.pdf: Image of key words from topics 8-15 of tweets sent to female senators.
8. M Topics 1_7.pdf: Image of key words from topics 1-7 of tweets sent to male senators.
9. M Topics 8_15.pdf: Image of key words from topics 8-15 of tweets sent to male senators.
10. cloud_f_taxes.pdf: Word cloud on the topic "taxes" for tweets sent to female senators. 
11. cloud_m_taxes.pdf: Word cloud on the topic "taxes" for tweets sent to male senators. 
12. TopicProportions_F.pdf: Graph of topic prevalence for tweets sent to female senators. 
13. TopicProportions_M.pdf: Graph of topic prevalence for tweets sent to male senators. 
14. TopicCorrelation_F.pdf: Graphic of topic correlation for tweets sent to female senators. 
15. TopicCorrelation_M.pdf: Graphic of topic correlation for tweets sent to male senators. 
16. TopicCovariate_F.pdf: Plot showing the effect of the covariate ?senator? on the topic of interest. The outcome is the proportion of the reply tweets sent to each female senator that is about the topic.
17. TopicCovariate_M.pdf: Plot showing the effect of the covariate ?senator? on the topic of interest. The outcome is the proportion of the reply tweets sent to each male senator that is about the topic.


## More Information

For questions or comments, please contact jfrehn@berkeley.edu. 