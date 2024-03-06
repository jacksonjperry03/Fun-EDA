# [Possum Predictions using Regression Models](./possum.ipynb)

### Data Acquisition

The dataset, ["Possum Regression"](./possum.csv), was retrieved from [https://www.kaggle.com/datasets/abrambeyer/openintro-possum](https://www.kaggle.com/datasets/abrambeyer/openintro-possum).

## Overview
This Jupyter notebook explores the task of predicting the age of possums based on various features using regression models. The dataset used contains information about possums, including their age, sex, physical measurements, and more.

## Requirements
- Python 3
- Jupyter Notebook
- Libraries: pandas, scikit-learn, matplotlib, seaborn

## Contents
1. **Introduction**: Provides an overview of the task and dataset.
2. **Data Preprocessing**: Loading the dataset, handling missing values, and identifying the target variable and features.
3. **Modeling**: 
   - Initial attempt with Linear Regression
   - Univariate Linear Regression
   - Decision Tree Regressor
   - Support Vector Regression (SVR)
4. **Model Evaluation**: Comparing the performance of different models using mean squared error and R-squared scores.
5. **Time Analysis**: Analyzing the computational time for fitting and scoring each model.
6. **Conclusion**: Summary of findings and recommendation for model selection.

## Conclusion
Based on the analysis, the Decision Tree Regressor emerged as the most suitable model for predicting possum age, providing a good balance between performance and computational efficiency. However, model selection may vary based on specific requirements and dataset characteristics.

<sub> 
This README document was partially generated with the assistance of artificial intelligence.
</sub>

