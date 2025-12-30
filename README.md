# Global Population Dynamics and Forecasting

📈 An end-to-end analysis of global population trends using World Bank data, focusing on long-term growth patterns, regional and income-group disparities, and population forecasting using statistical growth models and regression-based approaches.


## 📌 Overview

This project examines how global population has evolved over time and how demographic, economic, and migration-related factors influence population growth across countries.

The analysis combines exploratory data analysis, population growth theory, hypothesis testing, regression modeling, and forecast validation to better understand both historical patterns and near-term global population projections.

Key goals of the project include:
- Identifying countries with the largest population increases and declines
- Analyzing annual and instantaneous population growth rates
- Comparing growth patterns across regions and income groups
- Building and validating population growth and forecasting models


## 🗂️ Data Sources

All data were obtained from the **World Bank Group**:

- 🌐 Total Population  
  https://data.worldbank.org/indicator/SP.POP.TOTL
- 👶 Birth Rate  
  https://data.worldbank.org/indicator/SP.DYN.CBRT.IN
- ⚰️ Death Rate  
  https://data.worldbank.org/indicator/SP.DYN.CDRT.IN
- 🧑‍🤝‍🧑 Population Ages 15–64  
  https://data.worldbank.org/indicator/SP.POP.1564.TO.ZS
- 🌎 Net Migration  
  https://data.worldbank.org/indicator/SM.POP.NETM


## 🧹 Data Preparation

The datasets were cleaned and reshaped to support longitudinal and cross-country analysis:

- Converted wide-format World Bank indicators into long format
- Standardized column names and country identifiers
- Removed invalid and missing entries
- Validated country codes and region mappings
- Integrated population, demographic, migration, region, and income-group data

The final dataset supports country-level, regional, and income-group comparisons over time.


## 📊 Exploratory Data Analysis (EDA)

### 🌐 Global Trends
- World population increased steadily from 1960 to 2020
- Growth follows a near-linear trajectory at the global level
- Annual growth rates gradually decline over time

### 🏙️ Country-Level Patterns
- Rapid long-term growth observed in countries such as Saudi Arabia, UAE, Qatar, and Kuwait
- Sustained population decline in several Eastern European countries (e.g., Bulgaria, Ukraine, Latvia)
- In the last five years, population gains were highest in countries like Seychelles, Chad, and Oman

### 🌍 Regional Comparisons
- Highest growth rates consistently observed in:
  - Sub-Saharan Africa
  - Middle East & North Africa
  - South Asia
- Europe & Central Asia exhibits the lowest and often declining growth rates

### 💰 Income Group Analysis
- Low- and lower-middle-income countries maintain the highest growth rates
- High-income countries show slower, more stable growth
- Growth variability is higher in lower-income groups


## 📐 Population Growth Models

### 📈 Geometric Growth
- Annual growth rates interpreted as discrete compounding factors
- Long-term growth determined by geometric mean growth rates

### 📉 Exponential Growth
- Modeled population change using continuous instantaneous growth rates
- Demonstrated theoretical consistency between instantaneous rates and annual growth factors

A strong linear relationship was observed between instantaneous growth rates and the logarithm of annual growth rates, confirming population growth theory.


## 🤖 Statistical Modeling

### Linear Regression Model
- Modeled instantaneous growth rate as a function of:
  - Birth rate
  - Death rate
  - Net migration rate
  - Region
  - Income group
- Achieved **R² ≈ 0.73**, explaining most variation in growth rates
- Birth rate, death rate, and migration were the strongest predictors

### Extended Linear Model
- Included interactions between demographic variables and region/income group
- Improved model fit (**R² ≈ 0.755**)
- Captured nuanced regional and economic differences in population dynamics
- Introduced higher sensitivity to influential observations


## 🧪 Hypothesis Testing

- Welch two-sample t-test confirmed that **high-income countries have significantly higher net migration rates** than upper-middle-income countries
- Results support visual EDA findings with strong statistical significance (p < 0.001)


## 🔮 Population Forecasting

### Global Forecast (2024-2028)
- Projected world population increases from:
  - **7.88 billion (2023)** → **8.24 billion (2028)**
- Total increase of approximately **358 million people** over five years

### Model Validation
- Applied rolling-window cross-validation with forecast horizons of 1, 3, 5, 7, and 9 years
- **MAPE ≈ 0.33%** for 1-year forecasts
- Forecast error and underestimation increase with longer horizons
- Model performs well for short-term forecasting but becomes biased over longer periods


## 🔍 Key Findings

- Global population continues to grow, though growth rates are slowing
- Birth rate, death rate, and migration are primary drivers of population change
- Growth patterns differ substantially by region and income group
- Linear models fit historical data well but tend to underestimate long-term future population
- Forecast reliability declines as the prediction horizon increases


## ⚠️ Limitations

- Assumes stable demographic relationships over time
- Migration data quality varies across countries
- Extended models increase sensitivity to influential observations
- Linear assumptions do not fully capture nonlinear demographic dynamics
- Long-term forecasts are vulnerable to shocks (e.g., pandemics, conflicts)


## 🚀 Future Work

- Explore nonlinear and machine learning models (e.g., random forests, gradient boosting)
- Incorporate additional demographic indicators (fertility, life expectancy, education)
- Develop probabilistic forecasts with uncertainty intervals
- Perform scenario-based simulations using alternative growth assumptions
- Investigate dynamic models with time-varying parameters


## 🛠️ Tools and Technologies

- **Language:** R  
- **Libraries:** tidyverse, ggplot2, caret, regsubsets  
- **Methods:** EDA, population growth modeling, regression, hypothesis testing, forecasting, cross-validation


## 📄 Report

A detailed written report with figures, methodology, and validation results is included in this repository.

## ▶️ How to Run

### Prerequisites
- R (version 4.0 or later)
- RStudio (recommended)

### Install Required Packages

Install the required R packages if they are not already installed:

```r
install.packages(c(
  'tidyverse',
  'ggplot2',
  'caret',
  'leaps'
))
```
