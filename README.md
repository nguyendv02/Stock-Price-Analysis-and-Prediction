# Stock Price Analysis and Prediction

## Overview

This project aims to predict both the stock price and the quantity of stocks purchased at a specified time interval from the current moment. Here's a concise description of its input and output:

- Input: Time duration (dd/hh/mm) from the current time.
- Output: Predicted stock price and quantity of stocks purchased at that future time.

Training data for the model includes recorded stock prices, quantities of stocks purchased, and their corresponding timestamps.

## EDA

Visualize to examine the data distribution.

<p align="center">
  <img src="https://github.com/nguyendv02/Stock-Price-Analysis-and-Prediction/assets/137906492/3ca2fe09-a4b0-4d0f-8178-f7055597159f" width="400">
</p>

Calculate the correlation matrix and eliminate attributes with high correlation.

<p align="center">
  <img src="https://github.com/nguyendv02/Stock-Price-Analysis-and-Prediction/assets/137906492/681fc615-4c40-40d1-9bb2-319e327310dd" width="400">
</p>

After plotting the value distributions and Pearson correlations, we observe the following three points:
- The features 'Low', 'High', 'Open', and 'Close' have very high correlation among them.
- The feature 'Open Interest' has a constant value of 0 for all records.
- The ticker for all records is 'FPT'.
Therefore, we should remove the following features: 'Ticker', 'Low', 'High', 'Open', and 'Open Interest' as they do not provide significant value for the target variable.

<p align="center">
  <img src="https://github.com/nguyendv02/Stock-Price-Analysis-and-Prediction/assets/137906492/40625d45-2351-4511-a69b-aadaf7001dee" width="200">
</p>

## Modeling

Data Preprocessing: Normalize 3 attributes: 'Close', 'Volume', and scale, and normalize 'time_scaled' sequence data to fit time series models (in this case, sequence length is 400).

Model Construction and Training: Build and train a deep learning LSTM model with a fixed learning rate (lr) and a learning rate schedule.

## Result

This section presents the results of the model on a test set consisting of 500 data points. The two figures below compare the model's predicted values with actual data:

- The top figure represents stock prices.
- The bottom figure represents the volume of stocks purchased.

<p align="center">
  <img src="https://github.com/nguyendv02/Stock-Price-Analysis-and-Prediction/assets/137906492/9cd55533-d3c2-40dc-a504-2a6f64ada053" width="600">
</p>

Below is a small demo executed directly in a notebook:

<p align="center">
  <image src="https://github.com/nguyendv02/Stock-Price-Analysis-and-Prediction/assets/137906492/2feab3c8-1cc2-4c8b-b1c2-16788ba43e6e" width="600">
  </image>

### Contact:
Email: nguyendv02@gmail.com or 20520657@gm.uit.edu.vn

Faculty of Information Science and Engineering, University of Information Technology, Vietnam National University, Ho Chi Minh City, Vietnam.
