# Datathon-May-2020

(Describe the process of data cleaning here if you want)
Our first step was to combine the data spanning different states into one dataset with what we thought was all of its useful features (Density, Urban Population, Rural Population, etc.) However, as we were testing out various machine learning algorithms such as Boosted Random Forest and XGBoost, we found that these models failed to accurately depict the trend of COVID. After giving it much thought, we realized that the characteristics of the city cannot be used as a feature for the model due to the lack of different datapoints. With how data reliant machine learning models, it is unrealistic for us to assume that it would derive meaningful insights from 4 separate data points.

Therefore, we have decided to build a separate machine learning model for each city. The only feature we will be using is the number of days from the first recorded day of March 14. Each city will have three machine learning models to predict the infections, recoveries, and deaths in a day.

From here, we individually set out to find the best machine learning model that would fit well with our data.

Kenzie's experience:

The first thing I did was to test the simplest solution in the form of a linear regression model. This was obviously not sufficient in predicting the data but it did provide a good place to start off from and a root mean squared error (RMSE) to compare the other models to (78, 81, 3 : infections, recoveries, deaths). Afterwards, I explored the possibility of using a random forest regressor. Looking at the low RMSE value of the model (28, 34, 1 : infections, recoveries, deaths), it might have seemed to be a good model at first. However, after visualizing the data, it's easy to see that it overfit the data horribly and would be useless in predicting the infection/recovery/death counts for number of days outside the dataset.

Next, I moved on to fitting a polynomial curve onto the data. Although this seemed like a realistic thing to do and obtained RMSE values of 69, 78, and 2.6, I believed there are still better models especially since the visualization showed that fitting the data to a polynomial caused the predictions to unnescessarily fluctuate just to fit the data better.

Finally, I used a support vector machine where the visualization showed that this was the most realistic outcome. Although its RMSE values were slightly higher than fitting a polynomial (73, 84, 2.9), it is less likely to overfit and more likely to make accurate predictions on the future of the virus.

The next step is to implement the model. Since the dataset did not contain any trend of the virus decreasing, we can see that it is impossible for the machine learning model to be able to understand that the virus will eventually decrease in infectivity. Therefore, we will make the extreme assumption that everyone at one point will be infected with the coronavirus. By doing this, we can obtain a worse case estimator.




