# Solar Radiance Forecaster - Spain
---
> **Note for Stakeholders and Interested Parties**:
The information outlined in this README serves as a concise summary of the foundational solar radiation forecasting model. If your requirements necessitate more advanced capabilities, such as higher time granularity forecasts up to 30-minute intervals or the application of the latest forecasting techniques, I invite you to reach out to me directly for a customized solution. You can connect with me on [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar)
---

### Table of Contents
1. [Introduction](#introduction)
2. [Data](#data)
3. [Exploratory Data Analysis](#exploratory-data-analysis)
4. [Feature Engineering](#feature-engineer)
5. [Models](#models)
6. [Evaluation](#evaluation)
7. [Feature Importance](#feature-importance)
8. [Summary](#summary)
9. [Conclusion](#conclusion)
10. [Recommendations](#recommendations) 
11. [Limitations](#limitations)
12. [Acknowledgments](#acknowledgments)
13. [License](#license)

---

### <a name="introduction"></a>1. Introduction

Solar energy is an increasingly important part of the global energy mix. Accurate forecasting of solar radiation is essential for efficient grid management and maximizing the utilization of renewable energy. This repository provides various machine learning models to forecast solar radiation in South Spain, optimized for high accuracy and reliability.

---

### <a name="data"></a>2. Data

- Source: PVGIS-SARAH2, European Union, 2001-2023
- Features: Solar irradiance (Gb(i), Gd(i), Gr(i)), Sun height, Temperature, Wind speed, etc.
- Time Coverage: 2012-2020
- Meta-Data: Geographic and solar panel characteristics

---

### <a name="exploratory-data-analysis"></a>3. Exploratory Data Analysis (EDA)

Certainly, adding a dedicated section to describe the Exploratory Data Analysis (EDA) and Feature Engineering processes can provide valuable context for those who visit your repository. Here's how you might include that information in your README file:

#### Summary Statistics

- The dataset variables exhibit varying scales and distributions. For instance, the beam irradiance `Gb(i)` has a mean value of approximately \(236.28 \, \text{W/m}^2\) and a standard deviation of \(320.83 \, \text{W/m}^2\).
- The 2-m air temperature `T2m` varies from \(-3.98^\circ \text{C}\) to \(42.23^\circ \text{C}\), with a mean of \(16.08^\circ \text{C}\).

#### Missing Values

- The dataset has the advantage of containing no missing values, facilitating a smoother modeling process.

#### Data Distributions

- Variables like `Gb(i)`, `Gd(i)`, `Gr(i)`, and `H_sun` contain a significant number of zero values, likely corresponding to nighttime or cloudy conditions.
- Variables `T2m` and `WS10m` exhibit a nearly normal distribution.

---

###  <a name="feature-engineer"></a>4. Feature Engineering

#### Lagged Features

- Lagged variables for 1, 3, and 6 time steps were created for `Gb(i)`, `Gd(i)`, `Gr(i)`, `H_sun`, `T2m`, and `WS10m`.

#### Temporal Features

- Extracted temporal features such as the hour of the day, day of the week, month, and quarter from the timestamp.

#### Cloudiness Indicator

- A feature to indicate cloudy conditions was engineered based on a sudden drop in the variables `Gb(i)`, `Gd(i)`, and `Gr(i)`.

#### Moving Averages

- Rolling means with windows of 3 and 6 were generated for the irradiance and meteorological variables.

#### Historical Values

- Included historical values from one and two days prior, considering the 10-minute intervals (144 and 288 steps, respectively).

#### Cyclical Features

- Sine and cosine transformations of the hour, day of the week, month, and quarter were created to capture the cyclical nature of these temporal variables.

---

###  <a name="models"></a>5. Models

1. **Random Forest**: A bagging ensemble method that performs well on this dataset.
2. **XGBoost**: A boosting algorithm known for high performance in structured datasets.
3. **GradientBoostingRegressor**: Another boosting algorithm tested for this problem.
4. **LSTM**: A deep learning model designed to capture long-term dependencies in sequence data.

---

###  <a name="evaluation"></a>6. Evaluation

The models are evaluated based on the following metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- \( R^2 \) Score

---

###  <a name="feature-importance"></a>7. Feature Importance

Feature importance is evaluated for tree-based models to understand which variables most significantly influence predictions. This is crucial for model interpretability and further refinement.

---

###  <a name="summary"></a>8. Summary

1. **Tree-based Models**: Random Forest, XGBoost, and GradientBoostingRegressor models performed exceptionally well, with high \( R^2 \) scores and low error metrics (MAE, MSE, RMSE) on both validation and test sets.
  
2. **LSTM Model**: Despite its capability to capture long-term dependencies, the LSTM model didn't perform as well as the tree-based models in terms of MAE.

3. **Feature Importance**: Features like rolling means and sudden drops in solar irradiance (`Gb(i)_drop`) were consistently important across multiple models, suggesting these features capture crucial aspects of solar radiation.

4. **Statistical Testing**: T-tests generally failed to reject the null hypothesis, adding a layer of statistical validation to the models' performance.

---

###  <a name="conclusion"></a>9. Conclusion

The project successfully developed predictive models for solar radiation forecasting with high accuracy. Among the models tested, tree-based models like Random Forest and XGBoost stood out as the most effective.

---

###  <a name="recommendations"></a>10. Recommendations

1. **Opt for Tree-based Models**: Given their performance, tree-based models are recommended for operational deployment.
  
2. **Feature Engineering**: Continue to explore other features that could capture cloud movement or other atmospheric conditions to enhance the model further.
  
3. **Hyperparameter Tuning**: For deployment, hyperparameter tuning should be performed to optimize the model's performance further.

---

###  <a name="limitations"></a>11. Limitations

1. **Lack of Cloud Cover Data**: Cloud cover could provide valuable information but was not available in the dataset.
  
2. **Model Interpretability**: LSTM models are generally more difficult to interpret compared to tree-based models.
  
3. **Computational Cost**: Models like XGBoost and Random Forest can be computationally expensive to train on very large datasets.

4. **No Real-time Validation**: The models were not validated in a real-time operational setting, which is the ultimate test of their utility.

By addressing these limitations and following the recommendations, the predictive models can be further optimized for practical, real-world applications in solar energy forecasting.

---

###  <a name="acknowledgments"></a>12. Acknowledgments

Dataset: PVGIS-SARAH2, European Union, 2001-2023

---

###  <a name="license"></a>13. License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
