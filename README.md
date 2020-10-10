# salaryprediction


Salary Prediction Project (Python)

### The problem

I was given a feature dataset and a target dataset for training purposes, and also a test dataset for prediction purposes.
The feature dataset contains job characteristics for which there is a corresponding salary (target dataset). 

### Exploratory Data Analysis

I started verifying that there were no null, missing  or duplicated values, and that there were 5 categorical and 2 numeric features.
I proceeded to merge the features and  target training dataset into only 1 dataset.
I used the IQR of the salary feature to determine upper and lower bounds to find outliers.

I verified that upper outliers with junior jobtype were still reasonable so I just cleaned the data by eliminating the outliers below the lower bound.

I checked for correlation between each feature and the target.
I used label encoding in categorical features to be able to make a heatmap.

+ [Distribution Plot](/images/distribution_plot.png)

Ploting numerical features against target feature showed:

- Positive linear relation between "Years of experience" and "Salary".
- Negative linear relation between "Miles from Metropolis" and "Salary"


+ [Heatmap of correlation between features](/images/heatmap.png)


I started using Linear Regression as a baseline and selected MSE as a reasonable metric.

The following moodels were created:
-Linear Regression 
-Pipeline with StandardScaler, PCA and Linear Regression.
-Random Forest Regressor
-Gradient Boosting Regressor

I did 5 fold cross validation on models and measured MSE.

The model with the lowest MSE was Gradient Boosting Regressor

Gradient Boosting Regressor was trained on entire training set and scored on test set to create predictions.

### Files
 
 + CSV datasets can be found in the data folder
 + Images of this README can be found in the images folder
 + Model can be found in the model.txt file
 + Feature importances can be found in the feature_importances.csv file
 + Predictions on test set can be found in the predictions.csv file.