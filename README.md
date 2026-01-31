# Predicting Fuel Efficiency (MPG) of Cars

This project predicts the **Miles Per Gallon (MPG)** of cars using historical data from the Auto MPG dataset. It includes data cleaning, feature engineering, exploratory data analysis (EDA), model training, evaluation, and visualization.

## Project Overview

This project aims to predict fuel efficiency (MPG) of cars using historical data from the Auto MPG dataset. The workflow includes:

- Loading and cleaning the dataset  
- Handling missing values (`horsepower` column)  
- Creating new features such as `power_to_weight` (horsepower divided by weight), `displacement_per_cylinder`, `weight_acceleration`, and `car_age`  
- Exploratory Data Analysis (EDA) with plots for distributions, correlations, and outlier detection  
- Training Random Forest and XGBoost regression models  
- Evaluating model performance using **RMSE** and **R²**  
- Visualizing feature importance and predicted vs actual MPG  

## Dataset

The project uses the **Auto MPG dataset**, which contains **398 entries** of various car models from 1970 to 1982.

**Columns:**

| Column        | Description                           |
|---------------|---------------------------------------|
| mpg           | Fuel efficiency in miles per gallon   |
| cylinders     | Number of cylinders in the engine     |
| displacement  | Engine displacement (cubic inches)    |
| horsepower    | Engine horsepower                     |
| weight        | Vehicle weight (lbs)                  |
| acceleration  | Time to accelerate from 0 to 60 mph  |
| model year    | Year of the car (two digits)          |
| origin        | Origin of the car (1=USA, 2=Europe, 3=Japan) |
| car name      | Name of the car                        |

## Features

Derived features added for better prediction:

- `power_to_weight` = horsepower / weight  
- `displacement_per_cylinder` = displacement / cylinders  
- `weight_acceleration` = weight * acceleration  
- `model_year` = full year (e.g., 1970 instead of 70)  
- `car_age` = current year - model_year  

## Models Used

- **Random Forest Regressor** (200 trees, `random_state=42`)  
- **XGBoost Regressor** (300 estimators, learning rate 0.05, max_depth 4)  

## Results

| Model          | RMSE  | R² Score |
|----------------|-------|----------|
| Random Forest  | 2.40  | 0.89     |
| XGBoost        | 2.24  | 0.90     |

**Observation:** The XGBoost model performs slightly better in terms of RMSE and R².

