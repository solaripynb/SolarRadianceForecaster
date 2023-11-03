# Solar Radiance Forecaster - Spain

> **Note for Stakeholders and Interested Parties**:
> The information provided in this README serves as an executive summary of the Solar Radiance Forecaster project. For more advanced, real-time forecasting solutions, including higher granularity up to 30-minute intervals or cutting-edge forecasting methodologies, you are invited to connect with me directly on [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar) for a tailored approach to meet your specific requirements.
---

## Table of Contents
1. [Introduction](#introduction)
   - [Project Overview](#project-overview)
   - [Objective](#objective)
   - [Target Audience](#target-audience)
   - [Real-world Applications](#real-world-applications)
2. [Methodology](#methodology)
   - [Data Collection and Preprocessing](#data-collection-and-preprocessing)
   - [Exploratory Data Analysis](#exploratory-data-analysis)
   - [Modeling Approach](#modeling-approach)
3. [Results and Insights](#results-and-insights)
   - [Model Evaluation Summary](#model-evaluation-summary)
   - [Key Findings and Implications](#key-findings-and-implications)
4. [Recommendations and Future Work](#recommendations-and-future-work)
   - [Strategies for Improvement](#strategies-for-improvement)
   - [Limitations](#limitations)
   - [Potential Future Directions](#potential-future-directions)
5. [Acknowledgments and Contact](#acknowledgments-and-contact)
   - [Acknowledgments](#acknowledgments)
   - [Contact for Further Information](#contact-for-further-information)
6. [License](#license)

---

## <a name="introduction"></a>1. Introduction

Solar energy is a critical component of the global renewable energy portfolio. Effective solar radiation forecasting is vital for optimizing the utilization of this renewable resource and ensuring efficient grid management. This repository represents a benchmark in applying data science rigor and innovative algorithms to address the challenges of short-term solar radiation forecasting.

### <a name="project-overview"></a>1.1 Project Overview

The SolarRadianceForecaster is an advanced predictive analytics platform, designed with machine learning algorithms to accurately forecast solar radiation in the short-term. Focused on the South Spain region, the model is optimized for a 60-minute forecast horizon, providing critical information to facilitate real-time decision-making in solar grid operations.

### <a name="objective"></a>1.2 Objective

The core objective is to deliver high-precision forecasts of solar radiation for the upcoming 60 minutes. This enables stakeholders to make data-driven decisions for real-time grid balancing, thereby enhancing the efficiency and sustainability of solar energy utilization.

### <a name="target-audience"></a>1.3 Target Audience

This project is designed to benefit a broad range of stakeholders, including:

- **Solar Grid Operators**: For real-time electricity supply and demand management.
- **Solar Farms and Energy Companies**: To maximize energy capture and storage efficiencies.
- **Energy Regulators and Policymakers**: For data-driven decision-making on solar energy integration and policy formulation.
- **Researchers and Data Scientists**: Seeking reliable models for renewable energy forecasting.

### <a name="real-world-applications"></a>1.4 Real-world Applications

- **Grid Stability**: Assists in maintaining a balanced and stable electricity grid by providing accurate solar radiation forecasts.
- **Energy Storage Management**: Enhances the efficiency of energy storage systems through optimal charge and discharge cycles.
- **Operational Excellence**: Facilitates advanced operational strategies for solar farms, like dynamic solar panel adjustments for optimal energy capture.
- **Risk Mitigation**: Provides crucial data for contingency planning during adverse weather conditions, minimizing operational risks.

---

## <a name="methodology"></a>2. Methodology

### <a name="data-collection-and-preprocessing"></a>2.1 Data Collection and Preprocessing

Data Sources:
The data for this project was sourced from the Photovoltaic Geographical Information System (PVGIS), backed by the European Union. It provides vital solar radiation metrics and meteorological variables essential for our analysis.

Preprocessing Steps:
Data preprocessing involved several critical steps to ensure quality and consistency:

    Time Alignment: Adjustment of timestamps to a common format and frequency to maintain data continuity.
    Anomaly Detection: Identification of outliers using statistical techniques, such as Z-Score and Tukey's method, and subsequent remediation.
    Type Validation: Ensuring that all data columns adhere to their specified data types for accurate computations.
    Feature Engineering: Creation of additional data features, such as lagged variables, temporal attributes, and moving averages, to enhance model input.
    Data Imputation: Handling of missing values through robust imputation methods, ensuring a complete dataset for model training.
    
### <a name="exploratory-data-analysis"></a>2.2 Exploratory Data Analysis

Visual Analysis:

    Time-Series Visualization: To identify trends, seasonality, and patterns within the solar radiation data.
    Distribution Plots: To understand the underlying distribution of the data and identify potential skewness or kurtosis.

Statistical Analysis:

    Correlation Matrix: To uncover linear relationships between variables and prevent multicollinearity in the model.
    Statistical Testing: Application of tests like the Augmented Dickey-Fuller test to check for stationarity and the Shapiro-Wilk test for normality.

Anomaly Reassessment:

    Further scrutiny of detected anomalies and their impact on the dataset. Anomalies were addressed by imputation or exclusion, based on their nature and potential impact.
    
### <a name="modeling-approach"></a>2.3 Modeling Approach

Model Selection:

    Tree-Based Models: Random Forest and Gradient Boosting were chosen for their robustness in handling non-linear relationships and feature importance insights.
    Neural Networks: LSTM networks were employed to capture the temporal dependencies in the data, given the time-series nature of solar radiation.

Model Training:

    The models were trained on a historical dataset, with hyperparameter tuning performed to optimize their performance.

Performance Metrics:

    A range of metrics, including Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the Coefficient of Determination (R2R2), were used to evaluate model performance.

Validation Strategy:

    Cross-validation was employed to assess model robustness, with a specific focus on time-series cross-validation techniques given the sequential data structure.

Feature Importance Analysis:

    Post-training analysis was conducted to identify the most significant predictors and understand the driving factors behind the model's predictions.

Model Interpretability:

    Efforts were made to ensure model interpretability, with the use of tools and techniques that help explain the outcomes of complex models.

---

## <a name="results-and-insights"></a>3. Results and Insights

### <a name="model-evaluation-summary"></a>3.1 Model Evaluation Summary

Model Evaluation:
Each model was rigorously evaluated using a variety of metrics to determine its predictive accuracy and generalizability:

    Random Forest: Showcased strong performance with high R2R2 values and low error metrics on both the validation and test sets. The performance indicates the model's ability to capture the complex interactions in the data effectively.

    XGBoost: Performed comparably to the Random Forest, with slightly better error metrics. The model's gradient boosting framework provided a strong mechanism for handling the non-linear patterns in the dataset.

    Gradient Boosting Regressor: Although it had higher error metrics compared to Random Forest and XGBoost, it still maintained a reasonable R2R2 score, suggesting its usefulness as a potential model in an ensemble approach.

    LSTM: The LSTM model, while not outperforming tree-based models, did offer valuable insights into the temporal dynamics of the data. Further optimization and architectural adjustments could enhance its performance in future iterations.

The models were compared on the basis of Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and the Coefficient of Determination (R2R2). The evaluation highlighted the importance of selecting the right model based on the nature of the data and the specific use case.

Cross-Validation:
Cross-validation results aligned closely with the test set performance, reinforcing confidence in the model's stability and its capacity to generalize well to unseen data.

### <a name="key-findings-and-implications"></a>3.2 Key Findings and Implications

Findings:

    Feature Significance: The analysis revealed that certain features, particularly those related to global radiation, were consistently significant predictors across all models.
    Anomaly Handling: The project's methodology for identifying and managing anomalies proved to be effective, ensuring the robustness of the predictive models.
    Model Performance: The tree-based models, due to their ability to handle complex interactions between features, outperformed the LSTM model in terms of accuracy and reliability.

Implications:

    Operational Decision-Making: The high accuracy of the tree-based models suggests their potential for operational deployment, where real-time solar radiation predictions can significantly enhance decision-making processes.
    Resource Optimization: Accurate predictions can lead to better resource allocation, reducing waste and increasing efficiency in the use of solar energy.
    Policy and Planning: The insights from this study can inform policy decisions and strategic planning, particularly in the context of integrating solar energy into the broader energy mix.
    Research and Development: The findings underscore the importance of continued research into feature engineering and model optimization to further improve solar radiation forecasting.

---

## <a name="recommendations-and-future-work"></a>4. Recommendations and Future Work
### <a name="strategies-for-improvement"></a>4.1 Strategies for Improvement

4.1 Strategies for Improvement

To push the boundaries of solar radiation forecasting, the following strategies are recommended:

    Algorithmic Enhancement: Incorporating ensemble methods that combine the predictions from multiple models can potentially yield more accurate and robust forecasts. Techniques such as model stacking or blending can be explored to leverage the strengths of individual models.

    Feature Expansion: Introducing additional features such as atmospheric conditions, aerosol levels, and albedo effects could improve model performance. Additionally, exploring the inclusion of real-time satellite imagery as input could provide more nuanced predictions.

    Hyperparameter Optimization: Further tuning the hyperparameters of the existing models, especially for complex models like XGBoost and LSTM, could enhance their predictive capabilities.

    Model Interpretability: Implementing tools and techniques for better interpretability of the models can help stakeholders understand the prediction process, thereby increasing trust and facilitating easier adoption of the technology.
    
### <a name="limitations"></a>4.2 Limitations

The current project's limitations must be acknowledged to set realistic expectations and establish a framework for continuous improvement:

    Data Quality and Availability: The models are heavily reliant on the quality and completeness of the input data. Any inaccuracies or gaps in the data can significantly impact the results.

    Model Generalizability: While the models perform well on the dataset for South Spain, their performance on data from different geographical regions or under different climatic conditions has not been evaluated.

    Computational Resources: Some of the more complex models require substantial computational power, which might not be readily available in all operational settings.

    Temporal Resolution: The models currently provide forecasts on an hourly basis. Increasing the temporal resolution to provide more frequent forecasts could be beneficial but also more challenging due to the increased noise in the data.
    
### <a name="potential-future-directions"></a>4.3 Potential Future Directions

To ensure the continued evolution and relevance of the SolarRadianceForecaster project, the following future directions are proposed:

    Real-Time Forecasting: Moving towards a system that can process incoming data and update forecasts in real-time would be a significant advancement, allowing for more dynamic and responsive solar energy management.

    Deep Learning Architectures: Experimenting with advanced neural network architectures, such as Convolutional Neural Networks (CNNs) for image-based predictions and Recurrent Neural Networks (RNNs) for sequential data, might uncover patterns missed by current models.

    Geographical Expansion: Adapting and validating the models for different regions would increase their utility and provide insights into the spatial variability of solar radiation.

    Integration with Energy Systems: Combining solar radiation forecasts with models of energy demand and production could lead to the development of a more comprehensive energy management system.

    Climate Change Projections: Incorporating climate change projections into the models could provide valuable insights into the long-term trends of solar radiation and assist in strategic planning for energy infrastructure.

---

## <a name="acknowledgments-and-contact"></a>5. Acknowledgments and Contact

### <a name="acknowledgments"></a>5.1 Acknowledgments

The realization of the SolarRadianceForecaster project is a testament to collaborative effort and scientific exchange. I extend my deepest appreciation to:

    Scientific and Data Partners: The invaluable datasets and insights provided by entities like PVGIS and other open-source data repositories have been the foundation of this project's success.

    Academic Collaborators: Researchers and students who have contributed their expertise and innovative ideas to refine the forecasting models.

    Open-Source Community: Developers and contributors in the open-source community have created and maintained the tools that made the development of this project possible.

    Personal Network: Colleagues, mentors, and peers who have offered their support, constructive criticism, and encouragement throughout the development process.

Your collective contributions have not only propelled this project forward but also underscored the collaborative nature of scientific progress.

### <a name="contact-for-further-information"></a>5.2 Contact for Further Information

I am continually seeking to expand the horizons of this project and explore new partnerships that push the envelope of what's possible in solar energy forecasting. If you are interested in collaborating, contributing, or simply discussing the potential of this model and others in the energy sector, please feel free to reach out. Together, we can forge a path towards more sustainable and efficient energy solutions.

For inquiries, collaborations, or further discussions, please contact:

    [LinkedIn](https://www.linkedin.com/in/sergiodavidescobar)

Your interest and expertise could play a crucial role in shaping the next phase of this project, leading to innovative solutions that benefit the global community.

---
##  <a name="acknowledgments"></a>10. Acknowledgments

I would like to extend my deepest gratitude to everyone who contributed to the success of this project. Your expertise, feedback, and encouragement have been invaluable.

Special thanks go to the team of specialized scientists at PVGIS-SARAH2, funded by the European Union from 2001 to 2023. Your groundbreaking work in the field of solar radiation has laid the foundation for this project, and your collaboration has been a cornerstone in achieving the level of accuracy and reliability that this model provides.

I also want to acknowledge the broader scientific community for their continuous work in advancing our understanding of solar energy, as well as the open-source community for providing the tools that make projects like this possible.

Your contributions are not just powering this project; they are powering a more sustainable future for all.

---

## <a name="license"></a>6. License

This project is licensed under the MIT License.

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




