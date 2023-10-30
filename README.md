# SolarRadianceForecaster-Spain

## Description

This repository contains a machine learning model designed to forecast real-time solar radiation reaching solar farms in South Spain for intervals of 30 minutes and ahead.

## Objective

To assist Solar Grid Operators in balancing supply and demand in real-time by providing accurate solar radiation forecasts.

## Table of Contents

1. [Datasets](#datasets)
2. [Methodology](#methodology)
3. [Modeling](#modeling)
4. [Evaluation](#evaluation)
5. [Results](#results)
6. [Conclusion](#conclusion)
7. [Usage](#usage)
8. [License](#license)

## Datasets

The datasets used in this project include:

- SIS (Solar Incoming Surface radiation)
- SID (Solar Direct Irradiance)
- DAL (Daylight)

### Meta-Data

The data coverage starts from January 1, 2015, and ends at October 21, 2023. Further details about the dataset attributes are compliant with the Climate and Forecast (CF) conventions.

## Methodology

The project follows a structured data science pipeline:

1. Data Cleaning
2. Feature Engineering
3. Data Splitting
4. Model Selection
5. Model Training
6. Model Evaluation
7. Deployment

## Modeling

The machine learning model used is a Gradient Boosting Regressor, trained on features like lagged SIS values, time since sunrise, time until sunset, and cyclical features to capture time-based patterns.

## Evaluation

The model is evaluated using the following metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R-Squared (R2)
- Cross-Validation

## Results



## Conclusion



## Usage

Instructions on how to run the code and use the model for real-time forecasting.

## License

The data is owned by EUMETSAT, available to all users free of charge. [More about the license](https://doi.org/10.5676/EUM_SAF_CM/SARAH/V003).

## Contact

For more details, please contact [DE/DWD](mailto:contact.cmsaf@dwd.de).
