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

| Municipality | Exponential Smoothing | CNN    | LSTM   |
|--------------|----------------------|--------|--------|
| 0            | 340.977              | 134.597| 132.533|
| 1            | 120.568              | 49.876 | 51.118 |
| 2            | 132.936              | 65.950 | 68.652 |
| 3            | 402.217              | 149.599| 196.167|
| 4            | 976.265              | 314.571| 438.006|
| 5            | 123.499              | 41.220 | 56.447 |
| 6            | 323.853              | 139.523| 136.343|
| 7            | 320.478              | 137.758| 156.005|
| 8            | 333.127              | 135.753| 167.800|
| 9            | 208.309              | 85.859 | 98.169 |


From the table above, we can observe the RMSE scores for each model and municipality. It is evident that the performance of the models varies across different municipalities. In general, the CNN model outperforms the Exponential Smoothing and LSTM models in terms of lower RMSE values for most municipalities. However, the LSTM model performs better than the CNN model for a few municipalities such as municipality 4 and municipality 8. It's important to note that the performance can vary depending on the specific characteristics of the data and the modeling approach.

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
