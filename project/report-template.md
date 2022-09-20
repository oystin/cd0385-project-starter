# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Austin Chu

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
The predictions from the output of the predictor follow a regression line so there is potential for negative values, which does not make sense given we are predicting bike share demand. Therefore, it was required to change any negative prediction values to zero. However, for my case, there happened to be no negative value predictions.

### What was the top ranked model that performed?
The model that performed the best was the WeightedEnsemble_L3 model after I feature engineered some datetime related features.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Through exploratory data analysis, I realized the easiest feature to add would be converting the single datetime feature into multiple features related to year, month, day, and weekday.

### How much better did your model preform after adding additional features and why do you think that is?
The model performed significantly better, with a RMSE of 30 vs the original 50+. This makes sense intuiitively because bike share demand is likely highly correlated with the day of the week and also the month.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Honestly, the model performed worse after my attempts at tuning hyper parameters. I attempted to tune the general hyper parameters for AutoGluon TabularPredictor instead of specific model type hyper parameters. I then realized the hyper parameters I was tuning were overwriting the presets='best_quality' hyper parameters.

### If you were given more time with this dataset, where do you think you would spend more time?
I would take the time to standardize/normalize the continuous features, so their variation is more influential on the prediction results vs just sheer magnitude. I would also take the time to specifically tune the hyperparameters of the top performing models.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|?|?|?|?|
|add_features|?|?|?|?|
|hpo|?|?|?|?|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](model_test_score.png)

## Summary
TODO: Add your explanation
