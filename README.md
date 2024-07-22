
# NYC Taxi Trip Duration Prediction


This project involves predicting the duration of taxi trips in New York City using machine learning models. The dataset is sourced from a Kaggle competition and contains features such as pickup and dropoff datetime, pickup and dropoff locations, passenger count, and more.




## Project Structure

- **Data Preprocessing**: The data is loaded and split into training, validation, and test sets. Various preprocessing steps are performed, including handling missing values, datetime transformation, feature engineering, and scaling.
- **Model Training**: Three models are trained using hyperparameter tuning: SGDRegressor, HistGradientBoostingRegressor, and LGBMRegressor.
- **Evaluation**: Models are evaluated using Root Mean Squared Logarithmic Error (RMSLE) as the scoring metric.
- **Submission**: The best model is selected based on the evaluation results, and predictions are generated for submission to the competition.
## Data Preprocessing

- **Load Data**: The dataset is loaded from CSV files for training and testing.
- **Null Value Check**: A check for missing values in the datasets is performed.
- **Datetime Transformation**: Datetime features are split into components like year, month, day, hour, etc.
- **Feature Engineering**:
   - Rush Hour Feature: A new feature indicating whether the trip was during rush hours is added.
   - Categorical Encoding: Categorical variables are one-hot encoded.
- **Feature Scaling**: StandardScaler is used to scale both features and target variables.
## Model Training and Hyperparameter Tuning

Models are trained using RandomizedSearchCV to find the best hyperparameters. The following models and their hyperparameters are tuned:

- **SGDRegressor**:
  - Learning rate (eta0)
  - Regularization term (alpha)
  
- **HistGradientBoostingRegressor**:
  - Learning rate
  - Maximum number of iterations
  - Maximum depth
  - Minimum samples per leaf

- **LGBMRegressor**:
  - Number of leaves
  - Learning rate
  - Number of estimators
  - Maximum depth
## Evaluation

The models are evaluated using the Root Mean Squared Logarithmic Error (RMSLE) as the scoring metric. The best model is selected based on the lowest RMSLE score.


## Subsmission
The best-performing model is used to predict the test dataset, and the results are saved for submission.

## Results

- The results of the hyperparameter tuning are saved in CSV files located in the result/cv_results/GridSearchCV/ directory.
- The best model's parameters and scores are printed and saved.