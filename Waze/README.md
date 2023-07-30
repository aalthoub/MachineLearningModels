# Overview 
This project is to find factors that drive user churn. A model is required to predict whether or not a Waze user is retained or churned.

# Data Understanding
The data consisted of approximately 15k rows and 13 columns. The features are listed below: 

| #   | Column                  | Non-Null Count | Dtype     |
|-----|-------------------------|----------------|-----------|
| 0   | ID                      | 14999 non-null | int64     |
| 1   | label                   | 14299 non-null | object    |
| 2   | sessions                | 14999 non-null | int64     |
| 3   | drives                  | 14999 non-null | int64     |
| 4   | total_sessions          | 14999 non-null | float64   |
| 5   | n_days_after_onboarding | 14999 non-null | int64     |
| 6   | total_navigations_fav1  | 14999 non-null | int64     |
| 7   | total_navigations_fav2  | 14999 non-null | int64     |
| 8   | driven_km_drives        | 14999 non-null | float64   |
| 9   | duration_minutes_drives | 14999 non-null | float64   |
| 10  | activity_days           | 14999 non-null | int64     |
| 11  | driving_days            | 14999 non-null | int64     |
| 12  | device                  | 14999 non-null | object    |


Some features were engineered to represent different information as shown below:
- `km_per_driving_day`, which represents the mean distance driven per driving day for each user
- `percent_sessions_in_last_month`, which represents the percentage of each user's total sessions that were logged in their last month of use.
- `professional_driver` that is a 1 for users who had 100 or more drives and drove on 15+ days in the last month, and 0 otherwise
- `km_per_hour`, which represents the mean kilometers per hour driven in the last month.
- `km_per_drive`, which represents the mean number of kilometers per drive made in the last month for each user.
- `percent_of_sessions_to_favorite`, which represents the percentage of total sessions that were used to navigate to one of the users' favorite places.

Other features either dropped or encoded upon building the model.

# Modeling and Evaluation 
The confusion matrix below visualizes the results of the **`XGBoost model`**:
![Confusion Matrix](/Waze/images/1.png)
The model predicts three times as many false negatives than it does false positives, and it correctly identifies only 16.6% of the users who actually churned.

The barplot below visualizes the model's coefficients to show the importance of the model's features:
![Barplot](/Waze/images/2.png)


# Conclusion
1. > _If the model is built to drive consequential business decisions, then it is not recommeded to use it. The model is not a strong enough predictor, as made clear by its poor recall score. However, if the model is only being used to guide further exploratory efforts, then it can have value._

2. > _New features could be engineered to try to generate better predictive signal, as they often do if you have domain knowledge. In the case of this model, the engineered features made up over half of the top 10 most-predictive features used by the model. It could also be helpful to reconstruct the model with different combinations of predictor variables to reduce noise from unpredictive features._

6. > _It would be helpful to have drive-level information for each user (such as drive times, geographic locations, etc.). It would probably also be helpful to have more granular data to know how users interact with the app. For example, how often do they report or confirm road hazard alerts? Finally, it could be helpful to know the monthly count of unique starting and ending locations each driver inputs._
