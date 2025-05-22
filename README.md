# Analyzing the Relationship Between Weather Events and Traffic Accidents in NYC (2012-2023)

## Project Motivation
Traffic accidents are a major concern in large metropolitan areas like New York City. Weather conditions, such as heavy rain, snow, or extreme temperatures, can potentially influence the frequency and severity of traffic accidents. In this project my aim is to analyze how different weather conditions impact traffic accidents in NYC over the past decade (2012-2023).

## Data Sources
In this project I will utilize publicly available datasets:
- **NYC Vehicle Crashes (2012-2023)**: A dataset containing records of vehicle crashes in NYC, sourced from Kaggle.
- **NYC Weather Data**: Historical weather data for NYC, sourced from Kaggle. The current dataset available includes only 2019, so a more extensive dataset covering 2012-2023 will be identified and used.

## Data Collection & Enrichment Plan
Since the weather dataset currently covers only 2019, additional weather data will be collected to cover the full timeframe (2012-2023). Possible sources include:
- **NYC Open Data**
- **Additional publicly open datasets**

Once both datasets are available, they will be merged based on date and location to analyze correlations between weather events and accident occurrences.

## Tools and Technologies
I will utilize the following technologies during this project.
- **Python:** for working on data
- **Pandas:** for manipulating the data
- **Matplotlib:** for visualization of data

## Expected Analysis Steps
1. **Data Cleaning & Preprocessing**
   - I will handle missing values and inconsistencies on the data.
   - I will standardize date formats to merge datasets.
2. **Exploratory Data Analysis (EDA)**
   - It will be identified trends in accident frequency over time.
   - It will be analyized weather conditions on high-accident days.
3. **Statistical & Hypothesis Testing**
   - I will check if certain weather conditions significantly impact accident rates.
4. **Machine Learning Application**
   - In this project I will use predictive modeling to estimate accident likelihood based on weather conditions.
5. **Visualization & Insights**
   - Lastly, I will do visualizations to highlight patterns and correlations.

## Timeline
- **March 14**: Submitting project proposal (this document)
- **April 18**: Collect data and conduct exploratory data analysis
- **May 23**: Apply machine learning models
- **May 30**: Final submission and presentation

## Expected Outcome
In this project I will focus on to providing insights into how different weather conditions impact road safety in NYC. The findings could contribute to better urban planning, traffic regulations, and driver awareness during adverse weather conditions.

## Dataset Description
In order to have a deeper understanding of the topic, I decided to work on the data between 2019-2021 as a three year period.

I use three datasets:
- **NYC Vehicle Crashes (2012–2023)** – Contains timestamped crash records
- **NYC Temperature Data (2019)** – Daily data with temperature and precipitation values
- **NYC Hourly Weather Data (2020–2021)** – Hourly values aggregated to daily metrics

  Key features in the final dataset:
  - Date of the crash
  - Number of crashes on that date
  - Daily average temperature (°C)
  - Total daily precipitation (mm)
  - bad_weather
  - Categorical grouping of temperatures (Very Cold, Cold, Mild, Warm)
  - Flag indicating if the crash occurred on a weekend or not

## Tools and Technologies
- **Python**: Main programming environment
- **Pandas:** Data preprocessing, merging, and transformation
- **Matplotlib & Seaborn:** Data visualization
- **SciPy:** Statistical testing (Pearson correlation)

## Visualization
- **Scatter Plot:** Precipitation vs. Number of Crashes
- **Line Plot:** Monthly Average Crash Count
- **Heatmap:** Average Daily Crashes by Weekday and Month
- **Boxplot:** Crash Distribution by Temperature Category

## Hypothesis Testing
- **H0:** There is no correlation between precipitation and the number of daily crashes.
- **HA:** There is a correlation between precipitation and the number of daily crashes.

I used Pearson Correlation  and p = 0.05

I have calculated p = 0.5050049984197857 > 0.05, therefore we have failed to reject Null Hypothesis.

## Machine Learning Phase
In this phase I prepared a final dataset from using my previous data sets to adopt ML methods easyly. 
My aim is to measure the performances of the several methods and detect the most convenient method to choose. 

## Taken Steps:
1. **Data Preparation**
Created the final dataset **final_df_minimized.csv** with the following features:
- **precipitation**: total daily rainfall (mm)
- **tavg**: average daily temperature (°C)
- **is_weekend**: whether the day is a weekend
- **bad_weather**: whether the day had extreme weather (precipitation > 3mm or tavg < 0°C)
- **temp_category**: temperature category (Very Cold, Cold, Mild, Warm)
- **num_crashes**: number of vehicle crashes (target variable)

2. **Modeling**
- **Linear Regression**
- **Ridge Regression**
- **Decision Tree Regressor**
- **Random Forest Regressor**

3. **Evaluation Metrics**
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R² Score** (Explained Variance)

4. **Visualiziton**
- **Scatter plots** comparing predicted vs actual crash counts for each model
- **Feature importance barplot** for Random Forest
- **Decision tree structure plot**

## Conclusion:
**Decision Tree Regressor** achieved the best performance with the lowest RMSE (85.40) and highest R² score (0.70).
Linear models are underperformed very probably due to the non-linear nature of the problem.
**Precipitation** and **temperature** are observed the most influential features in crash prediction.

It is observed that there is an important relationship between weather conditions and traffic accidents in New York City which can be understood by Machine Learning methods (especially Tree Based Regressors). These findings can be important for urban planning and reducing the traffic accidents by governmantal instruments.
