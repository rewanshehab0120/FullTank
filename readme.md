<div align="center">

# ⛽ FullTank — Egyptian Fuel Price Prediction
### An End-to-End Machine Learning Project 🇪🇬

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-0.9087_R²-orange?style=for-the-badge&logo=xgboost&logoColor=white)](https://xgboost.readthedocs.io/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F1-yellow?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

</div>

---

## 📌 Project Overview

**FullTank** is a comprehensive Machine Learning project designed to predict fuel prices in Egypt using historical fuel-price data combined with key economic and market-related factors. 

The goal was never just to train a model and grab a high score; our vision was to build a complete **End-to-End Machine Learning Pipeline** bridging raw data collection all the way to a user-friendly graphical interface.

> **Project Flow:**  
> `Data` ➔ `Analysis` ➔ `Modeling` ➔ `Evaluation` ➔ `GUI` ➔ `End User`

---

## 🎯 Project Objectives

*   Analyze historical fuel price movements in Egypt.
*   Uncover hidden patterns and economic relationships within the data.
*   Clean, preprocess, and engineer robust features for machine learning.
*   Train, evaluate, and compare multiple machine learning algorithms.
*   Identify the top-performing model (**XGBoost** with $R^2 = 0.9087$).
*   Develop an interactive, clean **GUI** for seamless end-user interactions.

---

## 🗂️ Project Structure

```text
FullTank/
│
├── 📁 GetData/                  # Data collection & preparation files
├── 📄 final.ipynb               # Complete end-to-end ML workflow notebook
├── 📊 final_training_dataset.csv  # Final preprocessed dataset (CSV)
├── 📊 final_training_dataset.xlsx # Final preprocessed dataset (Excel)
└── 📄 README.md                 # Project documentation
## 🎯 Project Objectives

The project aims to:

- Analyze historical fuel prices in Egypt.
- Understand patterns and relationships within the data.
- Prepare and clean the dataset for Machine Learning.
- Perform Feature Engineering.
- Experiment with multiple Machine Learning models.
- Compare model performance.
- Select the best-performing model among the tested approaches.
- Build a simple GUI for interacting with the prediction system.
- Make the final solution easy to use for non-technical users.

---

# 🗂️ Project Structure

```text
FullTank/
│
├── GetData/
│   └── Data collection and preparation files
│
├── final.ipynb
│   └── Complete Machine Learning workflow
│
├── final_training_dataset.csv
│   └── Final training dataset in CSV format
│
├── final_training_dataset.xlsx
│   └── Final training dataset in Excel format
│
└── README.md
    └── Project documentation
````

---

# 📁 Files Description

## 1. `GetData/`

This folder contains the files related to the **data collection and preparation stage**.

The purpose of this stage is to gather the required data and prepare the different sources before using them in the Machine Learning pipeline.

The collected information was used to create the final dataset required for modeling.

---

## 2. `final.ipynb`

This is the main Jupyter Notebook of the project.

It contains the complete workflow, including:

* Data loading
* Data preparation
* Data exploration
* Feature Engineering
* Model Training
* Model Evaluation
* Model Comparison
* Final prediction workflow

The notebook represents the main technical implementation of the project.

---

## 3. `final_training_dataset.csv`

This is the final prepared dataset used for Machine Learning.

The CSV format makes the dataset easy to:

* Load using Python
* Process using Pandas
* Reuse in other Machine Learning workflows

---

## 4. `final_training_dataset.xlsx`

This is the final training dataset provided in Excel format.

The Excel version makes the data easier to inspect manually and useful for users who prefer working with spreadsheets.

---

# 🔍 Data Analysis

Before training the models, we focused on understanding the dataset.

The analysis helped us understand:

* Data distributions
* Relationships between variables
* Economic and market-related factors
* Patterns over time
* Relationships between input features and fuel prices

Exploratory Data Analysis was an important step before moving to Machine Learning.

---

# 🧠 Feature Engineering

One of the most important lessons from this project was that Machine Learning performance does not depend only on choosing a powerful model.

It also depends heavily on how well the available data represents the problem.

We therefore focused on preparing and creating meaningful features that could help the models understand the factors affecting fuel prices.

### Key Idea

> If you don't understand your data, you can't build effective features.

Good Feature Engineering can sometimes make a bigger difference than simply switching to a more complex model.

---

# 🤖 Machine Learning Models

Instead of relying on a single model, we experimented with several Machine Learning approaches and compared their performance.

---

## 1. Linear Regression

We started with Linear Regression as a baseline model.

**R² Score: ~0.67**

The result was reasonable as a starting point and helped us understand the basic relationships within the data.

However, it also showed that the problem was not simply based on linear relationships.

---

## 2. K-Nearest Neighbors (KNN)

We then experimented with KNN.

**R² Score: ~0.56**

The performance was lower than Linear Regression.

This helped us understand that the problem was not simply about finding data points that were similar to each other.

The dataset contains economic and time-related behavior that KNN did not capture as effectively.

---

## 3. Random Forest

Next, we tried Random Forest.

**R² Score: ~0.72**

The performance improved significantly compared with the previous models.

This suggested that the relationships between the features and fuel prices were more complex than a simple linear relationship.

However, we still wanted to investigate whether we could improve the prediction further.

---

## 4. Prophet

We also experimented with Prophet because the dataset contains time-related information.

The idea was logical because fuel prices change over time.

However, we found that the problem is broader than a pure Time Series forecasting problem.

Fuel prices are affected by several economic and market factors, not simply by the passage of time.

Therefore, Prophet alone was not sufficient for the complete problem.

---

## 5. Ensemble Model

We experimented with an Ensemble combining:

* Random Forest
* Linear Regression

**R² Score: ~0.78**

The Ensemble improved the performance compared with the individual models.

However, we still believed that there was room for improvement.

---

## 6. XGBoost 🚀

Finally, we tested XGBoost.

**R² Score: 0.9087**

This was the **highest R² score among the models we tested**.

XGBoost was able to capture the complex relationships between the different features more effectively than the other tested approaches.

---

# 📊 Model Comparison

| Model                             |                              R² Score |
| --------------------------------- | ------------------------------------: |
| Linear Regression                 |                                 ~0.67 |
| KNN                               |                                 ~0.56 |
| Random Forest                     |                                 ~0.72 |
| Prophet                           | Not suitable as a standalone solution |
| Random Forest + Linear Regression |                                 ~0.78 |
| **XGBoost**                       |                            **0.9087** |

> **Note:** The scores represent the results obtained during our project experiments and should not be interpreted as universal performance guarantees.

---

# 💡 What We Learned from Modeling

The biggest lesson was that there is no universally "best" Machine Learning model.

A model can perform differently depending on:

* The dataset
* Feature Engineering
* Data quality
* Problem structure
* Relationships between variables
* Evaluation strategy

Instead of asking:

> **"What is the best model?"**

A better question is:

> **"Which model understands this data and problem best?"**

---

# 🖥️ GUI — From Model to End User

We did not want the project to end with a Jupyter Notebook and a prediction score.

Our goal was to turn the Machine Learning workflow into something that an end user could interact with easily.

Therefore, we developed a simple and comfortable GUI.

## GUI Features

### 🌙 Dark Mode & Light Mode

Users can switch between dark and light themes depending on their preference.

### 🧪 Default Data

The interface provides default data so users can test the system without having to start from scratch.

### 📊 Model Comparison

The GUI displays the results of the tested models, allowing users to compare their performance.

### ⛽ Fuel Type Dropdown

Users can select the fuel type from a dropdown menu instead of typing it manually.

This helps reduce input mistakes and makes the interface easier to use.

### 🎯 Simple User Experience

The interface was designed to be:

* Simple
* Comfortable
* Easy to understand
* Suitable for non-technical users

---

# 🔄 End-to-End Architecture

```text
┌────────────────────────┐
│    Data Collection     │
│       GetData/         │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│    Data Preparation     │
│      Cleaning & Prep    │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│     Data Analysis      │
│         & EDA           │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│   Feature Engineering  │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│     Model Training      │
│                         │
│ LR | KNN | RF |         │
│ Prophet | Ensemble |    │
│ XGBoost                 │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│    Model Evaluation     │
│       R² Score          │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│        XGBoost          │
│       R² = 0.9087       │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│          GUI            │
│    User Interaction     │
└────────────┬───────────┘
             │
             ▼
┌────────────────────────┐
│        End User         │
└────────────────────────┘
```

---

# 🛠️ Technologies Used

The project was developed using:

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **XGBoost**
* **Prophet**
* **Matplotlib**
* **Jupyter Notebook**
* **Machine Learning**
* **Feature Engineering**
* **Data Analysis**
* **GUI Development**

---

# 📈 Evaluation Metric

We used the **R² Score** to evaluate the regression models.

R² measures how well a regression model explains the variation in the target variable.

A higher R² generally indicates that the model explains more of the variance in the target data.

For our experiments, the highest obtained score was:

## 🎯 R² = 0.9087

achieved by **XGBoost**.

---

# 👥 Team — FullTank

This project was developed as a team project by:

* **Rewan Shehab**
* **Tasneem Hesham**
* **Nada Elsayed**

The team collaborated across different stages of the project, including **Machine Learning, Modeling, and GUI development**.

---

# 🚀 Project Workflow

### 1️⃣ Data Collection

Gather the required historical and economic data.

### 2️⃣ Data Preparation

Clean and organize the collected data to create a usable dataset.

### 3️⃣ Data Analysis

Explore patterns, relationships, and important variables.

### 4️⃣ Feature Engineering

Create meaningful features that can help the models understand the problem.

### 5️⃣ Model Training

Experiment with different Machine Learning approaches.

### 6️⃣ Model Evaluation

Compare the models using R² Score.

### 7️⃣ Model Improvement

Experiment with Ensemble methods and more advanced models.

### 8️⃣ GUI Development

Create an easy-to-use interface for interacting with the final system.

### 9️⃣ End-to-End Solution

Connect the complete workflow from data to end user.

---

# 💭 Final Takeaway

This project taught us that Machine Learning is not simply:

```text
Dataset → Model → Score
```

A real Machine Learning solution is closer to:

```text
Data
  ↓
Analysis
  ↓
Feature Engineering
  ↓
Modeling
  ↓
Evaluation
  ↓
Interface
  ↓
End User
```

The most important lesson was that choosing a model should come after understanding the data and the problem.

A powerful model cannot compensate for poor understanding of the data.

---

# 📌 Future Improvements

Possible future improvements include:

* Adding more recent fuel-price data.
* Adding additional economic indicators.
* Improving Feature Engineering.
* Performing more extensive Hyperparameter Tuning.
* Testing additional Machine Learning models.
* Improving prediction visualization.
* Deploying the application as a web application.
* Adding more interactive dashboards and analytics.

---

# ⭐ Project Highlights

* 🇪🇬 Egyptian fuel price prediction
* 📊 Exploratory Data Analysis
* 🧹 Data Preparation
* 💡 Feature Engineering
* 🤖 Multiple Machine Learning Models
* 📈 Linear Regression
* 🔎 KNN
* 🌲 Random Forest
* ⏱️ Prophet
* 🔗 Ensemble Learning
* 🚀 XGBoost
* 🎯 R² Score = **0.9087**
* 🖥️ Interactive GUI
* 🌙 Dark & Light Mode
* 🧪 Default Test Data
* 📊 Model Comparison
* ⛽ Fuel Type Selection
* 🔄 Complete End-to-End Pipeline

---

## 📂 Repository Contents

This repository contains the main notebook, prepared datasets, and data collection resources required to understand and reproduce the project.

**FullTank — Egyptian Fuel Price Prediction 🇪🇬⛽**

---

```
```
