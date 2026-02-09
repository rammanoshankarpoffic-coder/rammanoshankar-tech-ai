# Smart Restaurant Recommendation and Crowd Prediction System using Machine Learning

**Author:** Rammanoshankar P
**Date:** February 2026

---

## Abstract

This project presents a Smart Restaurant Recommendation and Crowd Prediction System using Machine Learning techniques. The system recommends suitable restaurants based on user location, food preference, and rating, while simultaneously predicting expected crowd level using historical patterns. A Logistic Regression classification model is trained on a synthetic dataset containing day, time, and holiday attributes. The system is deployed as a Flask web application that provides users with data‑driven dining decisions. The project demonstrates the practical application of supervised learning in real‑world decision support systems.

---

## Introduction

With the rapid growth of restaurants and food outlets in urban cities, customers often struggle to choose the right place to eat. Many factors influence this decision — location, food preference, service quality, ratings, and most importantly crowd levels. Visiting an overcrowded restaurant results in long waiting time and poor dining experience.

This project introduces a machine learning‑based system that not only recommends restaurants but also predicts the expected crowd level. This helps users choose a better restaurant at the right time. The motivation for this project came from real‑life difficulty in selecting restaurants during weekends in Coimbatore city.

---

## Problem Statement

To design and implement a machine learning‑based system that recommends nearby restaurants based on user location and food preference (Veg/Non‑Veg) and predicts expected crowd level (Low/Medium/High) using historical data patterns.

---

## Objectives

* Develop a restaurant recommendation system based on location and food type
* Predict restaurant crowd level using machine learning
* Reduce waiting time for customers
* Demonstrate real‑world usage of classification algorithms
* Build an end‑to‑end ML web application using Flask

---

## Project Overview

The system performs two major functions:

### 1. Restaurant Recommendation

Restaurants are filtered based on:

* Selected area
* Food type preference
* Google ratings

The results are sorted from highest to lowest rating.

### 2. Crowd Prediction

For each recommended restaurant, the system predicts crowd level using:

* Day (Weekday / Weekend)
* Time (Morning / Afternoon / Evening / Night)
* Holiday (Yes / No)

---

## Dataset Used

Since a ready‑made dataset matching requirements was unavailable, a synthetic dataset was generated for experimental evaluation.

### Restaurant Dataset (restaurants.csv)

Contains:

* Restaurant Name
* Area
* Type (Veg / Non‑Veg)
* Google Rating
* Price Range

### Crowd Dataset (crowd_data.csv)

Contains:

* Restaurant Name
* Day
* Time
* Holiday
* Crowd Level (Low/Medium/High)

Each dataset consists of 500 records used for training and testing.

---

## Machine Learning Methodology

### Data Preprocessing

Categorical values were converted into numerical values using Label Encoding:

* Day
* Time
* Holiday
* Crowd Level

### Model Training

**Algorithm Used:** Logistic Regression

**Input Features:** Day, Time, Holiday
**Output:** Crowd Level

### Why Logistic Regression?

Logistic Regression is used because the output variable is categorical. The algorithm estimates probabilities using a sigmoid function and assigns the class with highest probability.

### Model Saving

The trained model and encoders were saved using Joblib for reuse in the web application.

---

## System Workflow

1. User enters location and food preference
2. System filters restaurants from dataset
3. Restaurants sorted by rating
4. User selects day, time and holiday
5. Encoded values sent to ML model
6. Model predicts crowd level
7. Results displayed in web interface

---

## Web Application

A Flask‑based web application was developed.

### User Inputs

* Area
* Veg / Non‑Veg
* Day
* Time
* Holiday

### System Output

A table displaying recommended restaurants and predicted crowd level.

---

## Technologies Used

* Programming Language: Python
* Machine Learning Library: Scikit‑learn
* Web Framework: Flask
* Data Handling: Pandas
* Model Storage: Joblib
* IDE: VS Code

---

## Result Analysis

The model produced consistent predictions for weekday and weekend patterns. Weekend evenings showed higher crowd probability compared to weekday mornings. The recommendation system successfully prioritized highly rated restaurants with lower predicted crowd levels, improving decision making.

---

## Advantages

* Saves time for users
* Reduces waiting in crowded restaurants
* Provides data‑driven recommendations
* Real‑world applicable project
* Beginner‑friendly ML implementation

---

## Limitations

* Predictions depend on historical data
* No real‑time crowd monitoring
* Limited dataset size affects accuracy

---

## Future Enhancements

* Integrate Google Maps API for live data
* Distance‑based ranking
* Sentiment analysis using reviews
* Cloud deployment (AWS/Heroku)
* Mobile application version

---

## Real World Applications

* Food delivery platforms
* Smart city planning
* Tourism recommendation systems
* Mall and theatre crowd prediction
* Event management systems

---

## Conclusion

This project demonstrates how machine learning can be applied to solve real‑world decision problems. By combining restaurant recommendation with crowd prediction, users can make smarter dining choices, reduce waiting time and improve overall experience.

---

## Feature Engineering

To improve prediction quality, categorical attributes were transformed into structured numerical features. Time slots were grouped into four ranges (Morning, Afternoon, Evening, Night) to capture human dining behavior patterns. Weekend and holiday indicators were separated to distinguish leisure dining from regular workday dining. These engineered features help the model learn temporal crowd patterns effectively.

---

## Model Evaluation

After training, the model was evaluated using classification metrics:

* **Accuracy:** Overall correctness of predictions
* **Precision:** Correctness of predicted crowd levels
* **Recall:** Ability to detect actual crowded situations
* **F1‑Score:** Balance between precision and recall

The model showed better prediction performance during weekend evenings and holiday nights due to stronger pattern consistency in the dataset.

### Confusion Matrix Interpretation

The confusion matrix compares predicted vs actual crowd levels. Most misclassifications occurred between *Medium* and *High* crowd categories because of similar real‑world patterns during peak dining hours.

---

## Hyperparameters Used

* Solver: lbfgs
* Max Iterations: 1000
* Multi‑class Mode: auto

Increasing iteration count ensured convergence of the model during training.

---

## Deployment Process

The trained model was integrated into a Flask web application.

### Steps Performed

1. Load trained model using Joblib
2. Accept user input from HTML form
3. Encode input values using saved encoders
4. Predict crowd level using trained model
5. Display results dynamically in table format

---

## How to Run the Project Locally

1. Install dependencies

   ```
   pip install flask pandas scikit-learn joblib
   ```
2. Run the application

   ```
   python app.py
   ```
3. Open browser

   ```
   http://127.0.0.1:5000
   ```

---

## Repository Structure

```
project/
│-- app.py
│-- model.pkl
│-- encoders.pkl
│-- restaurants.csv
│-- crowd_data.csv
│-- templates/
│     └── index.html
│-- static/
      └── style.css
```

---

## Practical Learning Outcomes

Through this project, the following concepts were understood:

* Supervised learning workflow
* Data preprocessing and encoding
* Model persistence using Joblib
* Web integration of ML models
* Real‑world decision support system design

---

## References

1. Scikit‑learn Documentation – Logistic Regression
2. Flask Official Documentation
3. Machine Learning for Beginners – Microsoft Learn
4. Python Pandas User Guide
