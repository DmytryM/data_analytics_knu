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

 0   name           8128 non-null   object 
 1   year           8128 non-null   int64  
 2   selling_price  8128 non-null   int64  
 3   km_driven      8128 non-null   int64  
 4   fuel           8128 non-null   object 
 5   seller_type    8128 non-null   object 
 6   transmission   8128 non-null   object 
 7   owner          8128 non-null   object 
 8   mileage        7907 non-null   object 
 9   engine         7907 non-null   object 
 10  max_power      7913 non-null   object 
 11  torque         7906 non-null   object 
 12  seats          7907 non-null   float64

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
 0   car_ID            205 non-null    int64  
 1   symboling         205 non-null    int64  
 2   CarName           205 non-null    object 
 3   fueltype          205 non-null    object 
 4   aspiration        205 non-null    object 
 5   doornumber        205 non-null    object 
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
