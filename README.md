# Price Prophet

![Image](https://github.com/user-attachments/assets/2c8c50e1-1ccf-4ac6-8621-c903b48f9d9b)

This project studies the Ames housing dataset which focuses on houses based in Ames, Iowa. The dataset has 81 features and 1460 rows of houses. The goal is to predict the sales prices of the houses by using different models: Gradient Boosting Regressor, Random Forest, and XGBoost. After using each model separetely, Random Search or Grid Search is used to tune the hyperparameters and then with this information, each model is used again to see how much they improved.

# Exploratory Data Analysis

EDA is performed on the train.csv dataset to see how each feature might impact the price. Univariate, Bivariate, and Multivariate analysis is performed on all the features of the dataset. The categorical and quantitative features are separated within this file in order to be able to visualize subplots. Some features are explored individually for more insight and are separated from the rest for analysis. 

The conclusion was that there several features which should be dropped due to their large amount of Nans. Interestingly, most of these Nans are not actually null errors but they are actually a substitute for N/A meaning that particular feature was not available in that specific house. Regardless, some features such as PoolQC are notable for having nearly the entire dataset except for about 6 houses of of 1400 that didn't have Nan. This is because only those few houses actually had a pool. Therefore PoolQC was a very obvious candidate for dropping. A few other features were also dropped for having too high of a collinearity.

# Transform

This is where the unnecessary features were dropped and nulls were checked for and the data was cleaned and then sent into a processed CSV.

# Models

XGBoost has a reputation for being the most accurate and it lived up to it. Even before hyperparameter tuning, it was more accurate than Gradient Boosting Regressor or Random Forest ever were. The potential top 20 most important features were also explored within the model's files.

After working on the train file, the test file was then used to see each model's performance. Again, XGBoost was the best accurate model and despite it's reputation for also being expensive and slow performance-wise, it wasn't in this case.

# Conclusions

The model I chose as the best was of course, XGBoost after Grid Search, which improved it from a Root Mean Squared Error (RMSE) of 26300.42 to 25152.99 after log-reverse. Given more time, I would also do both Random Search and Grid Search on each model to see the difference, as Grid Search was taking far too long to run on the Gradient Boost model. I might also define a function for getting rid of nulls and one-hot encoding in the cleaning file instead of doing it each time for the models. I would also see what other features I can drop or not drop.

[Data features description text file](https://github.com/dq93/Price_Prophet/blob/main/data_description.txt)

![Image](https://github.com/user-attachments/assets/69cc11d6-7f1e-4f6d-ab97-da577cd346ca)
