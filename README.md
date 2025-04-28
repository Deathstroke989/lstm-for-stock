Stock Price Prediction Using LSTM Neural Network

Project Title: NIFTY Bank Index Price Prediction with LSTM

Objective:

To develop a predictive model using Long Short-Term Memory (LSTM) neural networks to forecast the closing prices of the NIFTY Bank Index (^NSEBANK) based on historical stock price data.

Project Overview:

This project leverages deep learning techniques, specifically LSTM, to predict future stock prices of the NIFTY Bank Index. Historical price data is sourced, preprocessed, and fed into an LSTM model to capture temporal patterns and trends. The model is trained, evaluated, and visualized to compare predicted prices against actual prices, providing insights into its predictive performance.

Key Components:

    Data Acquisition:
        Historical closing prices of the NIFTY Bank Index are downloaded from Yahoo Finance (yfinance) for the period from January 1, 2020, to January 1, 2023.
        The dataset includes daily closing prices, which serve as the primary input for the model.
    Data Preprocessing:
        Normalization: The closing prices are scaled to a range of [0, 1] using MinMaxScaler to improve model training efficiency and convergence.
        Sequence Creation: The data is transformed into sequences of 60 days (sequence length) to predict the next day's closing price, creating input-output pairs for supervised learning.
        Train-Test Split: The dataset is split into 80% training and 20% testing sets to evaluate model performance on unseen data.
    Model Architecture:
        A Sequential LSTM model is built using the Keras framework with the following layers:
            LSTM Layer 1: 100 units, returns sequences, input shape of (60, 1).
            LSTM Layer 2: 100 units, processes the output of the first LSTM layer.
            Dense Layer: Outputs a single value representing the predicted scaled price.
        The model is compiled with the Adam optimizer and Mean Squared Error (MSE) loss function.
    Training:
        The model is trained on the training set for 20 epochs with a batch size of 32.
        A validation split of 10% is used during training to monitor performance and prevent overfitting.
    Prediction and Evaluation:
        The trained model predicts prices on the test set, and the scaled predictions are inverse-transformed to obtain actual price values.
        The model's performance is evaluated using the test loss (MSE).
        Predicted prices are compared with actual prices through visualization.
    Visualization:
        A line plot is generated using matplotlib to display actual vs. predicted prices over time.
        The plot includes labeled axes, a title, a legend, and a grid for clarity, enabling visual assessment of the model’s accuracy.

Technologies Used:

    Python Libraries: yfinance (data acquisition), numpy (data manipulation), sklearn (data preprocessing), keras (LSTM model), matplotlib (visualization).
    Deep Learning Framework: Keras with TensorFlow backend.

Outcomes:

    The model provides a predictive tool for estimating future NIFTY Bank Index prices based on historical trends.
    The visualization highlights the model’s ability to capture price patterns, with potential deviations indicating areas for improvement.
    The test loss quantifies the model’s predictive accuracy on unseen data.

