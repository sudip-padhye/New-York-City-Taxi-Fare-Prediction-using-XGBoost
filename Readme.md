### NOTE - Before proceeding to execute the project, it is requested to download complete data files from the URL https://www.kaggle.com/c/new-york-city-taxi-fare-prediction/data

# Data Description-
## File descriptions
1. train.csv - Input features and target fare_amount values for the training set (about 55M rows).
2. test.csv - Input features for the test set (about 10K rows). Your goal is to predict fare_amount for each row.
3. sample_submission.csv - a sample submission file in the correct format (columns key and fare_amount). This file 'predicts' fare_amount to be $11.35 for all rows, which is the mean fare_amount from the training set.

## Data fields
### ID
key - Unique string identifying each row in both the training and test sets. Comprised of pickup_datetime plus a unique integer, but this doesn't matter, it should just be used as a unique ID field. Required in your submission CSV. Not necessarily needed in the training set, but could be useful to simulate a 'submission file' while doing cross-validation within the training set.

### Features
1. pickup_datetime - timestamp value indicating when the taxi ride started.
2. pickup_longitude - float for longitude coordinate of where the taxi ride started.
3. pickup_latitude - float for latitude coordinate of where the taxi ride started.
4. dropoff_longitude - float for longitude coordinate of where the taxi ride ended.
5. dropoff_latitude - float for latitude coordinate of where the taxi ride ended.
6. passenger_count - integer indicating the number of passengers in the taxi ride.

### Target
fare_amount - float dollar amount of the cost of the taxi ride. This value is only in the training set; this is what you are predicting in the test set and it is required in your submission CSV.

## Algorithm
This project uses XGBoost algorithm complemented with the Randomized Grid Search Cross-validation to find optimal hyperparameters. Certain input features for the algorithm are not readily avaliable in the input data (Eg. Trip Distance). They are computed by performing Feature Engineering on other available features. Data exploration is performed on the input data to understand their distribution and intrinsic properties. Dimensionality reduction (such as PCA) was performed but didn't show great result, hence removed from the project.
