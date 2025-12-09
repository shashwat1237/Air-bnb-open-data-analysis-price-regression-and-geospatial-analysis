Kaggle dataset link- https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data

NYC Airbnb Data Analysis & Price Modeling

This project performs a complete exploratory, statistical, and machine-learning–driven analysis of the AB_NYC_2019 Airbnb dataset.
It explores pricing patterns across New York City, cleans and transforms the data, builds predictive models, and uses SHAP explainability to interpret key factors influencing Airbnb prices.

🔍 Project Objectives

Understand geographic distribution of Airbnb listings

Explore price trends, density patterns, and outliers

Study relationships between major numerical features

Engineer meaningful features (e.g., min_price_pay)

Clean dataset by handling missing values and removing outliers

Build a price prediction model using XGBoost

Explain model predictions using SHAP values

📂 Dataset

File: AB_NYC_2019.csv
Contains NYC Airbnb listings with attributes like price, location, room type, number of reviews, and availability.

🧹 Data Cleaning & Preprocessing
✔ Missing Values

Numerical columns → filled with column mean

Categorical columns → filled with column mode

✔ Outlier Removal

Outliers removed from:

price

minimum_nights

reviews_per_month

This makes visualizations stable and model training more reliable.

✔ Feature Engineering

Added: min_price_pay = price × minimum_nights

Log transformation applied to price: price_log

📊 Exploratory Data Analysis
1. Geographic Patterns

Hexbin plots reveal hotspots in Manhattan and Brooklyn.

Higher-priced listings cluster in central Manhattan.

2. Price Distribution

Highly right-skewed (many cheap listings, few extremely expensive).

Outlier removal significantly improves clarity.

3. Relationship Visualization

Visualized relationships using histograms, boxplots, jointplots, and correlation matrices.

🤖 Modeling Approach
Feature Groups

Categorical: room_type, neighbourhood_group

Numerical: latitude, longitude, minimum_nights, number_of_reviews, availability_365, min_price_pay

Column Transformer

One-hot encoding for categorical features

StandardScaler for numerical features

Model Used: XGBoost Regressor

Captures nonlinear relationships

Trained on transformed feature set

Produces strong performance and interpretable outputs

🧠 Model Explainability (SHAP)

The project uses SHAP to interpret feature effects on prices:

Top Influential Features

Room type

Neighbourhood group

Latitude & longitude

Minimum nights

Minimum total payable price (min_price_pay)

Beeswarm plots and feature importance charts reveal how each feature pushes predictions higher or lower.

📈 Key Findings

Location is the strongest determinant of price.

Room types significantly shift price distributions (Entire home/apartment > private room > shared room).

Minimum stay requirements influence final payable amount more than initial price alone.

Reviews per month do not show strong linear correlation with price.

XGBoost effectively models these nonlinear relationships, confirmed through SHAP.

🛠️ Technologies Used

Python

Pandas, NumPy

Seaborn, Matplotlib

Scikit-Learn

XGBoost

SHAP

Jupyter Notebook

📄 Notebook Features

Data loading

Cleaning & transformation

Exploratory plots

Outlier analysis

Model training & evaluation

SHAP-based interpretability

Summary insights

📜 Summary

This notebook provides a complete research pipeline for understanding and modeling Airbnb prices in NYC. It combines statistical exploration, feature engineering, machine learning, and explainability to deliver both predictive accuracy and transparent insights.
