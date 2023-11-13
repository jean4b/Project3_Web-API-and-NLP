# Project3_Web-API-and-NLP

## Problem Statement
The objective is to build the most optimal text classification model between Disneyland and Universal Subreddits, which will be implemented in KKDays (Travel booking agency) algorithm to classify customers' comments on these two theme parks. Moreover, the company wants to understand which brand is more popular and understand customer's tone/sentiment from the comment. The result would be the promotional tactics that will be targeted toward the more popular brand ticket sales.

## Analysis
- Data Summary: Disneyland and Universal data acquired are imbalanced, the title contains duplicates but the texts are distinct, Disney data spans from 2011 to 2017 while Universal data spans from 2011 to 2023.
- Vote Analysis: Outliers can be identified in both subreddits. Disneyland obtained more votes than Universal
- Top Vote Content Analysis: Both subreddits' contents are mainly policy updates, attraction/event updates, interesting stories, and interesting comments
- Post Length Analysis: Disneyland has more post length/post word count than Universal
- Top Word Count Analysis: 1-gram list cannot be able to classify as each subreddit, 2-gram and 3-gram contain distinct words that can be used for identifying distinct subreddits
- Sentiment Analysis: Both subreddits are neutral, no significant positive or negative tone
- Pre-processed the data: URL removal and Target words removal. Tokenizing, Lemmatizing, and Stop-word-removal are implemented in the form of 4 distinct combinations utilized in 4 new columns. Tokenized + Lemmatized are chosen.
- Bootstrapping is done to counter the imbalance of the Universal data
- Modeling:
  1. CountVectorizer+Logistic Regression
  2. CountVectorizer+Logistic Regression(bootstrapped data)
  3. CountVectorizer+Random Forest Classifier: Obtain the best score and the least percentage of incorrect prediction
  4. TfidfVectorizer+Random Forest Classifier
  5. CountVectorizer+Multinomial Naive Bayes
  6. TfidfVectorizer+Multinomial Naive Bayes
- Modeling Evaluation: Consider both Recall and Precision scores because both the prediction of both subreddits are important. F1 score is also considered
- Final Model: CountVectorizer+Random Forest Classifier is the chosen model because of the best score obtained and acquired the least amount of incorrect prediction

## Recommendation
- The classification model will utilized CountVectorizer+Random Forest Classifier
- Disneyland is more popular because obtained more post and more votes
- Promotional tactics will be targeted toward Disneyland ticket sales because popularity means higher demand

