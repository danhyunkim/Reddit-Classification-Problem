# Executive Summary

## Problem Statement

Using Natural Language Processing, classify whether a given Reddit post originated from the Nike or Adidas Subreddit

## Data Gathering

Gathered sample posts from both Nike and Adidas Subreddits through Reddit's API. The API caps users at 1000 posts per Subreddit so we were not able to retrieve that expansive of a sample set.

## Model Selection and Preprocessing

We tested each classification model below under both CountVectorizer and TFI-DF Vectorizer and proceeded with the one that had the strongest accuracy score:

- Logistic Regression
- Multinomial Naive Bayes
- Decision Tree
- Bagging Method
- Random Forest
- Extra Trees

## Findings

The Logistic Regression model under the CountVectorizer, although overfit, was the most accurate.

|Training Score| Test Score|
|---|---|
|0.97|0.768|

## Next Steps

Our model only worked with one vectorized feature, the title column, to predict whether a given post belonged to the Nike subreddit. To fine tune our model we can:

- Add more features:

    - The lemmatized and vectorized words in the text column
    - Dummy variables of the author column
    - Weeks since creation
    - Post Score

- Play with our hyperparameters of the vectorizers:

    - Increase the ngram_range
    - Increase the min_df count

- Remove vectorized words that are in the title of the Subreddit (i.e. ‘Nike’, ‘Adidas’) and remove post agnostic words