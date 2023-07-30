# Overview 
This project is to analyze the data collected by the HR department at Salifort Motors and to build a model that predicts whether or not an employee will leave the company. The model is also to identify possible factors that contribute to the employee's leaving. Because it is time-consuming and expensive to find, interview, and hire new employees, increasing employee retention will be beneficial to the company.

# Data Understanding
The data consisted of approximately 15k rows and 10 columns. The features are listed below: 

Feature  |Description |
-----|-----| 
satisfaction_level|Employee-reported job satisfaction level [0&ndash;1]|
last_evaluation|Score of employee's last performance review [0&ndash;1]|
number_project|Number of projects employee contributes to|
average_monthly_hours|Average number of hours employee worked per month|
time_spend_company|How long the employee has been with the company (years)
Work_accident|Whether or not the employee experienced an accident while at work
left|Whether or not the employee left the company
promotion_last_5years|Whether or not the employee was promoted in the last 5 years
Department|The employee's department
salary|The employee's salary (U.S. dollars)


Some other features were either extracted or dropped.

# Modeling and Evaluation 
- The graph below visualizes the **decision tree** splits:
![Confusion Matrix](/SalifortMotors/images/1.png)
The model predicts three times as many false negatives than it does false positives, and it correctly identifies only 16.6% of the users who actually churned.

- The barplot below visualizes the decision tree feature importances:
![Barplot](/SalifortMotors/images/2.png)

**Insight** 
- The barplot above shows that in this decision tree model, `last_evaluation`, `number_project`, `tenure`, and `overworked` have the highest importance, in that order. These variables are most helpful in predicting the outcome variable, `left`.


# Conclusion

To retain employees, the following recommendations could be presented to the stakeholders:

* Cap the number of projects that employees can work on.
* Consider promoting employees who have been with the company for atleast four years, or conduct further investigation about why four-year tenured employees are so dissatisfied. 
* Either reward employees for working longer hours, or don't require them to do so. 
* If employees aren't familiar with the company's overtime pay policies, inform them about this. If the expectations around workload and time off aren't explicit, make them clear. 
* Hold company-wide and within-team discussions to understand and address the company work culture, across the board and in specific contexts. 
* High evaluation scores should not be reserved for employees who work 200+ hours per month. Consider a proportionate scale for rewarding employees who contribute more/put in more effort. 
