# Overview 
The professional basketball league in North America is interested in retaining players who can last in the high-pressure environment of professional basketball and help the team be successful over time. The goal is to build a model that predicts whether a player will have an NBA career lasting five years or more. 

# Data Understanding
The data for this project consists of performance statistics from each player's rookie year. There are 1,340 observations, and each observation in the data represents a different player in the NBA. The target feature is a Boolean value that indicates whether a given player will last in the league for five years.

| #   | Column        | Meaning                                                      | Non-Null  | Dtype    |
| --- | ------------- | ------------------------------------------------------------ | --------- | -------- |
| 0   | fg            | Made Field goal percentage                                   | non-null  | float64  |
| 1   | 3p            | Made 3-point field goal percentage                           | non-null  | float64  |
| 2   | ft            | Made free throw percentage                                   | non-null  | float64  |
| 3   | reb           | Average rebounds per game                                    | non-null  | float64  |
| 4   | ast           | Average assists per game                                     | non-null  | float64  |
| 5   | stl           | Average steals per game                                      | non-null  | float64  |
| 6   | blk           | Average blocks per game                                      | non-null  | float64  |
| 7   | tov           | Average turnovers per game                                   | non-null  | float64  |
| 8   | target_5yrs   | Players career duration was more than 5 years (0= yes, 1=no) | non-null  | int64    |
| 9   | total_points  | Total number of points scored across 5 years                 | non-null  | float64  |
| 10  | efficiency    | Total points divided by minutes played per game              | non-null  | float64  |

# Modeling and Evaluation 
- The confusion matrix below visualizes the predicted and test values
![Confusion Matrix](/images/1.png)

- The performance metrics of the model:
    - `accuracy score`: 0.698
    - `precision score`: 0.821
    - `recall score`: 0.626
    - `f1 score`: 0.711

**Insights:** 
- The top left to bottom right diagonal in the confusion matrix represents the correct predictions, and the ratio of these squares showcases the accuracy.
- The concentration of true positives stands out relative to false positives. This ratio is why the `precision score` is so high (0.8212).
- True negatives and false negatives are closer in number, which explains the worse `recall score`.

# Conclusion
- The model provides some value in predicting an NBA player's chances of playing for five years or more.
- Notably, the model performed better at predicting true positives than it did at predicting true negatives. In other words, it more accurately identified those players who will likely play for more than five years than it did those who likely will not.