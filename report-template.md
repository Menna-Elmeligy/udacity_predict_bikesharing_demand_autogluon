# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### MennatAllah Hassan Elmeligy

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
First before submitting the results to kaggle:
* During training, I had to drop the registered and casual columns from the traindataset because they were missing from the test dataset.
* I needed to ensure that all prediction values were above zero, so I set all the negative values to zero.
* I needed to fill the prediction values in the submission dataframe which only had 2 features (datetime, count).

### What was the top ranked model that performed?
To find the top-ranked model, we run `predictor.leaderboard(train)`, the output is a dataframe of the top-performing models. The top model is KNeighborsDist_BAG_L1.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
After performing Exploratory Data Analysis (EDA) by running `train.hist()`, we find that:
* season: the data were approximately equal for 1(Spring), 2(Summer), 3(Fall), 4(Winter)
* holiday: the number of 0s (holidays) > 1s(not holidays)
* humidity: most data were in the low humidity.

### How much better did your model preform after adding additional features and why do you think that is?
After splitting datetime into separate year, month, day, hour features, the score went from 1.83 to 0.55, indicating that the accuracy of predicting the count increased. I think this is because of the increased specificity and thereby fitting of data after splitting the datetime. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After hyperparameter tuning; I increased the number of epochs for the NN model from the default 10 to 15, and set the presets to be high quality, and the num_boost_round for GBM to be 50. I noticed that the score has improved but not that much; it went from 0.55 to 0.48.

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend the extra time trying to do more EDA, because I think the score dramatically improved after EDA. I would do more feature engineering on the categorical data (such as holiday) by hot- encoding. I would also split the weather column into more features (clear, misty, light snow, and heavy rain)

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
	|model|hpo1|hpo2|hpo3|score|
	|initial|nn_options.num_epochs=10|gbm_options.num_boost_round=100|presets=best_quality|1.83480|
	|add_features|nn_options.num_epochs=10|gbm_options.num_boost_round=100|presets=best_quality|0.55169|
	|hpo|nn_options.num_epochs=15|gbm_options.num_boost_round=50|presets=high_quality|0.48307|
 

### Create a line plot showing the top model score for the three (or more) training runs during the project.


![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
The aim of this project was to predict the count of bike shares on test dataset. In doing this, we used the autoML platform AutoGluon. It provides automatic data cleaning and preprocessing and use a number of models to fit the training dataset. To sum up, we performed the following steps:
    * we created a predictor instance from TabularPredictor of Autogluon and used it to fit the raw training dataset.
    * We performed EDA and splitted the datetime feature and used the predictor to fit the train dataset after feature engineering .
    * Then we performed hyperparameter tuning of the model parameters and reused the predictor on the train dataset.
