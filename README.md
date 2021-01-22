# Project 3 - Web APIs & NLP

## Problem Statement

This project aims to scrape and analyze submissions and submission titles from r/HipHopHeads and r/Indieheads in order to train a classifier on which subreddit a post came from. Multinomial Naive Bayes, Logistic Regression, and Random Forest Classifier will be used to test the models. This goal of this project is to make the research process for The Fader article writers more streamlined and efficient.

## Data

The data used in this project was collected from two subreddits:
- r/HipHopHeads
- r/Indieheads

5,000 posts from each subreddit (10,000 total) were scraped. A dataframe was created, cleaned, and formatted from these posts.

## Modeling

After the features (*selftext_&_title*) and target (*hiphop_or_indie*) variables were selected and a train-test split was performed on them, the foll0wing models were tested:
- Multinomial Naive Bayes with CountVectorizer
    - Test Score: 0.785
- Logistic Regression with CountVectorizer
    - Test Score: 0.823
- Multinomial Naive Bayes with TFIDFVectorizer
    - Test Score: 0.791
    - Gaussian NB is generally recommended for TFIDF, but it wasn’t producing desirable results, so multinomial was used instead
- Random Forest Classifier with CountVectorizer
    - Test Score: 0.842

## Findings and Conclusion

- Although the Random Forest CLassifier had the highest test score, the model is overfit.
- Therefore, the Logistic Regression model performed the best with its test score of 0.823 and should be used when predicting the origin of a post.

## Next Steps

The following steps can be taken in order to guarantee a more accurate model and prediction:
- Experiment with more parameters when testing this model
- Preprocessing and modeling with a more powerful computer because it would produce results much sooner
- Test model on less popular subreddits
- Explore other methods like boosting

## Works Cited

- https://www.thefader.com/
- https://www.reddit.com/r/hiphopheads/new/
- https://www.reddit.com/r/indieheads/new/
- https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html
- https://github.com/pushshift/api
- https://stackoverflow.com/questions/24386489/adding-words-to-scikit-learns-countvectorizers-stop-list
- https://stackoverflow.com/questions/1276764/stripping-everything-but-alphanumeric-chars-from-a-string-in-python
- DSI lessons 5.01-6.04