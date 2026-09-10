# ⛽ Automated Hybrid Fuel Price & Global Market Data Pipeline

> How to integrate government pricing decrees with volatile, real-time global macroeconomic factors? 🌍

## 📖 The Story & The Challenge
When building a predictive analysis system for local fuel prices, the golden rule isn't about complex modeling—it's about **clean, reliable data**. 

I faced a major engineering dilemma: official fuel prices in Egypt are set by government decrees rather than public live exchange tickers. Relying purely on automated web scraping for historical government decrees is fragile and unreliable. 

To solve this, I designed a **Hybrid Data Pipeline** that bridges static historical records with live automated global indicators.

---

## 🛠️ Problems & Engineering Solutions

* 🛑 **Problem 1: Fragile Historical Scraping**
  * *Issue:* Official fuel prices are scattered across news articles or charts and lack a stable public API. Scraping them live risks breaking the pipeline if sources change or go down.
  * ✅ **Solution:** Built a verified local historical foundation (`raw data 1.csv`) capturing official pricing events for Octane 80, 92, 95, and Diesel.

* 🛑 **Problem 2: Macroeconomic Volatility**
  * *Issue:* Local prices are heavily driven by global factors (Inflation, USD exchange rates, and Brent Crude Oil prices) which fluctuate daily.
  * ✅ **Solution:** Implemented automated live global data extraction via `yfinance` to pull daily macroeconomic indicators (`BZ=F` and `EGP=X`) from 2014 to present.

* 🛑 **Problem 3: Mimicking the Pricing Committee**
  * *Issue:* Pricing committees don't react to yesterday's oil price; they evaluate market trends over a rolling window.
  * ✅ **Solution:** Computed 3-month (90-day) rolling averages to accurately simulate real-world committee evaluations:
    ```python
    market_df['Oil_3M_Avg'] = market_df['Oil_Price'].rolling(window=90).mean()
    market_df['USD_3M_Avg'] = market_df['USD_Rate'].rolling(window=90).mean()
    ```

* 🛑 **Problem 4: Preventing Data Leakage During Merge**
  * *Issue:* Blending static local decree dates with daily financial time series without causing time-travel bias or data leakage.
  * ✅ **Solution:** Used precise time-series backward merging (`pd.merge_asof`) to align local events with the latest valid macroeconomic averages.

---

## 📂 Project Structure & File Descriptions

Here is a breakdown of the files inside the `GetData` directory:

| File Name | Description |
| :--- | :--- |
| **`raw data 1.csv`** | The curated local historical dataset containing official Egyptian fuel pricing events, categories, and vehicle examples. |
| **`Download oil & USD.ipynb`** | An automated script/notebook dedicated to fetching, cleaning, and downloading daily Brent Oil and USD/EGP rates from Yahoo Finance. |
| **`raw data 1.ipynb`** | The main orchestration pipeline notebook: loads local data, merges with global market factors using `merge_asof`, computes rolling averages, and outputs the final dataset. |
| **`market_factors_history.7z`** | Compressed archive holding the historical global market factors dataset (`market_factors_history.csv`) to save repository space. |
| **`final_training_dataset.csv`** | The final, clean, and merged training dataset ready to feed machine learning models (Random Forest, XGBoost, Prophet, etc.). |

---

## 🚀 How to Run the Pipeline

1. Run **`Download oil & USD.ipynb`** to fetch and update the latest global market factors from Yahoo Finance.
2. Run **`raw data 1.ipynb`** to execute the pipeline, merge local decrees with global averages, and generate the final training dataset.

---
💡 *“Sometimes, the best architecture isn't the most complex one—it's the smart combination of reliable static historical data and dynamic automated live feeds.”*
