
readme_backtest 
# Cash 3 Lottery Historical Backtesting Simulation

This repo contains a detailed simulation engine that retroactively tests the accuracy of different predictive models on Georgia Cash 3 draws. Instead of predicting future numbers, this system walks **day-by-day** through historical data, **pretending it's in the past** and generating predictions using only past results.

---

## 🎯 Goal

To measure the **true real-world effectiveness** of various prediction models by:
- Running them on **only the data available before** each draw.
- Comparing their output to the **known actual winning number**.
- Recording match statistics over **hundreds of draws** to determine if any method performs better than chance.

---

## 🔄 How It Works

1. Load full Cash 3 dataset (sorted from oldest to newest).
2. Starting after the first 10 draws (to build initial model memory):
   - At draw i:
     - Use draws 0 to i to generate predictions.
     - Compare prediction against draw i+1 (which the model has not seen).
3. Repeat for all draws until the latest.
4. Log the following:
   - Actual winning number
   - Each method's prediction
   - Hit type (Exact, 2-digit, 1-digit match)
   - Rolling accuracy for each method

---

## 🤖 Predictive Models Tested

- **Markov Chain**
- **Frequency-Weighted**
- **ARIMA Time Series**
- **Hot/Cold Digit Analysis**
- **Sum & Parity Heuristics**
- **Digit Difference Patterns**
- **Gap Time Since Last Seen**
- **Modulo Cycles**
- **Entropy Scoring**
- **Machine Learning Model (RandomForest)**
- **Bayesian Probabilities**

---

## 📈 Output

- `historical_predictions_2025.csv` — Daily model predictions + actuals
- `historical_accuracy_2025.csv` — Summary of how well each method performed

Example accuracy metrics logged:
- `Exact Match %`
- `2-digit Match %`
- `1-digit Match %`
- `Top N performance if we pick top 10 guesses per day`

---

## 🔍 Why This Is Valuable

✅ No need to wait for new draws to validate your models  
✅ Shows how each method behaves over time — helps **fine-tune** or **eliminate** underperformers  
✅ Let’s you train **hybrid models** or ensemble methods using the best of all techniques  
✅ Allows for future "live" model deployment with high confidence in baseline performance

---

## 📁 Files

- `full_backtest.py` — Runs the full day-by-day simulation
- `historical_predictions_2025.csv` — All model outputs per day
- `historical_accuracy_2025.csv` — Final scorecard

---

## 🧠 Philosophical Insight

While the lottery is said to be random, this project explores:
- Whether **short 3-digit games** like Cash 3 show exploitable tendencies
- If statistical pressure, operational quirks, or entropy shifts allow for measurable patterns

---

**Built with curiosity by hamza/knightinfected **
"""


