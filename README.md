# Solar Radiance Forecaster - Spain
---

#### Description
Machine learning models for forecasting solar radiation in solar farms in South Spain, optimized for balancing real-time supply and demand in solar grid operations.

---

### Table of Contents
1. [Introduction](#introduction)
2. [Data](#data)
3. [Models](#models)
4. [Exploratory Data Analysis](#exploratory-data-analysis)
5. [Evaluation](#evaluation)
6. [Feature Importance](#feature-importance)
7. [Contribution](#contribution)
8. [License](#license)

---

### <a name="introduction"></a>1. Introduction

The repository focuses on the real-world problem of forecasting solar radiation in South Spain. It aims to provide a robust, accurate, and reliable solution for solar grid operators to balance supply and demand in real-time.

---

### Data

- Source: PVGIS-SARAH2, European Union, 2001-2023
- Features: Solar irradiance (Gb(i), Gd(i), Gr(i)), Sun height, Temperature, Wind speed, etc.
- Time Coverage: 2012-2020
- Meta-Data: Geographic and solar panel characteristics

---

### Models

1. **Random Forest**: A bagging ensemble method that performs well on this dataset.
2. **XGBoost**: A boosting algorithm known for high performance in structured datasets.
3. **GradientBoostingRegressor**: Another boosting algorithm tested for this problem.
4. **LSTM**: A deep learning model designed to capture long-term dependencies in sequence data.

---

### <a name="exploratory-data-analysis"></a>4. Exploratory Data Analysis (EDA)

Comprehensive EDA is performed to understand the dataset's underlying structure and relationships. The insights from EDA are crucial for feature engineering, which includes generating lagged features, temporal features, and moving averages.

---

### Evaluation

The models are evaluated based on the following metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- \( R^2 \) Score

---

### Feature Importance

Feature importance is evaluated for tree-based models to understand which variables most significantly influence predictions. This is crucial for model interpretability and further refinement.

---

### Contribution

Please read the [CONTRIBUTION.md](CONTRIBUTION.md) for details on our code of conduct and the process for submitting pull requests.

---

### License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
