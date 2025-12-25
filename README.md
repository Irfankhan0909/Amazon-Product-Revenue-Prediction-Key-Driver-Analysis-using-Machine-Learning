📦 Amazon Product Revenue Prediction & Key Driver Analysis
📌 Project Overview

This project focuses on building an end-to-end data science pipeline to predict product-level revenue on Amazon and identify the key factors driving sales performance. Using real-world Amazon product data, the project combines data cleaning, exploratory data analysis (EDA), feature engineering, machine learning modeling, and business interpretation to deliver actionable insights.

The goal is not only to build an accurate predictive model but also to translate model outputs into meaningful business decisions related to pricing, customer trust, and category strategy.

🎯 Problem Statement

Amazon hosts millions of products across diverse categories, where revenue performance varies significantly due to pricing, demand, customer ratings, reviews, and product positioning. However, it is not always clear which factors most strongly influence revenue or how accurately revenue can be predicted for individual products.

Objective:

Predict product-level revenue using machine learning regression techniques

Identify and quantify the most influential drivers of revenue

Provide data-driven insights to support pricing and product strategy decisions

📂 Dataset Description

The dataset contains Amazon product-level data with information related to pricing, demand, customer feedback, and product categories.

Key Columns Used

product_rating

total_reviews

purchased_last_month

discounted_price

original_price

discount_percentage

product_category

Target Variable

revenue = discounted_price × purchased_last_month

🧹 Data Cleaning & Preparation

Real-world data required careful preprocessing to ensure reliability.

Steps Performed

Removed non-predictive columns (URLs, images, metadata)

Handled missing values:

Ratings & reviews → filled with 0 (indicating no customer engagement)

Purchase counts → filled with 0 (indicating no sales)

Pricing-related missing values → dropped to avoid artificial revenue

Removed columns with 100% missing or no signal

Ensured all modeling features contained zero missing values

🧠 Feature Engineering

To improve predictive power, several high-signal features were engineered:

Revenue: Final target variable

Price Difference: original_price − discounted_price

Rating Strength: product_rating × total_reviews (captures customer trust)

Encoded categorical variables using One-Hot Encoding

📊 Exploratory Data Analysis (EDA)

EDA was conducted to understand data behavior and guide modeling decisions.

Key Observations

Revenue distribution is highly right-skewed

Presence of high-value outliers (common in e-commerce)

Weak linear relationship between discounts and revenue

Strong non-linear patterns between customer trust metrics and revenue

Significant variation in revenue across product categories

These findings justified the use of tree-based models over linear models.

🤖 Modeling Approach
Baseline Model

Linear Regression

Used as a sanity check and interpretability baseline

Performance was limited due to non-linear data patterns

Advanced Model

Random Forest Regressor

Captured non-linear relationships and feature interactions

Significantly improved predictive performance

📈 Model Evaluation
Metrics Used

MAE (Mean Absolute Error) – average prediction error

RMSE (Root Mean Squared Error) – penalizes large errors

R² Score – proportion of variance explained

Results
Model	MAE	RMSE	R²
Linear Regression	~46,250	~119,227	0.15
Random Forest	~14,538	~75,336	0.66

📌 Outcome:
Random Forest reduced MAE by nearly 70% and explained 66% of revenue variance, demonstrating strong generalization on unseen data.

🔍 Feature Importance Analysis

Random Forest feature importance revealed the most influential revenue drivers:

Rating Strength

Total Reviews

Discounted Price

Original Price

Product Rating

Product Category

Key Insight

Customer trust signals (ratings × reviews) were more influential than discounts, indicating that long-term trust outweighs short-term price reductions.

💼 Business Impact

Demonstrated that customer trust metrics drive revenue more than discounting

Showed that final selling price matters more than discount percentage

Highlighted category-specific revenue behavior, enabling differentiated strategies

Provided actionable insights for:

Pricing optimization

Promotion strategy

Product prioritization

🔧 Technical Impact

Built a complete end-to-end ML pipeline

Improved model performance from R² = 0.15 to 0.66

Applied feature engineering and non-linear modeling

Interpreted model behavior using feature importance

Validated results using both metrics and visual diagnostics

🛠️ Tech Stack
Programming & Libraries

Python

Pandas

NumPy

Data Visualization

Matplotlib

Seaborn

Machine Learning

Scikit-learn

Linear Regression

Random Forest Regressor

Pipelines

ColumnTransformer

Evaluation

MAE

RMSE

R² Score

🚀 Future Improvements

Apply log transformation to revenue to reduce skewness

Hyperparameter tuning for Random Forest

SHAP values for deeper explainability

Time-based forecasting using historical trends

Deployment as a prediction API or dashboard

📌 Conclusion

This project demonstrates how data science can move beyond prediction to decision-making. By combining robust modeling with business interpretation, the analysis shows that trust, demand, and pricing structure are the primary drivers of Amazon product revenue — not discounts alone.

📬 Contact

If you’d like to discuss this project or collaborate:

Mohd Irfan
📧 Email: irfan890908@gmail.com

🔗 LinkedIn: www.linkedin.com/in/mohammed-irfan-0160a2267
