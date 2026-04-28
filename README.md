🍷 Wine Quality Classification — From Linear Models to Feature-Engineered KNN
📌 Project Overview
This project explores the problem of wine quality classification (Low, Medium, High) using a structured machine learning pipeline. The goal was not just to build a high-performing model, but to deeply understand:


How different models behave on the same dataset


Whether performance is limited by model choice or data structure


How feature engineering impacts separability


The project follows a progressive modeling approach, starting from simple linear models and evolving toward more flexible algorithms with engineered features.

🧠 Problem Statement
Wine quality is inherently subjective and continuous in nature, yet it is framed here as a multi-class classification problem.

The key challenge:
Significant overlap between quality classes, especially the medium category.


🔍 Workflow & Methodology
🔹 1. Exploratory Data Analysis (EDA)


Univariate analysis:


Identified skewness, outliers, and feature distributions




Bivariate analysis:


Key relationships discovered:


Alcohol, sulphates → positive correlation with quality


Volatile acidity → negative correlation




Observed non-linear and threshold effects




👉 Early insight:

Wine quality behaves like a gradient, not distinct clusters


🔹 2. Data Preprocessing


Handling missing/invalid values


Feature scaling using StandardScaler


Train-test split with stratification (to preserve class distribution)


Encoding target into:


low, medium, high





🔹 3. Baseline Models
✅ Linear Discriminant Analysis (LDA)


Established linear separability baseline


Showed:


Strong clustering for low-quality wines


Heavy overlap between medium and high




⚠️ Quadratic Discriminant Analysis (QDA)


Introduced non-linear boundaries


No improvement → slight overfitting


👉 Key takeaway:

Increasing model complexity alone does not solve class overlap


🔹 4. Logistic Regression (Raw Features)


Multinomial Logistic Regression with scaling


Achieved 64% accuracy (best linear model)


Insights:


Low-quality wines → clearly separable


Medium class → transition zone


High class → frequently confused with medium



🔹 5. K-Nearest Neighbors (Raw Features)


Tuned using GridSearchCV


Accuracy: 63%


Behavior:


Improved detection of high-quality wines


Reduced performance on low-quality class


👉 Insight:

Local patterns exist, but are not strong enough in raw feature space


🔹 6. Feature Engineering
Created domain-driven features to capture interactions:


Ratios (e.g., alcohol/density)


Balance features (e.g., sulphates vs acidity)


Non-linear transformations


Goal:

Improve feature space geometry and class separability


🔹 7. Logistic Regression (Engineered Features)


No performance improvement (~64%)


👉 Insight:

Engineered features introduced non-linear relationships, not usable by linear models


🔹 8. KNN (Engineered Features) ✅ Final Model


Accuracy: 68% (Best Performance)


Improved across all classes:


High-quality detection ↑


Medium class stability ↑


Low class remains strong




👉 Key breakthrough:

Feature engineering + local learning significantly improves performance


📊 Model Comparison Summary
ModelAccuracyKey InsightLDA~61%Linear baselineQDA~61%No gain, overfittingLogistic (Raw)64%Best linear modelKNN (Raw)63%Captures local structureLogistic (Engineered)64%No improvementKNN (Engineered)68%✅ Best model

🧠 Key Learnings
1. Class Overlap is the Core Challenge


Medium class behaves as a transition zone


High vs Medium separation remains difficult



2. Model Complexity ≠ Better Performance


QDA did not outperform LDA


Non-linearity alone is not enough



3. Feature Engineering is Critical


Raw features limit performance


Engineered features improve representation



4. Model-Feature Alignment Matters


Logistic Regression → prefers linear relationships


KNN → benefits from local, non-linear structures



Best results come from aligning feature design with model capability


🚀 Final Conclusion

The best performance (68% accuracy) was achieved using KNN with engineered features, demonstrating that:



Wine quality classification is a fuzzy boundary problem


Feature engineering can reshape the problem space


Local learning methods can better exploit complex feature interactions



📈 Future Improvements


Try Random Forest / Gradient Boosting (XGBoost, LightGBM)


Perform advanced feature selection


Explore dimensionality reduction (PCA)


Reframe problem as:


Regression OR


Binary classification (high vs rest)





💡 Takeaway
This project is not just about building models—it's about understanding:

Why models succeed or fail, and how data representation shapes outcomes.


https://www.linkedin.com/in/shorya-bisht-a20144349/

