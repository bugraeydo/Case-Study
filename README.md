# Bus Usage Forecasting

## Overview

This project aims to forecast bus usage for different municipalities using historical data. Two different models, ExponentialSmoothing and a 1D Convolutional Neural Network (CNN), are implemented and compared based on their Root Mean Squared Error (RMSE) performance.

## Dataset

The dataset used in this project contains hourly bus usage data for ten different municipalities. The data can be found [here](https://pi.works/3w8IJbV).

## Methodology

1. Data preprocessing: The dataset is loaded, and the timestamp column is converted to a datetime object. The data is then grouped by hour and municipality, taking the maximum usage value for each group.
2. Train-test split: The dataset is split into training and testing sets based on a specific date range.
3. Model implementation:
    - ExponentialSmoothing: The Holt-Winters Exponential Smoothing model is fit to the training data and used to make predictions on the test data.
    - 1D CNN: A 1D Convolutional Neural Network model is built, trained on the normalized training data, and used to make predictions on the test data.
4. Model evaluation: The RMSE scores are calculated for each model and municipality, allowing for a comparison of their performance.

## Results

The RMSE scores for the ExponentialSmoothing and CNN models are as follows:

| Municipality | ExponentialSmoothing | CNN    |
|--------------|----------------------|--------|
| 0            | 340.9772             | 171.1170 |
| 1            | 120.5679             | 46.9981 |
| 2            | 132.9360             | 66.8967 |
| 3            | 402.2167             | 154.1827 |
| 4            | 976.2654             | 336.7585 |
| 5            | 123.4987             | 39.3344 |
| 6            | 323.8531             | 145.4946 |
| 7            | 320.4777             | 136.7220 |
| 8            | 333.1266             | 136.9544 |
| 9            | 208.3095             | 82.6763 |

Overall, the 1D CNN model outperforms the ExponentialSmoothing model in terms of RMSE for all municipalities.

## Dependencies

- pandas
- numpy
- matplotlib
- statsmodels
- tensorflow
- scikit-learn

## Installation

1. Clone this repository to your local machine.
2. Install the required dependencies using `pip install -r requirements.txt` (assuming you have a `requirements.txt` file).
3. Run the Jupyter Notebook (`Bus_Usage_Forecasting.ipynb`) to see the results.

## License

This project is released under the [MIT License](https://opensource.org/licenses/MIT).

## Acknowledgements

Special thanks to [OpenAI](https://www.openai.com/) for their guidance and support throughout the project.
