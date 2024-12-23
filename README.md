# Customer Satisfaction Survey Analysis and Prediction

## Overview
This project analyzes customer satisfaction survey results for a fast-growing logistics and delivery startup. The analysis identifies key areas of customer dissatisfaction, extracts actionable insights, and develops machine learning models to predict customer satisfaction with high accuracy.

---

## Contents
1. [Introduction](#introduction)
2. [Objectives](#objectives)
3. [Data Analysis](#data-analysis)
4. [Model Development](#model-development)
5. [Key Insights](#key-insights)
6. [Results](#results)
7. [Conclusion](#conclusion)
8. [Future Work](#future-work)
9. [Authors](#authors)

---

## Introduction
Customer satisfaction is critical for success in the logistics and delivery domain. This project:
- Analyzes survey data from **126 customers**.
- Identifies key features influencing satisfaction.
- Builds predictive models to forecast customer satisfaction.

The survey includes six questions:

1. **X1:** My order was delivered on time  
2. **X2:** The contents of my order were as I expected  
3. **X3:** I ordered everything I wanted to order  
4. **X4:** I paid a good price for my order  
5. **X5:** I am satisfied with my courier  
6. **X6:** The app makes ordering easy for me  

The target variable **Y** indicates whether a customer is satisfied (1 = Yes, 0 = No).

---

## Objectives
1. **Objective 1**: Analyze survey data and extract insights:
   - What are the patterns in the survey responses?
   - Which questions influence dissatisfaction the most?
   - How can mutual information rank the importance of questions?

2. **Objective 2**: Build and evaluate machine learning models to predict customer satisfaction.

---

## Data Analysis

### 1. Dataset Description
- **126 responses** with no missing values.
- Features are rated on a scale of 1 to 5.
- Target variable (Y) is binary: satisfied or unsatisfied.

### 2. Key Observations:
- **45.3\%** of customers are not satisfied.
- **X1**, **X3**, and **X5** are the most important questions based on mutual information.
- **X2** has **zero mutual information** with the satisfaction outcome and can be removed from further analysis.

### 3. Correlation Analysis
Feature-to-feature correlations are low (max correlation: **0.43** between X1 and X5). Therefore, no redundancy exists.

### 4. Data Distribution
Boxplots and statistical descriptions highlight:
- **X1** and **X6** have narrow distributions (low variability).
- Outliers are observed in features like **X2**, requiring further investigation.

---

## Model Development

We tested multiple machine learning models and optimized them for accuracy:

1. **Bernoulli Naive Bayes (BernoulliNB)**
   - Recursive Feature Elimination (RFE) identified **X1**, **X3**, and **X5** as key features.
   - Accuracy: **72.7\%**

2. **LightGBM Classifier (LGBM)**
   - Best accuracy: **76.5\%**
   - Robust performance across all features.

3. **Support Vector Machine (SVC)**
   - RFE improved accuracy with features **X1**, **X3**, and **X5**.
   - Accuracy: **72.7\%**

---

## Key Insights

1. **45.3\% of customers** are dissatisfied.  
2. **X1** (on-time delivery), **X3** (correct order), and **X5** (courier satisfaction) are the most critical questions.  
3. **X2** (order contents) has **zero impact** on satisfaction and can be removed from future surveys.  
4. **LGBM Classifier** is the best-performing model, achieving **76.5\% accuracy**.  

---

## Results

### Model Comparison
| Model                 | Accuracy (%) | F1 Score (%) |
|-----------------------|--------------|--------------|
| **LGBM Classifier**   | 76.5         | 89.0         |
| BernoulliNB           | 72.7         | 78.4         |
| Support Vector Machine (SVC) | 72.7         | 77.77        |

### Improvement
- Predictions by LGBM outperform random guessing by **40\%** or **1.4× better** accuracy.



---

## Conclusion

1. **Key Insights**:
   - **45.3% of customers** expressed dissatisfaction with our services.
   - The most influential factors for predicting customer satisfaction are:
     - **X1**: On-time delivery.
     - **X3**: Customers being able to order everything they wanted.
     - **X5**: Satisfaction with the courier service.
   - **X2** ("Contents of my order were as I expected") showed no correlation with satisfaction and was identified as unnecessary for predictive modeling.

2. **Model Performance**:
   - Among the machine learning models tested, the **LightGBM Classifier (LGBM)** demonstrated the best predictive accuracy at **76.5%** and an **F1 score of 89.0%**.
   - The **Bernoulli Naive Bayes (BernoulliNB)** and **Support Vector Machine (SVC)** also performed well, achieving accuracies of **72.7%**, but they were slightly less effective compared to LGBM.

3. **Practical Recommendations**:
   - To improve customer satisfaction, focus on:
     - Ensuring timely delivery (**X1**).
     - Simplifying the ordering process (**X3**).
     - Enhancing the performance and professionalism of couriers (**X5**).
   - Remove **X2** from future surveys to streamline data collection without sacrificing predictive accuracy.

4. **Impact of Analysis**:
   - The analysis highlights the importance of combining customer feedback with advanced data-driven methods.
   - By implementing the insights and leveraging predictive modeling, the company can prioritize customer satisfaction and improve service delivery systematically.

5. **Future Prospects**:
   - Scaling this model with additional data and features (e.g., delivery location and time) can further enhance accuracy and generalizability.
   - The methodology used can be extended to other aspects of the business, such as inventory management and operational logistics.

By addressing these key insights and applying the proposed recommendations, the company can significantly enhance its service quality and foster long-term customer loyalty.

## Authors
- **Data Analyst**: Ali Zoljodi  
- **Mentor**: Semih Yagcioglu  

---

## Acknowledgment
This work highlights the importance of customer feedback analysis for improving logistics services and predicting satisfaction effectively.
