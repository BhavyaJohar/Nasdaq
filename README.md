# Nasdaq

This project aims to predicts whether nasdaq composite price will go up or down for the next day. I used rolling averages and other technical analysis as the parameters for my algorithm. I employed historical price data and technical indicators to build a predictive model. The model's performance is evaluated and improved through feature engineering and hyperparameter tuning.

## Data Collection
### The historical price data for the Nasdaq Composite Index is collected using the yfinance library. The dataset includes:

- Open prices
- High prices
- Low prices
- Close prices
- Volume

## Feature Engineering
### To improve the model's performance, I engineer several new features:

- Technical indicators such as MACD, RSI, Bollinger Bands, Stochastic Oscillator, ATR, and EMA.
- Lag features for Close and Volume to provide historical context.
- Standardization of features using StandardScaler.

## Model Training
I initially trained a Random Forest Classifier with default hyperparameters to establish a baseline. The model is trained on the engineered features to predict whether the closing price will increase the next day.

## Hyperparameter Tuning
### To improve the model's performance, I used Grid Search to find the optimal hyperparameters:

- n_estimators: Number of trees in the forest.
- min_samples_split: Minimum number of samples required to split an internal node.
- max_features: Number of features to consider when looking for the best split.

## Evaluation
### The model is evaluated using several metrics:

- Precision
- Recall
- F1 Score
- Accuracy
- Confusion Matrix

Cross-validation is used to ensure the model's robustness, and the final model is tested on a separate test set.

## Results
### Before Hyperparameter Tuning
- Precision: 0.5289
- Recall: 0.7608
- F1 Score: 0.6241
- Accuracy: 0.5175
### After Hyperparameter Tuning and Feature Engineering
- Precision: 0.5272
- Recall: 0.8262
- F1 Score: 0.6437
- Accuracy: 0.5122

###Explanation of Results
- Precision slightly decreased, but remains similar.
- Recall significantly improved, indicating better identification of positive cases.
- F1 Score improved, showing a better balance between precision and recall.
- Accuracy slightly decreased, but this metric can be misleading in imbalanced datasets.

## Challenges
- Class Imbalance: The dataset might have an imbalance between positive and negative cases, affecting precision and accuracy.
- Overfitting: Initially, the model showed signs of overfitting, performing significantly better on the training data than on the test data.
- Complexity of Financial Data: Stock market data is inherently noisy and complex, making prediction challenging.
   - Going forward I believe it may be best to perform this analysis on a single security or derivative rather than the entire market as a whole 
