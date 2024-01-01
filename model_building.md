
### Model Building
We will be using pyspark to train our model and using RandomForest as our model which will be trained on the features that we have engineered.
#### Splitting the Dataset
- We split the data in 80:20 for training and testing purposes.
- We will undersample the training data to reduce the skew but will keep the test set as it is to represent the actual data population

#### Addressing Data Skew
- One of the challenges we saw was data imbalance where our data was skewed.
- To mitigate this issue, we employed undersampling techniques. Specifically, we used percentile bins to group data points based on the distribution of the target variable. Smaller width bins, representing data skew, were identified for undersampling.

#### Training with PySpark
- We trained our model on the undersampled_train_data using Random Forest Regressor in pyspark we used different worker configs 1,2,4 and logged the training time, model metrics like mae and mape for train, and test set using mlflow. Detailed results are attached in the main readme file for reference.
