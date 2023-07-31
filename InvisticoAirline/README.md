# Overview 
- An airline company wants to have a model that is highly effective at predicting passenger satisfaction and determines which factors has more impact of the passenger satisfaction. 

# Data Understanding
The dataset contains contains 129,880 rows and 23 columns of customer feedback, and each row representing one customer’s responses. Note that responses were given on a 0 to 5 scale, 0 meaning **not at all satisfied** and 5 meaning **very satisfied**.


| Column name                      | Type | Description                                                                        |
|----------------------------------|------|------------------------------------------------------------------------------------|
| Satisfaction                     | str  | Customer’s overall assessment of airline, either “satisfied” or “dissatisfied”     |
| Gender*                          | str  | For purposes of this dataset, “Male” or “Female” were the only two responses       |
| Customer Type                    | str  | Customer’s loyalty, “Loyal Customer” or “Disloyal Customer”                        |
| Age                              | int  | Customer’s age                                                                     |
| Type of Travel                   | str  | Customer’s reason for travel, “business” or “personal”                             |
| Class                            | str  | Customer’s purchased seat class, “Business,” “Eco,” or “Eco Plus”                  |
| Flight Distance                  | int  | How far the flight traveled                                                        |
| Seat comfort                     | int  | Customer’s rating of seat comfort                                                  |
| Departure/Arrival time convenient| int  | Customer’s rating of convenience for departure and arrival time                    |
| Food and drink                   | int  | Customer’s rating of food and drink                                                |
| Gate location                    | int  | Customer’s rating of the convenience of the gate location                          |
| Inflight wifi service            | int  | Customer’s rating of the inflight wifi/Internet service                            |
| Inflight entertainment           | int  | Customer’s rating of inflight entertainment                                        |
| Online support                   | int  | Customer’s rating of online support services of the airline                        |
| Ease of online booking           | int  | Customer’s rating of the ease of booking tickets online                            |
| On-board service                 | int  | Customer’s rating of service by airline personnel                                  |
| Leg room service                 | int  | Customer’s rating of the amount of legroom                                         |
| Baggage handling                 | int  | Customer’s rating of convenience or ease of baggage handling                       |
| Checkin service                  | int  | Customer’s rating of check-in service by airline personnel                         |
| Cleanliness                      | int  | Customer’s rating of cleanliness of the airplane                                   |
| Online boarding                  | int  | Customer’s rating of the online boarding process                                   |
| Departure Delay in Minutes       | int  | How long the departure delay was for the flight measured in minutes                |
| Arrival Delay in Minutes         | int  | How long the arrival delay was for the flight measured in minutes                  |

# Modeling and Evaluation 
- The confusion matrix visualizes the comparision between predicted and test values.
![confusion matrix](/images/1.png)

-  The bar plot visualizes the relative feature importance of the predictor variables in your model.
![bar plot](/images/2.png)

**Insights**
- By a wide margin, `seat comfort` rated as most important in the model. The type of seating is very different between first class and coach seating. However, the perks of being in first class also go beyond the seating type, so perhaps that is an underlying explanation of this feature's importance.
- Surprisingly, `delays (both arrival and departure)` did not score as highly important.

# Conclusion
- The model created is highly effective at predicting passenger satisfaction.
- The feature importance of seat comfort warrants additional investigation. It will be important to ask domain experts why they believe this feature scores so highly in this model.