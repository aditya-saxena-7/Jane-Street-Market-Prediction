# Jane Street Market Prediction Challenge 📈

## Description 📊

"Buy low, sell high." It sounds so easy... but in reality, trading for profit has always been a challenging problem, especially in today's fast-paced and complex financial markets. Electronic trading allows for thousands of transactions within fractions of a second, creating nearly unlimited opportunities to find and exploit price differences in real-time.

In a perfectly efficient market, buyers and sellers would have all the necessary information to make rational trading decisions. As a result, products would always stay at their "fair values" and never be undervalued or overpriced. However, financial markets are not perfectly efficient in the real world. 🌍

Developing trading strategies to identify and take advantage of these inefficiencies is challenging. Even if a strategy is profitable now, it might not be in the future, and market volatility makes it impossible to predict the profitability of any given trade with certainty. This uncertainty makes it hard to distinguish good luck from a well-made trading decision. 🤔

### The Challenge 🎯

In the first three months of this challenge, you'll build your own quantitative trading model to maximize returns using market data from a major global stock exchange. Next, you'll test the predictiveness of your models against future market returns and receive feedback on the leaderboard. 📈

Your task is to use historical data, mathematical tools, and technological tools at your disposal to create a model that gets as close to certainty as possible. You will be presented with various potential trading opportunities, which your model must choose to either accept or reject. 💡

A highly predictive model that selects the right trades to execute would play a crucial role in sending market signals that push prices closer to their "fair" values. In other words, a better model will make the market more efficient going forward. However, developing good models is challenging due to many factors, including a very low signal-to-noise ratio, potential redundancy, strong feature correlation, and difficulty in coming up with a proper mathematical formulation. 🧠

Jane Street has spent decades developing their own trading models and machine learning solutions to identify profitable opportunities and quickly decide whether to execute trades. These models help Jane Street trade thousands of financial products each day across 200 trading venues around the world. 🌐

Admittedly, this challenge oversimplifies the depth of the quantitative problems Jane Street professionals work on daily, but it's a fun introduction to a type of data science problem that a Jane Street employee might tackle. Jane Street looks forward to seeing the new and creative approaches the Kaggle community will take to solve this trading challenge. 🚀

### Evaluation 🏅

This competition is evaluated on a utility score. Each row in the test set represents a trading opportunity for which you will be predicting an action value: `1` to make the trade and `0` to pass on it. Each trade `j` has an associated weight and `resp`, representing a return. 💰

### Submission File 📂

To participate, you must submit your predictions using the provided Python time-series API, which ensures that models do not peek forward in time. Here's a template for your Kaggle Notebooks:

```python
import janestreet
env = janestreet.make_env()  # initialize the environment
iter_test = env.iter_test()  # an iterator that loops over the test set

for (test_df, sample_prediction_df) in iter_test:
    sample_prediction_df.action = 0  # make your 0/1 prediction here
    env.predict(sample_prediction_df)
```

### Code Requirements 📝

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
