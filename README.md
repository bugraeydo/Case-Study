# Bus Usage Forecasting

## Overview

This project aims to forecast bus usage for different municipalities using historical data. Two different models, Exponential Smoothing, a 1D Convolutional Neural Network (CNN), and Long Short-Term Memory (LSTM) are implemented and compared based on their Root Mean Squared Error (RMSE) performance.

## Dataset

The dataset used in this project contains hourly bus usage data for ten different municipalities. The data can be found [here](https://pi.works/3w8IJbV).

## Methodology

1. Data Preprocessing: The dataset is loaded, and the timestamp column is converted to a datetime object. The data is then grouped by hour and municipality, taking the maximum usage value for each group.
2. Train-Test Split: The dataset is split into training and testing sets based on a specific date range.
3. Model Implementation:
    - Exponential Smoothing: The Holt-Winters Exponential Smoothing model is fit to the training data and used to make predictions on the test data.
    - 1D CNN: A 1D Convolutional Neural Network model is built, trained on the normalized training data, and used to make predictions on the test data.
    - LSTM: A Long Short-Term Memory model is built, trained on the normalized training data, and used to make predictions on the test data.
4. Model Evaluation: The RMSE scores are calculated for each model and municipality, allowing for a comparison of their performance.

## Results

The RMSE scores for the Exponential Smoothing, CNN, and LSTM models are as follows:

| Municipality | Exponential Smoothing | CNN     | LSTM     |
|--------------|----------------------|---------|----------|
| 0            | 134.5967             | 134.5967 | 132.5328 |
| 1            | 49.8760              | 49.8760 | 51.1178  |
| 2            | 65.9495              | 65.9495 | 68.6517  |
| 3            | 149.5992             | 149.5992 | 196.1672 |
| 4            | 314.5714             | 314.5714 | 438.0063 |
| 5            | 41.2196              | 41.2196 | 56.4466  |
| 6            | 139.5230             | 139.5230 | 136.3428 |
| 7            | 137.7582             | 137.7582 | 156.0054 |
| 8            | 135.7533             | 135.7533 | 167.8005 |
| 9            | 85.8587              | 85.8587 | 98.1688  |

From the table above, it is clear that the LSTM model tends to have higher RMSE values compared to the Exponential Smoothing and CNN models for most municipalities. This indicates that the LSTM model performs less accurately in predicting the hourly maximum electricity usage compared to the other models. However, the performance may vary depending on the specific municipality. Further analysis and evaluation metrics may be necessary to gain a comprehensive understanding of the models' performance.

## Dependencies

- pandas
- numpy
- matplotlib
- statsmodels
- tensorflow
- scikit-learn

## Installation

1. Clone this repository to your local machine.
2. Install the required dependencies using `pip install -r requirements.txt` (assuming you have a `
