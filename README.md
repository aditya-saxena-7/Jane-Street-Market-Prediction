# Jane Street Market Prediction Challenge 📈

### Description 📊

"Buy low, sell high." It sounds so easy... but in reality, trading for profit has always been a challenging problem, especially in today's fast-paced and complex financial markets. Electronic trading allows for thousands of transactions within fractions of a second, creating nearly unlimited opportunities to find and exploit price differences in real-time.

In a perfectly efficient market, buyers and sellers would have all the necessary information to make rational trading decisions. As a result, products would always stay at their "fair values" and never be undervalued or overpriced. However, financial markets are not perfectly efficient in the real world. 🌍

Developing trading strategies to identify and take advantage of these inefficiencies is challenging. Even if a strategy is profitable now, it might not be in the future, and market volatility makes it impossible to predict the profitability of any given trade with certainty. This uncertainty makes it hard to distinguish good luck from a well-made trading decision. 🤔

### The Challenge 🎯

I will be building my own quantitative trading model to maximize returns using market data from a major global stock exchange. Next, I'll test the predictiveness of my models against future market returns. 📈

Trading for profit in today's fast-paced and complex financial markets is a challenging task. In this competition, I was tasked with developing quantitative trading models to identify and take advantage of inefficiencies in a global stock exchange. The goal was to maximize returns using historical market data and mathematical and technological tools. 🔧📉

My task was to use historical data, mathematical tools, and technological tools at my disposal to create a model that gets as close to certainty as possible. 💡

A highly predictive model that selects the right trades to execute would play a crucial role in sending market signals that push prices closer to their "fair" values. In other words, a better model will make the market more efficient going forward. However, developing good models is challenging due to many factors, including a very low signal-to-noise ratio, potential redundancy, strong feature correlation, and difficulty in coming up with a proper mathematical formulation. 🧠

Based on Kaggle Competition Overview: Jane Street has spent decades developing their own trading models and machine learning solutions to identify profitable opportunities and quickly decide whether to execute trades. These models help Jane Street trade thousands of financial products each day across 200 trading venues around the world. 🌐

Admittedly, this challenge oversimplifies the depth of the quantitative problems Jane Street professionals work on daily, but it's a fun introduction to a type of data science problem that a Jane Street employee might tackle. Jane Street looks forward to seeing the new and creative approaches the Kaggle community will take to solve this trading challenge. 🚀

### Data 📊

- **Historical price and volume data** for a range of financial instruments (stocks, indices, etc.). 📈📉
- **Relevant market indicators** and macroeconomic data. 🌍
- **Information on potential trading opportunities**, including weights and return information for each trade. 📜
- The data should be divided into **training and testing datasets**. 🗂️

