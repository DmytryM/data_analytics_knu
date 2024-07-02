# Tasks for passing the data analytics course at KNU

## Task 1: Laboratory work #1

1. Load data, check for correctness, missing values, data types.
2. If necessary, create new variables.
3. Conduct a correlation analysis. Define the dependent and independent variables. Build visualizations.
4. Check that the assumptions of the regression analysis are met.
5. Build a model with one predictor. Evaluate the effectiveness of the model.
6. Perform residual analysis.
7. Interpret the model parameters. Construct confidence intervals for the model parameters. Test the hypotheses about the significance of the parameters.
8. Draw conclusions.

#### Dataset:
    
Car details v3.csv

##### Column descriptions

 1. name           8128 non-null   object 
 2. year           8128 non-null   int64  
 3. selling_price  8128 non-null   int64  
 4. km_driven      8128 non-null   int64  
 5. fuel           8128 non-null   object 
 6. seller_type    8128 non-null   object 
 7. transmission   8128 non-null   object 
 8. owner          8128 non-null   object 
 9. mileage        7907 non-null   object 
 10. engine         7907 non-null   object 
 11. max_power      7913 non-null   object 
 12. torque         7906 non-null   object 
 13. seats          7907 non-null   float64

## Task 2: Laboratory work #2

Let's apply linear regression in practice - let's try to predict the cost of cars and understand what factors determine car pricing. In addition, we will learn which variables are important for forecasting and how well the obtained model describes the data.

Task:
1. Load data, check for correctness, missing values, data types.
2. Create a new feature - car brand (company). Which manufacturers' machines are found in the dataset? Next, correct the names and verify the changes.
3. Leave only a part of the predictors, after which calculate the correlation between price and other variables.
4. Convert categorical variables using pd.get_dummies() for Python and fastDummies::dummy_cols() for R.
5. Build a model with one price predictor - horsepower. What percentage of variability does the resulting model explain? (R**2)
6. Next - two models (with all predictors and with all except car brands). Note the changes in R**2, coefficients and their significance. Which model is better to leave?
7. Fill in the gaps in the following text:

The selected model explains approximately SELECT% of the variance (round to a whole). Among the predictors, CHOOSE from 27 were not significant (p > 0.05). An example of interpretation: with a unit change in the horsepower indicator, the price of CHOOSE is CHOOSE (without rounding).

#### Dataset:

cars.csv

##### Column descriptions

Data columns (total 26 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 1. car_ID            205 non-null    int64  
 2. symboling         205 non-null    int64  
 3. CarName           205 non-null    object 
 4. fueltype          205 non-null    object 
 5. aspiration        205 non-null    object 
 6. doornumber        205 non-null    object 
 6   carbody           205 non-null    object 
 7   drivewheel        205 non-null    object 
 8   enginelocation    205 non-null    object 
 9   wheelbase         205 non-null    float64
 10  carlength         205 non-null    float64
 11  carwidth          205 non-null    float64
 12  carheight         205 non-null    float64
 13  curbweight        205 non-null    int64  
 14  enginetype        205 non-null    object 
 15  cylindernumber    205 non-null    object 
 16  enginesize        205 non-null    int64  
 17  fuelsystem        205 non-null    object 
...
 25  price             205 non-null    float64
dtypes: float64(8), int64(8), object(10)

## Task 3: Laboratory work #3

Description of the experiment
Before you is a table with the results of the experiment. You need to assess whether there are statistically significant differences between the control and test groups.

value experimentVariant
1 10.3804953740268 Control
2 9.54686666784264 Control
3 11.0882146509904 Control
4 10.1472740570122 Control
5 9.78980767524929 Control
... ... ...
996 1000 Treatment
997 1200 Treatment
998 1500 Treatment
999 2000 Treatment
1000 3000 Treatment
1000 rows × 2 columns

Description of variables:

1. value - the value of the metric
2. experimentVariant - Test variant (Control - control, Treatment - test)

Task
1. Compare the result between the test and the control for the two cases:
2. Apply the bootstrap (by mean) and the Mann-Whitney U-test , then compare the p-value
3. Apply the bootstrap (by median) and the Mann-Whitney U-test and then compare the p-value.
4. Create appropriate visualizations, write conclusions that can be drawn based on the analysis of the applied criteria

## Task 4: Laboratory work #4

Task description
A/A testing of a mobile application.

It is necessary to calculate the results of the A/A test, checking the FPR quality metric (we will check for conversions to purchases). It is known that the split system is broken.

It is necessary to check the claim about the breakdown and find its reasons, if the split system is really broken.

uid experimentVariant version purchase
1 c4ca4238a0b923820dcc509a6f75849b 1 v2.8.0 0
2 c81e728d9d4c2f636f067f89cc14862c 0 v2.9.0 0
3 eccbc87e4b5ce2fe28308fd9f2a7baf3 1 v2.9.0 0
4 a87ff679a2f3e71d9181a67b7542122c 1 v2.8.0 0
5 e4da3b7fbbce2345d7772b0674a318d5 1 v2.8.0 0
... ... ... ... ...
127014 d1f082ede77b17a99a9b0b240daf7bdf 0 v2.8.0 0
127015 94f0d540830ccdc6b29c1938eea445cc 0 v2.8.0 0
127016 709f74cf9721328e98be6f216e8a05a8 1 v2.9.0 0
127017 1767ae3f8ffec269d9ed0ac0ede68d90 1 v2.8.0 0
127018 8dd8503c49b5e8c6aaea1ed7f0c49765 1 v2.8.0 0
127018 rows × 4 columns

Description of columns
uid - user ID
experimentVariant - experiment variant
version - version of the application
purchase - the fact of purchase
Task
Run an A/A test.
Calculate the FPR on the level
 = 0.05 (put subsamples without return with a volume of 1000). You will see that
! We need the opposite - to be less.
Find the reasons for the breakdown of the split system based on the results of the experiment (hint: find the anomaly in the application version).
Write the conclusions that can be drawn based on the analysis of the results of the A/A test.

## Task 5: Laboratory work #5

There is data about a taxi company that wants to study driver churn and see what the differences are between drivers who leave the service and those who stay. It is necessary to formulate and test hypotheses, to identify groups of drivers who are most prone to "drain". Based on the results, draw conclusions about what can be improved in the service in order to make changes in the future.

Data description
city ​​- a city
phone - the main device used by the driver
signup_date - account registration date (YYYYMMDD)
last_trip_date - date of the last trip (YYYYMMDD)
avg_dist - average distance (in miles) per trip in the first 30 days after registration
avg_rating_by_driver - average rating of trips by driver
vg_rating_of_driver - average rating of the driver's trips
surge_pct - percentage of trips made with a multiplier > 1 (appears when there is a lot of traffic, etc.)
avg_surge - average surge multiplier for all trips of this driver
trips_in_first_30_days - the number of trips made by the driver in the first 30 days after registration
luxury_car_user - TRUE if the user used a premium car in the first 30 days
weekday_pct - percentage of user trips made on weekdays
Importantly
If more than 30 days have passed since the last trip, the driver is considered to have stopped using the service (new variable churn): days are counted from the maximum date of the last trip in the data (last_trip_date).

Issues to be resolved:
Check whether there are differences in customer churn rates in different cities (churn, city)
Is there a difference in activity in the first 30 days from the moment of registration between drivers from different cities? (city, trips_in_first_30_days)
Can churn be related to activity in the first 30 days after signing up? (churn, trips_in_first_30_days)
