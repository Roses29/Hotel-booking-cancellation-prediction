🌍 [Lire en Français](README_FR.md) | 📓 [See PDF](./CHT_Graded_Project_Learner_Notebook.ipynb)

# 🏨 Hotel Booking Cancellation Prediction

## Overview

This project, which was done as part of my MIT certification, addresses the challenge of hotel booking cancellations, which represent a significant source of revenue loss for hotels. Using a real-world dataset from **INN Hotels Group** (Portugal), the goal is to build machine learning models capable of predicting whether a booking will be cancelled, and to derive actionable business recommendations.

## Dataset

The dataset contains **36,275 bookings** with **19 features**, including:

- Guest details (number of adults, children, special requests)
- Booking details (lead time, market segment, room type, meal plan)
- Stay information (week nights, weekend nights, arrival date)
- Target variable: `booking_status` (Cancelled / Not Cancelled)

## Methodology

1. **Exploratory Data Analysis (EDA)**
   - Univariate and bivariate analysis
   - Handling outliers (avg price per room, number of children)
   - Key findings: 32.8% of bookings were cancelled; online bookings had the highest cancellation rate (~38%); repeated guests had a very low cancellation rate (~2-3%)

2. **Data Preparation**
   - One-hot encoding of categorical variables
   - 70/30 stratified train/test split

3. **Models Trained**
   | Model | F1-Score (Test) |
   |-------|----------------|
   | Logistic Regression | 0.79 |
   | SVM – Linear Kernel | 0.80 |
   | SVM – RBF Kernel | 0.81–0.82 |
   | Decision Tree (tuned) | 0.82 |
   | Random Forest | 0.90 |

4. **Evaluation Metric**: F1-Score (to balance precision and recall for both classes)

##  Key Findings

- **Lead time** is the most important feature: the longer the time between booking and arrival, the higher the cancellation risk.
- **Average room price** and **number of special requests** are also strong predictors.
- **Online bookings** have the highest cancellation rate; **complementary** and **corporate** segments are the most reliable.

## Business Recommendations

1. Apply stricter cancellation policies (lower refunds) for bookings with high lead times.
2. Offer dynamic pricing to attract bookings during low-occupancy periods.
3. Introduce non-refundable or low-refund policies for online bookings.
4. Enhance customer experience with additional services and perks to reduce churn.

## Tech Stack/ Skills

- **Python** – pandas, NumPy, Matplotlib, Seaborn
- **Scikit-learn** – Logistic Regression, SVM, Decision Tree, Random Forest, GridSearchCV

