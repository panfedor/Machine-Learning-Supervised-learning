**Intro**

*Answer the questions*

- Derive an analytical solution to the regression problem. Use a vector form of the equation.
- What changes in the solution when L1 and L2 regularizations are added to the loss function.
- Explain why L1 regularization is often used to select features. Why are there many weights equal to 0 after the model is fit?
- Explain how you can use the same models (Linear regression, Ridge, etc.) but make it possible to fit nonlinear dependencies.

*Introduction — make all the preprocessing staff from the previous lesson*

- Import libraries.
- Read Train and Test Parts.

*Intro data analysis part 2*

- Let's generate additional features for better model quality. Consider a column called "Features". It consists of a list of highlights of the current flat.
- Remove unused symbols ([,], ', ", and space) from the column.
- Get all values in each list and collect the result in one huge list for the whole dataset. You can use DataFrame.iterrows().
- How many unique values does a result list contain?
- Let's get acquainted with the new library — Collections. With this package you could effectively get quantity statistics about your data.
- Count the most popular functions from our huge list and take the top 20 for this moment.
- If everything is correct, you should get next values:  'Elevator', 'CatsAllowed', 'HardwoodFloors', 'DogsAllowed', 'Doorman', 'Dishwasher', 'NoFee', 'LaundryinBuilding', 'FitnessCenter', 'Pre-War', 'LaundryinUnit', 'RoofDeck', 'OutdoorSpace', 'DiningRoom', 'HighSpeedInternet', 'Balcony', 'SwimmingPool', 'LaundryInBuilding', 'NewConstruction', 'Terrace'.
- Now create 20 new features based on the top 20 values: 1 if the value is in the "Feature" column, otherwise 0.
- Extend our feature set with 'bathrooms', 'bedrooms' and create a special variable feature_list with all feature names. Now we have 22 values. All models should be trained on these 22 features.

*Models implementation — Linear regression*

- Implement a Python class for a linear regression algorithm with two basic methods — fit and predict. Use stochastic gradient descent (SGD) to find optimal model weights. For better understanding, we recommend implementing separate versions of the algorithm with the analytical solution and non-stochastic gradient descent under the hood.
- What is determenistic model? Make SGD determenistic.
- Define the R squared (R2) coefficient and implement a function to calculate it.
- Make predictions with your algorithm and estimate the model with MAE, RMSE and R2 metrics.
- Initialize LinearRegression() from sklearn.linear_model, fit the model, and predict the training and test parts as in the previous lesson.
- Compare the quality metrics and make sure the difference is small (between your implementations and sklearn).
- Store the metrics as in the previous lesson in a table with columns model, train, test for MAE table, RMSE table, and R2 coefficient.

*Regularized models implementation — Ridge, Lasso, ElasticNet*

- Implement Ridge, Lasso, ElasticNet algorithms: extend the loss function with L2, L1 and both regularizations accordingly.
- Make predictions with your algorithm and estimate the model with MAE, RMSE and R2 metrics.
- Initialize Ridge(), Lasso(), and ElasticNet() from sklearn.linear_model, fit the model, and make predictions for the training and test samples as in the previous lesson.
- Compare quality metrics and make sure the difference is small (between your implementations and sklearn).
- Store the metrics as in the previous lesson in a table with columns model, train, test for MAE table, RMSE table, and R2 coefficient.

*Feature normalization*

- First, write several examples of why and where feature normalization is mandatory and vice versa.
- Let's consider the first of the classical normalization methods — MinMaxScaler. Write a mathematical formula for this method.
- Implement your own function or class for MinMaxScaler feature normalization.
- Initialize MinMaxScaler() from sklearn.preprocessing.
- Compare the feature normalization with your own method and with sklearn.
- Repeat the steps from b to e for another normalization method StandardScaler.

*Fit custom and sklearn models with normalized data*

- Fit all models — Linear Regression, Ridge, Lasso, and ElasticNet — with MinMaxScaler.
- Fit all models — Linear Regression, Ridge, Lasso, and ElasticNet — with StandardScaler.
- Add all results to our dataframe with metrics on samples.

*Overfit models*

- Let's look at an overfitted model in practice. From theory, you know that polynomial regression is easy to overfit. So let's create a toy example and see how regularization works in real life.
- In the previous lesson, we created polynomial features with degree 10. Here we repeat these steps from the previous lesson, remembering that we have only 2 basic features — 'bathrooms' and 'bedrooms'.
- And train and fit all our implemented algorithms — Linear Regression, Ridge, Lasso, and ElasticNet — on a set of polynomial features.
- Store the results of the quality metrics in the result dataframe.
- Analyze the results and select the best model according to your opinion.
  
*Native models*

- Calculate the mean and median metrics from the previous lesson and add the results to the final dataframe.

*Compare results*

- Print your final tables
- What is the best model?
- Which is the most stable model?
