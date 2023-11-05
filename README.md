# Welcome to Solar Radiance Forecaster

> **Note for Stakeholders and Interested Parties**:
This README provides an executive summary of the Solar Radiance Forecaster project. For an in-depth analysis and comprehensive project details, please request the full report. Additionally, for advanced, real-time forecasting solutions with higher granularity (up to 30-minute intervals) and cutting-edge methodologies, feel free to reach out to me via [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar) for a tailored approach to meet your specific requirements.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Methodology](#methodology)
3. [Results and Insights](#results-and-insights)
4. [Recommendations and Future Work](#recommendations-and-future-work)
5. [Acknowledgments and Contact](#acknowledgments-and-contact)
6. [License](#license)

---

## <a name="introduction"></a>1. Introduction

Solar energy is a critical component of the global renewable energy portfolio. Effective solar radiation forecasting is vital for optimizing the utilization of this renewable resource and ensuring efficient grid management. This repository represents a benchmark in applying data science rigor and innovative algorithms to address the challenges of short-term solar radiation forecasting.

For comprehensive analysis, please refer to the [project Wiki](https://github.com/solaripynb/SolarRadianceForecaster/wiki).

### 1.1 Project Overview

The SolarRadianceForecaster is an advanced predictive analytics platform, designed with machine learning algorithms to accurately forecast solar radiation in the short-term. Focused on the South Spain region, the model is optimized for a 60-minute forecast horizon, providing critical information to facilitate real-time decision-making in solar grid operations.

### 1.2 Objective

The core objective is to deliver high-precision forecasts of solar radiation for the upcoming 60 minutes. This enables stakeholders to make data-driven decisions for real-time grid balancing, thereby enhancing the efficiency and sustainability of solar energy utilization.

### 1.3 Target Audience

This project is designed to benefit a broad range of stakeholders, including solar grid operators, solar farms and energy companies, energy regulators and policymakers, and researchers and data scientists in the renewable energy forecasting domain.

### 1.4 Real-world Applications

- **Grid Stability**: Provides accurate solar radiation forecasts to maintain a balanced electricity grid.
- **Energy Storage Management**: Enhances energy storage systems' efficiency through optimal charging and discharging strategies.
- **Operational Excellence**: Enables dynamic solar panel adjustments for optimal energy capture at solar farms.
- **Risk Mitigation**: Offers crucial data for contingency planning during adverse weather conditions.

---

## <a name="methodology"></a>2. Methodology

### 2.1 Data Collection and Preprocessing

Data from the Photovoltaic Geographical Information System (PVGIS) has been utilized, involving preprocessing steps such as time alignment, anomaly detection, type validation, feature engineering, and data imputation.
    
### 2.2 Exploratory Data Analysis

Visual and statistical analyses were conducted, including time-series visualization, distribution plots, correlation matrices, and statistical testing to ensure the data's quality and readiness for model training.

---

![Average Beam Irradiance Heatmap (Hour of Day vs  Day of Week)](https://github.com/solaripynb/SolarRadianceForecaster/assets/148157132/96d2b61c-db2d-4102-ab60-2d550f8a1e47)

*Figure 1: The heatmap of Average Beam Irradiance displays the interaction between the time of day and the day of the week, revealing peak solar radiation periods and consistent weekly patterns. This visualization is pivotal in understanding when solar energy is most abundant and could inform grid operators about expected energy supply variations throughout the week.*

![Daily Profiles of Solar Irradiance](https://github.com/solaripynb/SolarRadianceForecaster/assets/148157132/7ba16770-c42c-4110-8524-6f397598ff28)

*Figure 2: The Daily Profiles of Solar Irradiance graph illustrates the typical cycle of solar energy availability throughout the day. It showcases the average irradiance values from sunrise to sunset, highlighting the midday peak and allowing for a detailed understanding of daily energy production potential.*

![Monthly Boxplots of Beam Irradiance (Gb(i)](https://github.com/solaripynb/SolarRadianceForecaster/assets/148157132/f32e752d-bc8b-49e6-a698-d5f4109a3cfc)

*Figure 3: Monthly Boxplots of Beam Irradiance offer a granular view of the data's distribution across different months. They highlight the central tendency and variability within each month, demonstrating the seasonal influence on solar radiation. Outliers are also evident, which may indicate anomalous days with unusual weather conditions.*

---

### 2.3 Modeling Approach

- **Model Selection:** Random Forest, Gradient Boosting, and LSTM networks were chosen for their strengths in handling different aspects of the data.
- **Model Training:** Hyperparameter tuning was performed to optimize the models' performance.
- **Performance Metrics:** Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the Coefficient of Determination (R2R2) were used to evaluate the models.
- **Validation Strategy:** Time-series cross-validation techniques were utilized to assess model robustness.

---

## <a name="results-and-insights"></a>3. Results and Insights

### 3.1 Model Evaluation Summary

- **Tree-Based Models:** Random Forest and Gradient Boosting models demonstrated strong predictive performance.
- **LSTM:** Offered insights into temporal dynamics and could benefit from further optimization.
- **Cross-Validation:** Reinforced the models' stability and generalizability.

### 3.2 Key Findings and Implications

- **Feature Significance:** Certain features related to global radiation were significant predictors.
- **Anomaly Handling:** Effective methodology ensured robust predictions.
- **Operational Decision-Making:** The models' accuracy suggests potential for real-time application.
- **Policy and Planning:** Insights from this study can inform policy decisions regarding solar energy integration.

---

## <a name="recommendations-and-future-work"></a>4. Recommendations and Future Work

### 4.1 Strategies for Improvement

To push the boundaries of solar radiation forecasting, the following strategies are recommended:

- **Algorithmic Enhancement:** Explore ensemble methods and advanced architectures for improved forecasting accuracy.
- **Feature Expansion:** Consider incorporating additional meteorological and atmospheric features.
- **Hyperparameter Optimization:** Continue refining the models for enhanced performance.
    
### 4.2 Limitations

- **No Real-time Validation**: The models have yet to be tested in a real-time operational environment.
- **Model Generalizability:** The performance in other regions or under different conditions is unknown.
- **Computational Resources:** The requirement for substantial computational power may limit accessibility.
    
### 4.3 Potential Future Directions

- **Real-Time Forecasting:** Develop systems capable of processing data and updating forecasts dynamically.
- **Geographical Expansion:** Validate the models across various regions to understand spatial variability.
- **Integration with Energy Systems:** Combine solar radiation forecasts with models of energy demand and production.

---

## <a name="acknowledgments-and-contact"></a>5. Acknowledgments and Contact

### 5.1 Acknowledgments

Gratitude is extended to all contributors, especially the team at PVGIS-SARAH2, for their foundational work in solar radiation. The scientific and open-source communities have also played a crucial role in enabling this project.

### 5.2 Contact for Further Information

For inquiries or discussions about collaboration, please reach out through [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar).

---

## <a name="license"></a>6. License

This project is licensed under the MIT License.
