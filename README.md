# Solar Radiance Forecaster - Spain

## Description

This repository contains an ensemble machine learning model designed to forecast real-time solar radiation reaching solar farms in South Spain for intervals of 30 minutes and ahead. The project aims to assist Solar Grid Operators in the efficient balancing of supply and demand.

## Objective

To provide Solar Grid Operators with accurate solar radiation forecasts for the next 30 minutes and beyond, thereby enabling them to balance the grid efficiently.

## Table of Contents

1. [Datasets](#datasets)
2. [Methodology](#methodology)
3. [Modeling](#modeling)
4. [Evaluation](#evaluation)
5. [Results](#results)
6. [Conclusion](#conclusion)
7. [Limitations](#limitations)
8. [Future Work](#futureWork)
9. [License](#license)

## <a name="datasets"></a>1. Datasets

The project uses the following datasets:

- **SIS (Solar Incoming Surface radiation)**: The primary target variable for forecasting, measured in Wm−2.
- **SID (Solar Direct Irradiance)**: Provides information on the direct component of solar radiation.
- **DAL (Daylight)**: Useful for understanding the availability of visible light.

### Meta-Data

The data starts from January 1, 2015, and ends at October 21, 2023. All attributes conform to Climate and Forecast (CF) conventions.

## Methodology

The project adheres to a rigorous data science pipeline, which includes:

1. **Data Cleaning**: Conversion of time columns to datetime data types, sorting, and merging datasets.
2. **Feature Engineering**: Generation of lagged features, temporal elements, moving averages, and cyclical features.
3. **Data Splitting**: 70% training, 15% validation, and 15% test splits.
4. **Model Selection**: Evaluation of multiple machine learning models.
5. **Model Training**: Training the selected Gradient Boosting Regressor model.
6. **Model Evaluation**: Employing MAE, MSE, RMSE, R2, and cross-validation for thorough evaluation.
7. **Deployment**: Real-time forecasting using Flask and `render_template`.

## Modeling

The machine learning model used is a Gradient Boosting Regressor. It is trained on engineered features like:

- Lagged SIS values (`SIS_lag_1`, `SIS_lag_2`)
- Time since sunrise
- Time until sunset
- Moving averages (`short_term_avg`, `long_term_avg`)
- Cyclical features capturing time-based patterns (`hour_sin`, `hour_cos`)

## Evaluation

The model's performance is meticulously evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R-Squared (R2)
- Cross-Validation

## Results

Detailed results will be updated upon completion of the model evaluation phase.

## Conclusion

Insights and conclusions will be updated after the evaluation phase.

## Limitations

1. **Limited Datasets**: The model currently only uses SIS, SID, and DAL datasets. Other potentially useful datasets like weather conditions, cloud cover, or humidity levels have not been included.
  
2. **Geographical Focus**: The model is tailored for South Spain, limiting its applicability in other geographical areas with different solar irradiance characteristics.

3. **Short-term Forecasts**: While the model specializes in real-time, short-term forecasting (next 30 minutes and beyond), its performance for long-term forecasts has not been evaluated.

4. **Feature Engineering**: While extensive feature engineering has been performed, there may be other unexplored features that could improve the model's performance.

5. **External Factors**: The model doesn't account for unforeseen circumstances like equipment failure or sudden atmospheric changes, which could affect solar irradiance.

6. **Computational Requirements**: The model uses ensemble methods, which may require significant computational resources for training and prediction, potentially limiting its real-time applicability on low-resource devices.

## <a name="futureWork"></a>8. Future Work

1. **Incorporate Additional Datasets**: Include weather-related datasets like temperature, cloud cover, and humidity to improve the model's accuracy.

2. **Long-term Forecasting**: Extend the model for long-term forecasting and assess its performance.

3. **Optimization**: Explore hyperparameter tuning and feature selection methods to enhance model performance.

4. **Real-Time Data Ingestion**: Implement a real-time data pipeline to continuously update the model with new data for improved accuracy.

5. **Geographical Expansion**: Adapt the model for different geographical areas and evaluate its performance.

6. **Deployment Scalability**: Optimize the model and its deployment setup for scalability, to handle higher volumes of queries.

7. **User Interface Enhancements**: Improve the UI/UX of the deployed model for easier usage by grid operators.


## License

The data are owned by EUMETSAT and are available to all users free of charge. EUMETSAT's copyright credit must be displayed. [More about the license](https://doi.org/10.5676/EUM_SAF_CM/SARAH/V003).

## Contact

For more details, please contact [DE/DWD](mailto:contact.cmsaf@dwd.de).
