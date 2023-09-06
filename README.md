# Health-Insurance_premium_prediction

### Context:
An insurance company in the US is reviewing its insurance claims/charges and is trying to do a cause and effect analysis for future business decisions. It has collected data for its customers who have made claims till recent time. The data-points collected are age, gender, bmi, number of children/dependents, smoking habit, region they belong to, charges/bills claimed under the insurance. This analysis would have a bearing on what premium should the company charge a customer availing an insurance policy.

### Business objective:
The objective is to do a cause and effect analysis on historic-data of insurance claims and predict how much premium amount should  the company it's customers.

### Approach:
#### Excel Analysis
   1. To understand the given data the histograms and box plots were used and primary EDA have been carried out and following insights were gathered.
         1. The demography that we are looking at has more no. of young people in the age bracket of 18-30
         2. More no of people have lesser insurance charges, whereas lesser no of people have high insurance charges, It would be interesting to know who are these people
         3. Age and charges graphs slightly hint that middle aged people and probably older people might be getting billed more under the insurance
         4. Is age the only factor or are there more factors contributing to the insurance charges?
         5. BMI is distributed normally
         6. Charges and bmi have outliers, these might be some points to study separately, whether higher BMI is causing higher health problems and claims as result
      
  2. The correlation between the fields age, bmi and charges were analyzed to gather the information about how they are related.
  3. Various pivot tables and cahrts were introdeced to understand the following fields
        1. Male/Female ratio and share information on which gender has more smokers
        2. Charges vs Age
        3. Charges vs BMI
        4. Charges for Smokers vs Non-smokers 
  
  4. The regionwise smokers ratio and the premium charged to a smoker were analyzed and it was determined that a smoker from a southeast region was charged the most.
  5. The number of family members in the claimants family also have effects on the charge. a person with 2 and 3 childern was charged more than others.

With all these done and after a good understanding of the dataset and the fields within the data was being prepared for Regression.
  1. The Categorical columns were encoded and converted into Numerical columns.
  2. First regression has been carried out and the following insights were gathered.
       1. On checking the normality plot we see the data is not a perfectly normal-distributed data, because we saw many outliers; these outliers could be natural outliers															
       2. R-square values are good enough for real-life case study															
       3. The observation for regions is to be interpreted w.r.t 'northeast' region															
       4. We observe that charges for southeast region reduces wr.r.t northeast region, contrary to our expectation from EDA															
       5. We should try another regression analysis with "northwest" and "sex" variables dropped.
  
  3. The second regression gave the following insights
       1. smoker, age, bmi, no. of children are important variables in that order of their t-stat values
       2. southeast region has a negative relation with charges (this is w.r.t. northeast), meaning people from this region claim lesser than others
       3. southwest region doesn't come out to be a significant variable
       4. Standardized residuals show no deviating pattern, means there is no heteroscadasticity
  
  5. However we should also check for combined effect of region and smoking habbit so three mmore columns were added.
  6. And third regression has been carried out	which shows that sex, northwest and northwest_smoker are not significant variables So we will run one more regression with these variables dropped
  7. The final regression has been carried out and final insights which that have been collected were
       1. Smoker, age, bmi have a very strong and direct impact on increasing insurance charges claim
       2. Also a smoker in southeast and southwest region will claim higher charges
       3. If we look at only the region as an independant variable then people from south east and south west region claim lesser charges w.r.t our reference region northeast
       4. Claimants having more no. of children also show higher claims

#### Python Analysis
This is a Python script that uses the scikit-learn library to train two machine learning models, a Linear Regression model and a Gradient Boosting Regression model, on an insurance dataset. 
1. Import necessary libraries: The script starts by importing the necessary libraries, including joblib, pandas, matplotlib.pyplot, train_test_split, LinearRegression, GradientBoostingRegressor, and mean_squared_error.
2. Load and preprocess data: The script loads the insurance dataset from a CSV file using the pandas library. It then preprocesses the data by mapping categorical variables to numerical values.
3. Split data into features and target: The script splits the data into features (X) and target (y) by dropping the 'charges' column from the dataset.
4. Split data into training and test sets: The script uses the train_test_split function to split the data into training and test sets, with 20% of the data reserved for testing.
5. Train Linear Regression model: The script creates an instance of the LinearRegression class and fits it to the training data using the fit method.
6. Train Gradient Boosting Regression model: The script creates an instance of the GradientBoostingRegressor class and fits it to the training data using the fit method.
7. Make predictions on test data: The script uses both trained models to make predictions on the test data using the predict method.
8. Calculate mean squared error for both models: The script calculates the mean squared error (MSE) for both models using the mean_squared_error function from the sklearn.metrics module. It then prints the MSE values for both models.
9. Calculate R² for both models: The script calculates the coefficient of determination (R²) for both models using the r2_score function from the sklearn.metrics module. It then prints the R² values for both models.
10. Visualize the model’s performances: The script creates a DataFrame containing actual and predicted values for both models, then uses matplotlib.pyplot to create two subplots visualizing these values.
11. Get user input: The script prompts the user to enter information about a new customer, including their age, sex, BMI, number of children, smoker status, and region.
12. Create DataFrame for new customer: The script creates a DataFrame containing this information.
13. Make prediction for new customer: The script uses the trained Gradient Boosting Regression model to make a prediction for this new customer’s insurance cost using the predict method. It then prints this predicted value.

### Tools used: Advanced Excel, Python(NumPy, Pandas, Statsmodel)
