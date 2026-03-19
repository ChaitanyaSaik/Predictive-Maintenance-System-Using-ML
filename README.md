
# Predictive Maintenance System using ML

## Overview
Predictive maintenance uses machine learning to anticipate equipment failures before they occur. 
Instead of performing maintenance only after a breakdown or at fixed intervals, predictive models 
analyze sensor data from machines and detect patterns that indicate an upcoming failure.

This project builds a **machine learning system that predicts industrial machine failures using sensor data**. 
By identifying failure patterns early, the system can help industries reduce downtime, optimize maintenance schedules, 
and lower operational costs.

---

# Problem Statement

In industrial environments, unexpected machine failures can lead to:

- Production downtime
- Expensive repairs
- Safety risks
- Reduced operational efficiency

Traditional maintenance strategies include:

**Reactive Maintenance**
Maintenance happens after equipment fails.

**Preventive Maintenance**
Maintenance happens at fixed intervals, even if the machine is healthy.

Both approaches are inefficient.

**Predictive Maintenance** uses machine learning to analyze machine sensor data and predict failures before they occur.

---

# Project Objectives

The primary goals of this project are:

- Predict machine failures using historical sensor data
- Identify key operational features that indicate potential failures
- Build a machine learning pipeline for failure prediction
- Evaluate multiple ML models and select the best performing one
- Deploy the trained model using a Streamlit application

---

# Dataset Description

The dataset contains machine operational data collected from industrial equipment sensors.

### Features

- Air Temperature (K)
- Process Temperature (K)
- Rotational Speed (RPM)
- Torque (Nm)
- Tool Wear (minutes)
- Machine Type

### Target Variable

Failure

0 → Normal machine operation  
1 → Machine failure

The dataset allows the model to learn patterns that differentiate normal operation from failure conditions.

---

# Machine Learning Pipeline

The project follows a standard machine learning workflow.

1. Data preprocessing
2. Feature engineering
3. Model training
4. Hyperparameter tuning
5. Model evaluation
6. Model deployment

---

# System Architecture

The predictive maintenance system follows a modular architecture.

Raw Sensor Data → Data Preprocessing → Feature Engineering → Machine Learning Model → Failure Prediction → Visualization Dashboard

### Architecture Explanation

**Raw Sensor Data**
Machine sensors continuously generate operational data.

**Data Preprocessing**
The dataset is cleaned by handling missing values, removing duplicates, and scaling features.

**Feature Engineering**
Important variables are selected and transformed to improve model performance.

**Model Training**
Multiple machine learning models are trained on the dataset.

**Prediction**
The trained model predicts whether the machine will fail.

**Visualization**
Results are displayed using an interactive dashboard.

---

# Machine Learning Models

Two machine learning algorithms were evaluated.

## Random Forest

Random Forest is an ensemble learning method that builds multiple decision trees and combines their predictions.

The final prediction is determined using majority voting.

Random Forest prediction function:

f(x) = (1/N) * Σ T_i(x)

Where:

- N = number of trees
- T_i(x) = prediction from the i-th decision tree

Advantages:

- Handles high dimensional data
- Reduces overfitting
- High accuracy in classification tasks

---

## Support Vector Machine (SVM)

Support Vector Machine is a supervised learning algorithm used for classification.

It works by finding the optimal hyperplane that separates different classes.

SVM decision function:

f(x) = w · x + b

Where:

- w = weight vector
- x = input features
- b = bias

The goal is to maximize the margin between classes.

Advantages:

- Effective in high dimensional spaces
- Works well with smaller datasets
- Strong theoretical foundation

---

# Model Evaluation

The models were evaluated using classification metrics.

### Accuracy

Accuracy measures the proportion of correct predictions.

Accuracy = (TP + TN) / (TP + TN + FP + FN)

Where:

TP = True Positives  
TN = True Negatives  
FP = False Positives  
FN = False Negatives  

### ROC-AUC

ROC-AUC measures how well the model separates the two classes.

A value closer to **1** indicates better performance.

---

# Model Performance

| Model | Accuracy | ROC-AUC |
|------|------|------|
| Random Forest | 98% | 0.977 |
| Support Vector Machine | 98% | 0.963 |

Random Forest performed slightly better and was selected as the final model.

---

# Deployment

The trained machine learning model was saved using **joblib** and deployed using **Streamlit**.

The Streamlit web application allows users to:

- Input machine sensor values
- Run failure predictions
- Visualize prediction results

Run the application using:

streamlit run app.py

---

# Technology Stack

Programming Language

Python

Libraries

Pandas  
NumPy  
Scikit-learn  
Matplotlib  
Seaborn  

Deployment

Streamlit

Tools

Jupyter Notebook  
Git  
GitHub  

---

# Project Structure

Predictive_Maintenance_Project/

data/
Machine sensor dataset

notebooks/
Exploratory data analysis and model training

models/
Saved trained machine learning models

src/
Application source code

app.py
Streamlit web interface

README.md
Project documentation

requirements.txt
Project dependencies

---

# Applications

Predictive maintenance systems are widely used in:

Manufacturing Industry  
Automotive Industry  
Energy and Power Plants  
Aerospace Systems  
Industrial IoT Monitoring  

---

# Future Improvements

Real-time sensor data integration  
Deep learning models for predictive maintenance  
IoT device integration  
Cloud-based deployment  
Automated alert systems

---

# License

This project is released under the MIT License.
