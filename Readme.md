# **NYC Limousine Taxi Fare Prediction Using Hypothesis Testing and Regression Analysis**


## TABLE OF CONTENTS
1. [Project Title](#project-title)
2. [Project Summary](#project-summary)
3. [Project Proposal](#project-proposal)
4. [Dependencies](#dependencies)
5. [Requirements](#requirements)
6. [Results/Insights](#resultsinsights-gotten)
7. [Recommendations](#recommendations)
8. [Limitations](#limitations)
9. [Connect With Me](#connect-with-me)


### PROJECT SUMMARY
---
This project used a dataset called [2017_Yellow_Taxi_Trip_Data.csv](https://drive.google.com/file/d/1dukkevz_dONJf1aqojEy_4Q6pFZ8kK5_/view). It contains data gathered by the New York City Taxi & Limousine Commission. New York City TLC is an agency responsible for licensing and regulating New York City's taxi cabs and for-hire vehicles. For this project, I would be developing a regression model that helps estimate taxi fares before the ride. I would also be building a model that can accurately predict if a customer would be generous enough to give a tip to the drivers. 

### PROJECT PROPOSAL
---
1. Build a dataframe for the TLC dataset.
2. Examine data type of each column.
3. Perform EDA and Data Cleaning.
4. Gather Descriptive/inferential statistics of the data.
5. Build a Regression model from the New York City TLC dataset.
6. Evaluate the model and check model assumptions
7. Interpret model results and summarize findings 

### DEPENDENCIES
---
- Pandas
- Numpy
- Scikit Learn
- Scipy
- Datetime
- Matplotlib

### REQUIREMENTS
---
- Exploratory Data Analysis
- Feature Engineering
- Hypothesis Testing
- Regression Analysis: Linear Regression
- Machine Learning: Random Forest, XGBoost

### RESULTS/INSIGHTS GOTTEN
---
1. It can be deduced that only customers that paid with Credit cards tipped the drivers.
2. Monthly rides were fairly consistent, with notable dips in February, July, August, and September.
3. May had the highest revenue by month while July had the least. The monthly revenue have a close distribution within themselves.
4. Wednesday through Saturday had the highest number of daily rides, while Sunday and Monday had the least.
5. Thursday had the highest gross revenue of all days while Sunday and Monday had the least.
6. 71% of the rides were single occupancy.
7. From the Hypothesis Testing, there was a statistically significant difference in the average fare amount between customers who use credit cards and customers who use cash. The null hypothesis was rejected.
8. Half of the customers in this dataset were "generous" (tipped ≥ 20%). The dataset is very nearly balanced.
9. XGBoost model was the champion for predicting customers that would leave a tip.


### RECOMMENDATIONS
---
1. Encouraging customers to pay with credit cards can generate more revenue for taxi cab drivers.
2. Would I recommend using this model? Why or why not?\
Yes, this model performs acceptably. Its F1 score was 0.995337 and it had an overall accuracy of 0.995087. It correctly identified ~99% of the actual responders in the test set, which is 50% better than a random guess. It may be worthwhile to test the model with a select group of taxi drivers to get feedback.
3. How good is my highest scoring model and how can I explain its predictions?\
Unfortunately, XGBoost is not the most transparent machine learning algorithm. We know that VendorID, predicted_fare, mean_duration, and mean_distance are the most important features, but we don't know how they influence tipping. This would require further exploration. It is interesting that VendorID is the most predictive feature. This seems to indicate that one of the two vendors tends to attract more generous customers. It may be worth performing statistical tests on the different vendors to examine this further.
4. What features would I want to have that would likely improve the performance of the model?\
It would probably be very helpful to have past tipping behavior for each customer. It would also be valuable to have accurate tip values for customers who pay with cash. It would be helpful to have a lot more data. With enough data, we could create a unique feature for each pickup/dropoff combination.


### LIMITATIONS
---
- The model performance is high on both training and test sets, suggesting that there is little bias in the model and that the model is not overfit. In fact, the test scores were even better than the training scores.
- When the mean_distance and mean_duration columns were computed, the means were calculated from the entire dataset. These same columns were then used to train a model that was used to predict on a test set. A test set is supposed to represent entirely new data that the model has not seen before, but in this case, some of its predictor variables were derived using data that was in the test set. This is known as data leakage. Data leakage is when information from your training data contaminates the test data. If your model has unexpectedly high scores, there is a good chance that there was some data leakage. To avoid data leakage in this modeling process, it would be best to compute the means using only the training set and then copy those into the test set, thus preventing values from the test set from being included in the computation of the means. This would have created some problems because it's very likely that some combinations of pickup-dropoff locations would only appear in the test data (not the train data). This means that there would be NaNs in the test data, and further steps would be required to address this. In this case, the data leakage improved the R2 score by ~0.03.

### Connect with Me
- [Linkedin](https://www.linkedin.com/in/alexandergodwindre)
- [Twitter](https://www.X.com/afambualexander)
- [Gmail](alexandergodwindre@gmail.com)