The dataset can be found here: [Jane Street Dataset](https://www.kaggle.com/competitions/jane-street-market-prediction/data)

### Tasks 🛠️

1. **Data Exploration**: Explore the data to understand its structure and relationships between variables. 🔍
2. **Model Development**: Build predictive models that determine whether to execute a trade for each trading opportunity presented. You can use a variety of machine learning and quantitative finance techniques. 🤖💼
3. **Testing and Validation**: Test the models against future market returns to evaluate their predictive power. 📅✔️
4. **Utility Maximization**: Develop models that maximize the utility score by selecting the right trades to execute, thus pushing prices closer to "fair" values. 📊

### Challenges and Considerations ⚠️

- **Signal-to-Noise Ratio**: Develop models that effectively filter out noise in the data to make accurate predictions and decisions. 🔇🔍
- **Redundancy and Feature Correlation**: Address potential redundancy and strong correlations among features in the data. 🔗📉
- **Mathematical Formulation**: Create mathematical formulations for trading models that maximize returns. 📐💹

### Quick Summary of My Entire Code

#### 1. **Data Preparation and Exploration**
   - **Loading and Cleaning Data**:
     - Load the training and features data.
     - Handle missing values by calculating mean imputation values.
   - **Feature Exploration**:
     - Analyze the features to understand their distributions and relationships.
   - **Dimensionality Reduction**:
     - Use t-SNE to visualize high-dimensional data in 2D space.
   - **Cluster Analysis**:
     - Use K-means clustering and silhouette scores to determine the optimal number of clusters.

#### 2. **Data Balancing and Splitting**
   - **Class Balancing**:
     - Separate the data into abundant (action=0) and rare (action=1) classes.
     - Shuffle and split the abundant class data into three chunks.
     - Combine each chunk with the rare class data to create balanced datasets.
   - **Train-Test Split**:
     - Split each balanced dataset into training and validation sets (90% training, 10% validation).

#### 3. **Modeling**
   - **LightGBM Models**:
     - Set hyperparameters for LightGBM.
     - Train three LightGBM models on different balanced datasets with early stopping.
     - Save the trained LightGBM models.
   - **Neural Network Models**:
     - Define a custom neural network architecture using TensorFlow.
     - Train the neural network on different balanced datasets.
     - Compile and fit the model using AUC as the evaluation metric.

#### 4. **Feature Importance**
   - **Visualize Feature Importance**:
     - Plot feature importance for each LightGBM model to identify the most influential features.

#### 5. **Real-Time Prediction**
   - **Initialize Jane Street Environment**:
     - Create an environment for making real-time predictions.
   - **Make Predictions**:
     - Iterate over the test data.
     - Preprocess test samples, handle missing values, and make predictions using the trained models.
     - Average the predictions from multiple models and apply a threshold to determine the action.
     - Submit the predictions to the environment.

### Methodology

1. **Data Preparation**:
   - Clean and preprocess the data.
   - Explore features and visualize distributions.
   - Handle missing values using mean imputation.

2. **Class Balancing**:
   - Balance the dataset to ensure equal representation of classes in training.
   - Create multiple balanced chunks for robust training.

3. **Model Training**:
   - Use LightGBM for tree-based modeling with hyperparameter tuning.
   - Employ neural networks for deep learning-based predictions.
   - Train multiple models to capture diverse patterns in the data.

4. **Feature Importance Analysis**:
   - Evaluate and visualize the importance of each feature to understand their impact on predictions.

5. **Real-Time Predictions**:
   - Implement real-time prediction logic using the Jane Street environment.
   - Preprocess incoming data, make predictions, and submit actions based on model outputs.

### Evaluation

1. **Metrics**:
   - **AUC (Area Under the Curve)**: Used as the primary metric for evaluating model performance.

2. **Early Stopping**:
   - Implemented in LightGBM training to prevent overfitting by stopping training if the validation score doesn't improve for 50 rounds.

3. **Model Validation**:
   - Split data into training and validation sets to evaluate model performance on unseen data.
   - Monitor validation AUC to assess and compare model effectiveness.

### Complete Code Summary

The entire code involves:
- Loading and preprocessing the data.
- Handling missing values.
- Exploring and visualizing features.
- Balancing the dataset and creating multiple training chunks.
- Training LightGBM and neural network models.
- Evaluating feature importance.
- Making real-time predictions using a production environment.

Each step is designed to ensure robust model training, effective feature utilization, and accurate real-time predictions, validated using appropriate metrics and techniques.

Entire Walkthrough of the codebase can be found [here](https://github.com/aditya-saxena-7/Jane-Street-Market-Prediction/blob/main/JaneStreetSubmission.ipynb)

### Evaluation 🏅

This competition is evaluated on a utility score. Each row in the test set represents a trading opportunity for which you will be predicting an action value: `1` to make the trade and `0` to pass on it. Each trade `j` has an associated weight and `resp`, representing a return. 💰

### Submission File 📂

I had to submit my predictions using the provided Python time-series API, which ensured that models do not peek forward in time. Here's a template from my Kaggle Notebooks:

```python
import janestreet
env = janestreet.make_env()  # initialize the environment
iter_test = env.iter_test()  # an iterator that loops over the test set

for (test_df, sample_prediction_df) in iter_test:
    sample_prediction_df.action = 0  # make your 0/1 prediction here
    env.predict(sample_prediction_df)
```

### Kaggle Code Requirements 📝

- **This is a Code Competition** 🔍
- Submissions must be made through Notebooks.
- Training is not required in Notebooks.
- Your notebook must use the time-series module to make predictions.
- CPU Notebook ≤ 5 hours run-time.
- GPU Notebook ≤ 5 hours run-time.
- TPU Notebooks are not supported.
- Freely & publicly available external data is allowed, including pre-trained models.

### Citation 📚

cnyberg, dd_engi, janestreet-jjia, Maggie, Will Cukierski. (2020). Jane Street Market Prediction. Kaggle. [Jane Street Market Prediction](https://kaggle.com/competitions/jane-street-market-prediction)
