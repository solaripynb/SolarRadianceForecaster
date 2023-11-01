# Solar Radiance Forecaster - Spain
---
> **Note for Stakeholders and Interested Parties**:
The information provided in this README serves as an executive summary of the Solar Radiance Forecaster project. For more advanced, real-time forecasting solutions, including higher granularity up to 30-minute intervals or cutting-edge forecasting methodologies, you are invited to connect with me directly on [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar) for a tailored approach to meet your specific requirements.
---

## Table of Contents
1. [Introduction](#introduction)
2. [Data Collection and Preprocessing](#data)
3. [Exploratory Data Analysis](#exploratory-data-analysis)
4. [Modeling](#modeling)
5. [Model Evaluation](#model-evaluation)
6. [Insights](#insights)
7. [Recommendations](#recommendations)
8. [Limitations](#limitations)
9. [Future Work](#future-work)
10. [Acknowledgments](#acknowledgments) 
11. [License](#license)
12. [Contact](#contact)

---

## <a name="introduction"></a>1. Introduction

Solar energy is a critical component of the global renewable energy portfolio. Effective solar radiation forecasting is vital for optimizing the utilization of this renewable resource and ensuring efficient grid management. This repository represents a benchmark in applying data science rigor and innovative algorithms to address the challenges of short-term solar radiation forecasting.

### 1.1 Project Overview

The SolarRadianceForecaster is an advanced predictive analytics platform, designed with machine learning algorithms to accurately forecast solar radiation in the short-term. Focused on the South Spain region, the model is optimized for a 60-minute forecast horizon, providing critical information to facilitate real-time decision-making in solar grid operations.

### 1.2 Objective

The core objective is to deliver high-precision forecasts of solar radiation for the upcoming 60 minutes. This enables stakeholders to make data-driven decisions for real-time grid balancing, thereby enhancing the efficiency and sustainability of solar energy utilization.

### 1.3 Target Audience

This project is designed to benefit a broad range of stakeholders, including:

- **Solar Grid Operators**: For real-time electricity supply and demand management.
- **Solar Farms and Energy Companies**: To maximize energy capture and storage efficiencies.
- **Energy Regulators and Policymakers**: For data-driven decision-making on solar energy integration and policy formulation.
- **Researchers and Data Scientists**: Seeking reliable models for renewable energy forecasting.

### 1.4 Real-world Applications

- **Grid Stability**: Assists in maintaining a balanced and stable electricity grid by providing accurate solar radiation forecasts.
- **Energy Storage Management**: Enhances the efficiency of energy storage systems through optimal charge and discharge cycles.
- **Operational Excellence**: Facilitates advanced operational strategies for solar farms, like dynamic solar panel adjustments for optimal energy capture.
- **Risk Mitigation**: Provides crucial data for contingency planning during adverse weather conditions, minimizing operational risks.

---

## <a name="data"></a>2. Data Collection and Preprocessing

### 2.1 Data Sources - PVGIS (c) European Union, 2001-2023

The dataset used for this project is sourced from the Photovoltaic Geographical Information System (PVGIS), which is a reliable and comprehensive database supported by the European Union. The data provides key metrics such as Global Beam Irradiance (Gb(i)), Global Diffuse Irradiance (Gd(i)), and Global Reflected Irradiance (Gr(i)), along with additional meteorological variables like temperature, wind speed, and solar elevation angle.

### 2.2 Data Cleaning

The initial dataset underwent rigorous cleaning processes, including:

- **Time Alignment**: Ensured that all time series data is aligned in uniform time intervals.
- **Outliers**: Anomaly detection was performed using Z-Score and Tukey Fences methods. Specifically, 680 and 381 anomalies were detected for the `Gd(i)` feature using these methods.
- **Data Types**: Ensured that all columns are of the appropriate data type.

### 2.3 Feature Engineering

To improve the model's predictive capabilities, several new features were engineered:

- **Lagged Features**: Variables like `Gb(i)`, `Gd(i)`, and `Gr(i)` were lagged at 1, 3, and 6 time intervals.
- **Temporal Features**: Hour of the day, day of the week, month, and quarter were extracted.
- **Moving Averages**: 3-period and 6-period moving averages were calculated for key features.
- **Historical Values**: Past day values for the same time were incorporated.
- **Cyclical Features**: Sinusoidal transformations were applied to capture cyclical patterns in hours and days.

### 2.4 Data Imputation

For the anomalies detected in the `Gd(i)` feature, data imputation was performed using the median of the dataset. The median was chosen over the mean for its resistance to outliers. After imputation, the dataset was verified to contain no missing or infinite values.

---

## <a name="exploratory-data-analysis"></a>3. Exploratory Data Analysis (EDA)

### 3.1 Time-Series Plotting

Two types of time-series plotting techniques were used:

- **Temporal Trends**: Time-series graphs of `Gb(i)`, `Gd(i)`, and `Gr(i)` were plotted to understand underlying patterns, trends, and seasonality.
- **Hourly/Daily/Monthly Profiles**: The data were aggregated to hourly, daily, and monthly intervals to visualize diurnal, weekly, and seasonal patterns.

### 3.2 Distribution Analysis

To understand the statistical properties of the data, the following analyses were conducted:

- **Histograms and Density Plots**: These were created for each variable, especially the newly engineered features, to understand their distribution.
- **Box Plots**: These plots were used to understand the spread, skewness, and identify outliers in the dataset.

### 3.3 Correlation Analysis

Correlation between variables was assessed through:

- **Heatmap**: A heatmap was generated to identify highly correlated variables.
- **Pair Plots**: Scatter plots for selected pairs of features were created to visualize relationships.

### 3.4 Statistical Tests

Two types of statistical tests were applied:

- **Stationarity Tests**: Augmented Dickey-Fuller tests were conducted on `Gb(i)`, `Gd(i)`, and `Gr(i)`, confirming stationarity in these variables.
- **Normality Tests**: D'Agostino and Pearson's tests confirmed that the distributions of `Gb(i)`, `Gd(i)`, and `Gr(i)` were not normal, indicating the need for transformations if parametric methods are to be applied.

### 3.5 Anomaly Detection

Anomalies were identified using:

- **Z-Score and Tukey Fences**: Anomalies were detected predominantly in the `Gd(i)` feature. The data points identified as anomalies were imputed with the median value of the respective variable.

---

##  <a name="modeling"></a>4. Modeling

### 4.1 Random Forest

The Random Forest model was selected for its ability to capture complex relationships in the data. It was trained with 100 trees.

**Performance Metrics on Validation Set:**
- MAE: 9.13
- MSE: 576.40
- RMSE: 24.01
- \( R^2 \): 0.995

**Performance Metrics on Test Set:**
- MAE: 9.80
- MSE: 620.34
- RMSE: 24.91
- \( R^2 \): 0.994

**Most Important Features:**
- `Gr(i)`
- `Gb(i)_ma3`
- `Gd(i)`

### 4.2 XGBoost

The XGBoost model was trained with 100 estimators and a learning rate of 0.1.

**Performance Metrics on Validation Set:**
- MAE: 9.36
- MSE: 472.78
- RMSE: 21.74
- \( R^2 \): 0.996

**Performance Metrics on Test Set:**
- MAE: 9.75
- MSE: 477.64
- RMSE: 21.85
- \( R^2 \): 0.995

**Most Important Features:**
- `Gr(i)`
- `Gb(i)_ma3`
- `Gd(i)_ma6`

### 4.3 Gradient Boosting Regressor

The Gradient Boosting Regressor model was trained with 100 estimators and a learning rate of 0.1.

**Performance Metrics on Validation Set:**
- MAE: 18.99
- MSE: 1612.02
- RMSE: 40.15
- \( R^2 \): 0.985

**Performance Metrics on Test Set:**
- MAE: 19.89
- MSE: 1730.23
- RMSE: 41.60
- \( R^2 \): 0.983

**Most Important Features:**
- `Gr(i)`
- `Gb(i)_ma3`
- `Gd(i)`

### 4.4 Long Short-Term Memory (LSTM)

The LSTM model was implemented using TensorFlow's Keras API. The model consisted of one LSTM layer with 50 units followed by a dense layer. It was trained for 50 epochs with a batch size of 72.

**Performance Metrics on Validation Set:**
- MAE: 23.02

---

##  <a name="model-evaluation"></a>5. Model Evaluation

### 5.1 Metrics Used

Four key metrics were used to evaluate the performance of the models:

1. **Mean Absolute Error (MAE)**: Represents the average absolute difference between the observed actual outcomes and the predictions made by the model.
2. **Mean Squared Error (MSE)**: Measures the average of the squares of the errors—that is, the average squared difference between the estimated values and the actual value.
3. **Root Mean Squared Error (RMSE)**: The square root of MSE. It has the benefit of being in the same unit as the response variable.
4. **Coefficient of Determination (\( R^2 \))**: Represents the proportion of the variance for the dependent variable that's explained by the independent variables in the model.

### 5.2 Model Comparison

Here's a summary of the performance metrics for each model:

| Model                    | MAE (Validation) | MSE (Validation) | RMSE (Validation) | \( R^2 \) (Validation) | MAE (Test) | MSE (Test) | RMSE (Test) | \( R^2 \) (Test) |
|--------------------------|------------------|------------------|-------------------|------------------------|------------|------------|-------------|------------------|
| Random Forest            | 9.13             | 576.40           | 24.01              | 0.995                  | 9.80       | 620.34     | 24.91       | 0.994            |
| XGBoost                  | 9.36             | 472.78           | 21.74              | 0.996                  | 9.75       | 477.64     | 21.85       | 0.995            |
| Gradient Boosting        | 18.99            | 1612.02          | 40.15              | 0.985                  | 19.89      | 1730.23    | 41.60       | 0.983            |
| LSTM                     | 23.02            | N/A              | N/A                | N/A                    | N/A        | N/A        | N/A         | N/A              |

### 5.3 Statistical Significance

A t-test was conducted to determine whether the means of the predicted and actual values are statistically different.

- For Random Forest, XGBoost, and Gradient Boosting, the p-value was greater than 0.05, failing to reject the null hypothesis. This suggests that the means of the predicted and actual values are not statistically different, affirming the model's accuracy.
- For LSTM, statistical testing was not conducted due to the model's different nature and evaluation metric (MAE only).

---

##  <a name="insights"></a>6. Insights

### 6.1 Key Findings

1. **Model Performance**: The Random Forest and XGBoost models showed exceptional performance with an \( R^2 \) value exceeding 0.99 on both validation and test sets. These models are highly accurate and suitable for solar radiation forecasting.
  
2. **Feature Importance**: The 'Gr(i)' feature, representing global radiation, showed the highest importance across all tree-based models. This indicates its pivotal role in forecasting solar radiation.

3. **Statistical Significance**: T-tests conducted for tree-based models showed that the means of the predicted and actual values are not statistically different, affirming the models' accuracy.

4. **Anomaly Handling**: Outliers in the 'Gd(i)' feature were effectively handled using median-based imputation, ensuring robustness in the models.

5. **LSTM Limitations**: The LSTM model showed a higher MAE compared to other models, indicating room for improvement in neural network-based approaches.

### 6.2 Implications

1. **Operational Efficiency**: Accurate forecasting can significantly improve the efficiency of solar grid operations, aiding in real-time decision-making.

2. **Resource Allocation**: Knowing the solar irradiance in advance can help in optimal allocation of energy resources, thereby reducing wastage.

3. **Financial Benefits**: Improved forecasting can lead to better financial planning and pricing strategies for solar energy.

---

##  <a name="recommendations"></a>7. Recommendations

1. **Model Deployment**: Considering its high accuracy and reliability, the Random Forest model is recommended for immediate deployment.
  
2. **Real-time Anomaly Detection**: Implement a real-time anomaly detection and imputation system to maintain the model's performance.

3. **User Interface**: Develop a user-friendly interface that enables grid operators to easily understand and utilize the forecast data.

---

##  <a name="limitations"></a>8. Limitations

1. **No Real-time Validation**: The models were not validated in a real-time operational setting, which is the ultimate test of their utility.

2. **Computational Expense**: The Random Forest and XGBoost models, despite their high accuracy, can be computationally intensive.

3. **Data Dependency**: The models are highly dependent on the quality and quantity of the data. Any inconsistency in data collection can affect the performance.

4. **LSTM Performance**: The LSTM model did not perform as well as the tree-based models, indicating limitations in capturing the time-dependent nature of the data.

---

##  <a name="future-work"></a>9. Future Work

1. **Hyperparameter Tuning**: Further tuning of model parameters can be carried out for performance optimization.

2. **Inclusion of Additional Features**: Weather-related features like cloud cover could be included to improve the model.

3. **Ensemble Methods**: Combining the strengths of different models into an ensemble could provide even better results.

4. **Deep Learning Approaches**: More advanced neural network architectures can be experimented with for capturing complex patterns in the data.

5. **Expanding the Scope**: The model can be adapted for other geographic locations and different time horizons.

---

##  <a name="acknowledgments"></a>10. Acknowledgments

I would like to extend my deepest gratitude to everyone who contributed to the success of this project. Your expertise, feedback, and encouragement have been invaluable.

Special thanks go to the team of specialized scientists at PVGIS-SARAH2, funded by the European Union from 2001 to 2023. Your groundbreaking work in the field of solar radiation has laid the foundation for this project, and your collaboration has been a cornerstone in achieving the level of accuracy and reliability that this model provides.

I also want to acknowledge the broader scientific community for their continuous work in advancing our understanding of solar energy, as well as the open-source community for providing the tools that make projects like this possible.

Your contributions are not just powering this project; they are powering a more sustainable future for all.

---

##  <a name="license"></a>11. License

This project is licensed under the MIT License.

---

##  <a name="contact"></a>12. Contact

For any questions, feedback, or discussions, feel free to reach out to me:
- [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar)




