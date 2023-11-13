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
  3. CountVectorizer+Random Forest Classifier
  4. TfidfVectorizer+Random Forest Classifier: Obtain the best score and the least percentage of incorrect prediction
  5. CountVectorizer+Multinomial Naive Bayes
  6. TfidfVectorizer+Multinomial Naive Bayes

Model Metrics Table:
|                                                   | Accuracy | Precision                        | Recall                           | F1                               | % Incorrect Prediction |
|---------------------------------------------------|----------|----------------------------------|----------------------------------|----------------------------------|------------------------|
| CountVectorizer+Logistic Regression(Original)     | 0.91     | Universal: 0.98 Disneyland: 0.91 | Universal: 0.75 Disneyland: 0.97 | Universal: 0.82 Disneyland: 0.94 | 6.75%                  |
| CountVectorizer+Logistic Regression(Bootstrapped) | 0.94     | Universal: 0.94 Disneyland: 0.94 | Universal: 0.93 Disneyland: 0.95 | Universal: 0.93 Disneyland: 0.94 | 6.13%                  |
| CountVectorizer + RandomForestClassifier          | 0.95     | Universal: 0.95 Disneyland: 0.94 | Universal: 0.93 Disneyland: 0.96 | Universal: 0.94 Disneyland: 0.95 | 5.13%                  |
| TfidfVectorizer + RandomForestClassifier          | 0.95     | Universal: 0.96 Disneyland: 0.94 | Universal: 0.93 Disneyland: 0.97 | Universal: 0.94 Disneyland: 0.95 | 4.45%                  |
| CountVectorizer + MultinomialNB                   | 0.92     | Universal:0.91 Disneyland:0.93   | Universal:0.92 Disneyland:0.92   | Universal:0.91 Disneyland:0.92   | 5.15%                  |
| TfidfVectorizer + MultinomialNB                   | 0.92     | Universal:0.91 Disneyland:0.93   | Universal:0.92 Disneyland:0.92   | Universal:0.92 Disneyland:0.93   | 6.96%                  |
- Modeling Evaluation: Consider both Recall and Precision scores because both the prediction of both subreddits are important. F1 score is also considered
- Final Model: TFidfVectorizer+Random Forest Classifier is the chosen model because of the best score obtained and acquired the least amount of incorrect prediction

## Recommendation
- The classification model will utilized TFidfVectorizer+Random Forest Classifier
- Disneyland is more popular because obtained more post and more votes
- Promotional tactics will be targeted toward Disneyland ticket sales because popularity means higher demand

