# IPL-Match-Result-Prediction

This is an interesting dataset containing features such as team which bats first, Venue of the match, day and time of the match, windspeed, humidity at the venue, strike rate, number of 4s, 6s, etc.
It contains a total of 28 features and the task is to predict which team wins and with what probability. 

# Procedure followed

First, we explore the dataset and look for any missing values and any ambiguous figures. We perform interesting feature engineering such as:
1) Time of the Day the match is played segmented into 3 parts: Noon, Afternoon/Early Evening, Late Evening/Night
2) Team 1 (which bats first) One-Hot-Encoded as 1 and Team 2 (which bowls first) One-Hot-Encoded as -1. 
3) City (contains categorical data) One-Hot-Encoded
4) Extracting year and month as features from Date-time feature
5) Re-arranging the columns for our tree-based models (Their accuracy also depends upon the relative order of features)

Not much data-cleaning was required here as the data was more-or-less perfect. Also, I tried to scale the features using Standard Scaler, but the accuracy suffered big time, so I clinged back. 
I then used train-test-split and used a loop containing approx. 5 classifiers to quickly get the accuracy of all at once. Also, later I tried 2 more models, LightGBM and Multi-layer Perceptron.
Lastly, I tried using ensembles (SequentialEnsemble, SuperLearner, VotingClassifier) and hyperparameter tuning (RandomizedSearchCV).

Finally, I got good prediction accuracy, of 96% using LightGBM. 


