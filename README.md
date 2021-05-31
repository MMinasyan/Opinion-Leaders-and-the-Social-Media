# Opinion-Leaders-and-the-Social-Media

Research project analyzing public opinion formation during the campaign during the campaign.

Used methods: Sentiment analysis, Recurrent NNs, Structural vector autoregression, Impulse response analysis.

Outcome: Finding the patterns of responses from groups of people to the exogeneous shocks

The primary data used in this paper is collected from Twitter using Twitter Search API. It includes over 1,000,000 public tweets created between September 9th and October 27th and  mentioning President Trump or the Republican Party in two datasets accordingly

## Classification Problem

 
For getting sentiment values (positive, neutral or negative) for whole data set, the most efficient way is to train and test a model on a small portion of the full data, and apply it to the rest of tweets. Nearly 5000 random sample of tweet texts are classified manually and used in training of a neural network model in 75/25 training/validation ratio.

### RNN Classification Candidate.ipynb RNN Classification Candidate.ipynb

* cleaning by dropping the symbols and word endings (voting, voted, votes $\rightarrow$ vot)
* dropping stop words (the, is, on, etc.)
* vectorizing tweet texts.
* RNN/LSTM model training and testing on sample data
* predicting sentimant values using trained model for rest of the data

## Analysis

### preprocessing.ipynb

Tweets of users having number of followers larger than 10000 (95 percentile) are detached from the others. And as a last step, all the data is aggregated into a single data set with 12-hours frequency and with 4 variables presenting the percentage of positive tweets in total number of non-neutral tweets.

### R_notebook.Rmd

A Structural vector autoregressive model is estimated. Based on SVAR model, impulse responses are estimated as well as confidence intervals.

### Impulse Responses.ipynb

Impulse response functiones are visualised.

### tests.ipynb

Augmented Dickey–Fuller test for stationarity of variables used in SVAR model.
