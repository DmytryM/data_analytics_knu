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

## Task 2: Laboratory work #2

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
