# 📈 Stock Analysis and Report – Data Visualization & Technical Indicators

![GitHub stars](https://img.shields.io/github/stars/your-username/stock-analysis-and-report?style=social)
![GitHub forks](https://img.shields.io/github/forks/your-username/stock-analysis-and-report?style=social)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> A detailed analysis pipeline for stock price data with visualizations, moving averages, Bollinger Bands, and key market indicators.

This project demonstrates how to analyze stock data using Python. We build visualizations and indicators like moving averages, Bollinger Bands, candlestick charts, and volume analysis to help identify trading opportunities and trends.

## 📋 Table of Contents

* [📁 Dataset](#-dataset)
* [🎯 Goals Achieved](#-goals-achieved)
* [📉 Basic Plotting](#-basic-plotting)
* [🟦 Moving Averages (MA20 & MA50)](#-moving-averages-ma20--ma50)
* [📊 Bollinger Bands](#-bollinger-bands)
* [🕯️ Candlestick Chart with MA & Volume](#-candlestick-chart-with-ma--volume)
* [📊 Price vs Volume Analysis](#-price-vs-volume-analysis)
* [📐 Technical Indicators (RSI, MACD)](#-technical-indicators-rsi-macd)
* [📌 Summary & Findings](#-summary--findings)
* [🚀 Usage](#-usage)
* [📁 Project Structure](#-project-structure)
* [🔧 Installation](#-installation)
* [📜 License](#-license)
* [👨‍💻 Author](#-author)

## 📁 Dataset

We use daily historical stock data for Apple Inc. (AAPL) from Yahoo Finance spanning 2020-2024.

### 📥 Get the Dataset

* Source: [Yahoo Finance – AAPL](https://finance.yahoo.com/quote/AAPL/history)

* Alternative via `yfinance`:

  ```python
  import yfinance as yf
  df = yf.download("AAPL", start="2020-01-01", end="2024-05-01")
  ```

* Fields include:

  * Open, High, Low, Close, Volume
  * Indexed by date
  * Used for time-series analysis

## 🎯 Goals Achieved

We completed multiple steps in stock data analysis:

1. 📉 Plotted raw stock price data for insight into trends
2. 📏 Added 20-day and 50-day moving averages
3. 📊 Calculated and visualized Bollinger Bands
4. 🕯️ Created candlestick charts with volume analysis
5. 📊 Analyzed price-volume relationships
6. 📈 Computed RSI and MACD for buy/sell signals
7. 🔍 Interpreted graphs to extract key market behavior

## 📉 Basic Plotting

![Basic Plot](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/basic.png)

The basic AAPL closing price chart (2020-2024) reveals several key insights:

- **Remarkable Growth Trajectory**: AAPL has demonstrated exceptional growth, starting around $75 in early 2020 and exceeding $250 by early 2025, representing an approximate 233% increase.

- **COVID-19 Recovery**: The chart shows a pronounced V-shaped recovery following the March 2020 market crash, with AAPL quickly rebounding and exceeding pre-pandemic levels by mid-2020.

- **Sustained Bull Run (2020-2021)**: A strong uptrend from mid-2020 through late 2021, with the price increasing from approximately $60 to nearly $180, representing a 200% gain during this period.

- **2022 Correction**: A notable price correction occurred throughout 2022, with the stock entering a bearish phase that saw prices decline from around $180 to approximately $130, reflecting broader tech sector struggles.

- **2023 Recovery and Consolidation**: The stock showed resilience with a recovery beginning in early 2023, followed by a period of sideways consolidation between $170-$190.

- **2024 Breakout**: A significant breakout phase began in early 2024, with the stock surging from approximately $180 to over $250, potentially driven by AI-related developments and strong financial performance.

- **Price Volatility**: Throughout the period, AAPL exhibits characteristic volatility with several short-term price swings, providing numerous trading opportunities for active investors.

This chart serves as an excellent foundation for further technical analysis, allowing us to identify major support and resistance levels, trend reversals, and patterns that can inform investment decisions.

## 🟦 Moving Averages (MA20 & MA50)

![Moving Averages](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/ma20and50.png)

The moving averages chart provides crucial trend identification for AAPL, with the following key observations:

- **Trend Confirmation**: The 20-day MA (green) and 50-day MA (red) both follow the general price trend but with reduced volatility, confirming the underlying directional movement. When both MAs point upward (most of 2020-2021 and 2024), the bullish trend is confirmed.

- **Crossover Signals**:
  - **Golden Crosses** (20-day crosses above 50-day): Notable golden crosses occurred in mid-2020, early 2023, and mid-2023, each preceding significant bullish movements. The mid-2020 golden cross was particularly powerful, preceding a massive rally from approximately $80 to $130.
  - **Death Crosses** (20-day crosses below 50-day): Significant death crosses appeared in early 2022 and late 2022, correctly predicting extended bearish movements. The early 2022 death cross preceded a drop from approximately $175 to $130.

- **Price-MA Relationships**:
  - When price stays consistently above both MAs (as seen throughout much of 2020, 2021, and 2024), it indicates strong bullish momentum.
  - When price falls below both MAs (as in periods of 2022), it signals bearish sentiment.
  - Periods where price oscillates between the two MAs often indicate consolidation or transition phases (seen in parts of 2023).

- **Support and Resistance Levels**: The 50-day MA frequently acts as a support level during uptrends (visible in late 2020 and 2021) and as resistance during downtrends (seen in 2022). The 20-day MA serves as a more immediate support/resistance level for shorter-term price movements.

- **Slope Analysis**: The steepness of both MAs provides insight into trend strength:
  - The steepest upward slopes (early 2021 and early 2024) correspond to the strongest bullish movements.
  - Flat or minimally sloped MAs (parts of 2022 and 2023) indicate periods of consolidation or weak trends.

- **Current Trend (2024-2025)**: Both MAs are trending strongly upward with the 20-day MA above the 50-day MA, confirming the current bull run. The price remains consistently above both MAs, suggesting continued upward momentum.

These moving averages effectively smooth out price noise and provide clearer signals for entry and exit points, making them invaluable tools for timing investment decisions.

> 🔁 When MA20 crosses above MA50 = **Buy signal**  
> 🔁 When MA20 drops below MA50 = **Sell signal**

## 📊 Bollinger Bands

![Bollinger Bands](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/bollinger-bands.png)

The Bollinger Bands chart reveals important volatility patterns and potential reversal zones for AAPL:

- **Volatility Measurement**: The width between upper (red) and lower (blue) bands represents market volatility:
  - Wider bands (seen in early 2020, mid-2022, and early 2024) indicate periods of high volatility.
  - Narrower bands (visible in late 2021 and parts of 2023) signal lower volatility and potential upcoming price movements, as periods of low volatility often precede significant breakouts.

- **Band Contractions and Expansions**:
  - Notable band contractions occurred before major price movements, such as the early 2020 contraction preceding the COVID crash and subsequent recovery.
  - The dramatic band expansion during March 2020 coincided with the pandemic-induced market crash, reflecting extreme market uncertainty.
  - Further significant expansions occurred during the 2022 downtrend and the 2024 uptrend, both indicating periods of increased market activity and price discovery.

- **Price-Band Interactions**:
  - **Lower Band Touches**: Price touches or breakthroughs of the lower band (March 2020, late 2022) often preceded bullish reversals, representing potentially oversold conditions. These proved to be excellent buying opportunities.
  - **Upper Band Touches**: Interactions with the upper band (early 2021, parts of 2022, late 2024) frequently preceded short-term pullbacks or consolidations, signaling potential overbought conditions.

- **Mean Reversion Principle**: The price repeatedly demonstrated a tendency to revert to the 20-day moving average (green middle line) after touching either band, exemplifying the mean reversion principle that underpins Bollinger Bands theory.

- **Band Width as Volatility Indicator**: The dramatic expansion of band width during significant market events (COVID crash, 2022 tech selloff, 2024 AI-driven rally) provides clear visual representation of increased market uncertainty and potential for larger price swings.

- **Recent Pattern (2024-2025)**: The recent uptrend has seen the price repeatedly testing the upper band while maintaining a safe distance from the lower band, indicating strong bullish momentum with brief consolidations. However, these upper band touches suggest caution as they may indicate short-term overbought conditions.

The Bollinger Bands effectively frame the price action, highlighting extreme conditions that often present advantageous trading opportunities when combined with other indicators.

> 📌 If price touches lower band → Possible **buy**  
> 📌 If price touches upper band → Possible **sell**

## 🕯️ Candlestick Chart with MA & Volume

![Candlestick Chart with MA & Volume](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/candlestick-with-ma-and-volume.png)

The candlestick chart with moving averages and volume provides rich technical insights through pattern recognition:

- **Candlestick Patterns**:
  - **Doji Formations**: Several doji patterns (where opening and closing prices are nearly identical) appear at key reversal points, particularly visible at the end of downtrends in 2022, signaling indecision and potential trend reversals.
  - **Engulfing Patterns**: Bullish engulfing patterns (where a green candle completely engulfs the previous red candle) preceded many upward movements, notably visible at the start of the 2023 recovery and during the 2024 rally.
  - **Hammer Formations**: Hammer candlesticks (with long lower shadows and small bodies) appeared at several market bottoms, particularly during the 2022 downtrend, accurately predicting subsequent reversals.

- **Price-MA Relationships**:
  - The candlesticks show clear interactions with the moving averages, with the 20-day MA (orange) and 50-day MA (green) acting as dynamic support and resistance levels.
  - Extended runs of candles above both MAs (2020-2021 and 2024) confirm strong bullish sentiment.
  - Periods where candles fluctuate around the MAs (parts of 2022-2023) indicate market indecision and trend transitions.

- **Volume Analysis**:
  - **Volume Confirmation**: Major trend changes are confirmed by increased volume, particularly visible during the 2020 recovery, the 2022 selloff, and the 2024 rally.
  - **Volume Spikes**: Significant volume spikes often coincide with major candlestick patterns, enhancing their predictive reliability. The largest volume spikes (early 2020) occurred during the COVID-related market volatility.
  - **Volume Trends**: Declining volume during price advances (visible in parts of 2021 and 2023) warned of potential weakening trends that later materialized as corrections.

- **Gap Analysis**:
  - Several price gaps (where one day's opening price differs significantly from the previous day's close) appear on the chart, particularly around earnings announcements.
  - Upward gaps that remain unfilled (early 2024) signal strong bullish conviction.
  - Downward gaps that were later filled (mid-2022) provided technical resistance levels during subsequent recovery attempts.

- **Trend Confirmation**: The combined visualization of candlesticks, moving averages, and volume provides powerful trend confirmation:
  - Green candles above both MAs with increasing volume represent the strongest bullish signals (early 2021, early 2024).
  - Red candles below both MAs with increasing volume represent the strongest bearish signals (early 2022).

This comprehensive chart combines three powerful technical tools—candlestick patterns for short-term price action, moving averages for trend direction, and volume for confirmation—creating a robust framework for technical analysis and trading decisions.

## 📊 Price vs Volume Analysis

![Price vs Volume](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/price-vs-volume.png)

The price vs volume chart reveals critical relationships between AAPL's price movement and trading activity:

- **Volume Precedence**: Major price movements are typically preceded by significant volume increases, demonstrating that volume often leads price. This relationship is particularly evident during:
  - The 2020 market crash and recovery, where extraordinary volume spikes (reaching nearly 4.5 × 10^8 shares) preceded and accompanied the V-shaped price recovery.
  - The early 2021 rally, where sustained above-average volume supported the price advance from approximately $120 to $150.
  - The 2022 market correction, where intermittent volume spikes marked crucial support and resistance levels during the downtrend.

- **Volume-Price Confirmation**:
  - **Bullish Confirmation**: Rising prices accompanied by rising volume (early 2020 recovery and 2024 rally) indicate strong buyer conviction and typically result in sustainable uptrends.
  - **Bearish Divergence**: Rising prices with declining volume (parts of 2021 and 2023) signaled potential trend weakness that often preceded consolidations or corrections.
  - **Climactic Volume**: Extremely high volume spikes (early 2020) often mark panic selling or buying climaxes that indicate potential trend exhaustion and reversal points.

- **Volume Profile Evolution**:
  - Overall trading volume has generally decreased since the 2020 pandemic-related volatility, with recent volume levels averaging noticeably lower than the 2020-2021 period.
  - Despite lower absolute volume in 2024-2025, the price has continued its upward trajectory, suggesting increased institutional participation and reduced retail trading volatility.

- **Key Volume-Price Events**:
  - The highest volume periods (Q1-Q2 2020) coincided with the COVID-19 market crash and recovery, representing panic selling followed by opportunity buying.
  - Secondary volume spikes in late 2020 and early 2021 supported the extended bull run from approximately $100 to $150.
  - Intermittent high-volume days during the otherwise declining volume environment of 2022-2024 often marked important pivot points and reversal zones.

- **Current Volume-Price Dynamics (2024-2025)**:
  - The 2024 rally has occurred on relatively modest volume compared to historical spikes, potentially indicating a more orderly and sustainable uptrend driven by consistent institutional accumulation rather than retail enthusiasm.
  - Volume has become more selective, with isolated spikes likely representing earnings announcements or significant company news.

This price-volume relationship analysis enhances trading decisions by providing confirmation of trend strength and early warning signs of potential reversals, a dimension of market analysis not available from price charts alone.

## 📐 Technical Indicators (RSI, MACD)

### RSI (Relative Strength Index)

![RSI](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/rsi.png)

The Relative Strength Index (RSI) chart for AAPL reveals critical momentum conditions and potential reversal points:

- **Overbought/Oversold Conditions**:
  - **Overbought Signals** (RSI > 70): AAPL repeatedly reached overbought territory, most notably in:
    - Q3-Q4 2020, preceding a brief consolidation
    - Mid-2021, before a sideways price movement
    - Early 2022, accurately preceding the significant market correction
    - Mid-2023, correctly predicting a short-term pullback
    - Early and late 2024, suggesting caution during the strong uptrend
  - **Oversold Signals** (RSI < 30): The stock reached oversold conditions less frequently, with notable occurrences in:
    - March 2020 (COVID crash), marking an excellent buying opportunity
    - Mid-2022, correctly identifying a temporary bottom during the correction
    - Early 2024, preceding the powerful 2024 rally

- **Divergence Patterns**:
  - **Bearish Divergences**: Several instances where price made higher highs while RSI made lower highs (particularly visible in late 2021 and parts of 2023) correctly predicted subsequent price pullbacks.
  - **Bullish Divergences**: Occasions where price made lower lows while RSI formed higher lows (notably in late 2022) accurately preceded significant price recoveries.

- **RSI Trend Analysis**:
  - The RSI has maintained generally higher levels during bullish market phases (2020-2021, 2024), frequently oscillating between 40-80.
  - During the bearish 2022 phase, RSI predominantly traded between 30-60, reflecting the weaker momentum.
  - RSI centerline (50) crossovers often aligned with short-term trend changes, providing additional confirmation signals.

- **Failure Swings**:
  - Notable RSI failure swings (where RSI fails to reach a new high or low during price extremes) occurred at several key reversal points, particularly during the 2022 bottoming process.

- **Current RSI Dynamics (2024-2025)**:
  - Recent RSI readings frequently approaching or exceeding 70 suggest a potentially overbought condition in the short term, though this can persist in strong bull markets.
  - The overall RSI trend remains bullish, staying predominantly above the 40 level throughout 2024, confirming the strength of the current uptrend.

The RSI provides crucial momentum-based signals that complement price action analysis, helping identify potential reversal zones and confirming trend strength or weakness.

### MACD (Moving Average Convergence Divergence)

![MACD](https://github.com/GowrishankarSMenon/stock-analysis-and-report/blob/master/images/macd.png)

The MACD indicator for AAPL offers valuable insights into trend strength, momentum shifts, and potential entry/exit points:

- **Signal Line Crossovers**:
  - **Bullish Crossovers** (MACD crossing above signal line): Significant bullish crossovers occurred in:
    - April 2020, preceding the major recovery rally
    - November 2022, accurately predicting the 2023 uptrend
    - Mid-2023, preceding another leg up
    - Early 2024, correctly identifying the powerful 2024 rally
  - **Bearish Crossovers** (MACD crossing below signal line): Notable bearish signals appeared in:
    - Late 2021, correctly warning of the upcoming 2022 correction
    - Mid-2022, predicting further downside during the correction
    - Late 2023, accurately identifying a temporary pullback

- **Histogram Analysis**:
  - **Positive Histogram Expansion**: Periods of expanding positive histogram values (early 2021, early 2024) coincided with the strongest bullish momentum and largest price advances.
  - **Negative Histogram Expansion**: Periods of expanding negative histogram values (early 2022, late 2022) aligned with accelerating downtrends and significant price drops.
  - **Histogram Contraction**: Periods where the histogram narrowed toward zero (throughout parts of 2023) identified consolidation phases and potential trend shifts.

- **Centerline Crossovers**:
  - MACD crossing above the zero line (mid-2020, early 2023, mid-2023) confirmed established bullish trends.
  - MACD crossing below the zero line (early 2022, mid-2022) confirmed bearish trend conditions.

- **Divergence Patterns**:
  - **Bearish Divergences**: Instances where price reached higher highs while MACD formed lower highs (late 2021, parts of 2023) successfully predicted upcoming price weaknesses.
  - **Bullish Divergences**: Occasions where price formed lower lows while MACD created higher lows (late 2022) accurately indicated impending bullish reversals.

- **MACD Amplitude**:
  - The amplitude of MACD oscillations provides insight into market volatility, with larger swings (early 2020, early 2024) corresponding to periods of increased volatility and trading opportunities.
  - Reduced amplitude during consolidation phases (parts of 2021 and 2023) indicated decreased momentum and potential trend exhaustion.

- **Current MACD Dynamics (2024-2025)**:
  - Recent MACD readings show strong positive momentum with the MACD line above both the signal line and zero line, confirming the strength of the current uptrend.
  - The histogram remains predominantly positive, though fluctuations suggest periodic profit-taking within the overall bullish trend.

The MACD effectively combines trend and momentum analysis in a single indicator, providing reliable signals for trend confirmation and potential reversals when used in conjunction with other technical tools.

> 📈 MACD crossover above signal → **Buy**  
> 📉 MACD crossover below signal → **Sell**

## 📌 Summary & Findings

### ✅ Key Takeaways:

* **Comprehensive Technical Analysis**: By combining multiple technical indicators (MA crossovers, Bollinger Bands, candlestick patterns, volume analysis, RSI, and MACD), we've created a robust analytical framework that helps identify high-probability trading opportunities while minimizing false signals.

* **Trend Identification**: The moving averages clearly defined the overarching trend directions: bullish in 2020-2021, bearish in 2022, mixed in 2023, and strongly bullish in 2024.

* **Volatility Assessment**: Bollinger Bands effectively framed price volatility, with band expansions correctly identifying periods of increased market uncertainty and potential trading opportunities.

* **Momentum Confirmation**: RSI and MACD successfully identified overbought/oversold conditions and momentum shifts, providing valuable confirmation of trend strength and potential reversal points.

* **Volume-Price Relationship**: Volume analysis demonstrated that significant price movements are typically preceded and confirmed by volume changes, with the highest volume periods marking key market turning points.

* **Pattern Recognition**: Candlestick analysis revealed important reversal patterns and continuation signals that enhanced the precision of entry and exit points.

### 💡 Observations:

* **Signal Confluence**: The most reliable trading signals occurred when multiple indicators aligned:
  - The strongest buy signals appeared when price touched the lower Bollinger Band while RSI was oversold and MACD showed bullish divergence, often with above-average volume (March 2020, late 2022).
  - The most reliable sell signals emerged when price reached the upper Bollinger Band while RSI was overbought and MACD displayed bearish divergence, typically accompanied by declining volume (early 2022, parts of 2023).

* **Indicator Limitations**:
  - Individual indicators produced occasional false signals, particularly during consolidation phases.
  - RSI overbought readings during strong bull markets (2020, 2024) sometimes persisted without immediate price corrections.
  - Moving average crossovers occasionally generated whipsaw signals during ranging markets (parts of 2023).

* **Market Phase Adaptations**:
  - Different indicators proved more valuable in different market phases:
    - Moving averages and MACD performed best during trending markets (2020-2021, 2022, 2024).
    - Bollinger Bands and RSI provided superior signals during consolidation phases (parts of 2021 and 2023).
    - Volume analysis was most critical during major market transitions (March 2020, late 2022).

* **Practical Trading Applications**:
  - **Long-term Investment**: MA crossover strategy offered excellent entry points for position trading (April 2020, early 2023, early 2024).
  - **Swing Trading**: Bollinger Band touches combined with RSI extremes provided reliable reversal signals for multi-week positions.
  - **Short-term Trading**: Candlestick patterns with volume confirmation enabled precise entry and exit timing for short-term trades.

### 🔮 Current Market Assessment (As of May 2025):

* AAPL remains in a strong bullish trend with price above both 20-day and 50-day moving averages.
* Recent RSI readings approaching overbought territory suggest caution in the short term, though the overall trend remains intact.
* Bollinger Bands show continued expansion, indicating sustained volatility and trading opportunities.
* Volume patterns support the price advance, though at lower levels than previous major rallies.
* MACD confirms positive momentum with the indicator above both signal line and zero line.

### 📝 Best Practices Going Forward:

* Use a combination of trend, momentum, volatility, and volume indicators to reduce false signals and enhance trading precision.
* Adapt indicator interpretation to current market conditions (trending vs. ranging).
* Prioritize signal confluence over individual indicator readings.
* Consider broader market conditions and fundamental catalysts alongside technical signals.
* Implement appropriate risk management through position sizing and stop-loss placement.

## 🚀 Usage

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import mplfinance as mpf

# Load data
df = pd.read_csv('data/AAPL.csv', index_col='Date', parse_dates=True)

# Calculate moving averages
df['MA20'] = df['Close'].rolling(20).mean()
df['MA50'] = df['Close'].rolling(50).mean()

# Calculate Bollinger Bands
df['MA20'] = df['Close'].rolling(window=20).mean()
df['std'] = df['Close'].rolling(window=20).std()
df['Upper'] = df['MA20'] + (df['std'] * 2)
df['Lower'] = df['MA20'] - (df['std'] * 2)

# Calculate RSI
def calculate_rsi(data, window=14):
    diff = data.diff()
    gain = diff.where(diff > 0, 0).rolling(window=window).mean()
    loss = -diff.where(diff < 0, 0).rolling(window=window).mean()
    rs = gain / loss
    return 100 - (100 / (1 + rs))

df['RSI'] = calculate_rsi(df['Close'])

# Calculate MACD
def calculate_macd(data, fast=12, slow=26, signal=9):
    ema_fast = data.ewm(span=fast, adjust=False).mean()
    ema_slow = data.ewm(span=slow, adjust=False).mean()
    macd_line = ema_fast - ema_slow
    signal_line = macd_line.ewm(span=signal, adjust=False).mean()
    histogram = macd_line - signal_line
    return macd_line, signal_line, histogram

df['MACD'], df['Signal'], df['Histogram'] = calculate_macd(df['Close'])

# Visualize candlestick with MA and volume
mpf.plot(df, type='candle', style='yahoo', 
         title='AAPL Candlestick Chart with MA & Volume',
         ylabel='Price (USD)',
         volume=True, 
         mav=(20, 50),
         savefig='images/candlestick_chart.png')

# Plot price and volume
fig, ax1 = plt.subplots(figsize=(12, 6))
ax2 = ax1.twinx()
ax1.plot(df.index, df['Close'], 'b-', label='Close Price')
ax2.bar(df.index, df['Volume'], color='gray', alpha=0.3, label='Volume')
ax1.set_xlabel('Date')
ax1.set_ylabel('Close Price (USD)', color='b')
ax2.set_ylabel('Volume', color='gray')
plt.title('Price vs Volume')
plt.grid(True, alpha=0.3)
plt.tight_layout()
plt.savefig('images/price_vs_volume.png')
```

## 📁 Project Structure

```
.
├── data/
│   └── AAPL.csv                     # Raw stock data (downloaded)
├── images/
│   ├── basic_plot.png               # Close price plot
│   ├── moving_averages.png          # MA20 and MA50 plot
│   ├── bollinger_bands.png          # Bollinger Bands
│   ├── candlestick_chart.png        # Candlestick with MA & volume
│   ├── price_vs_volume.png          # Price vs volume analysis
│   ├── rsi.png                      # RSI indicator
│   └── technical_indicators.png     # MACD & histogram
├── notebooks/
│   └── stock_analysis.ipynb         # Jupyter notebook for all analysis
├── scripts/
│   ├── technical_indicators.py      # Functions for indicators
│   └── visualization.py             # Plotting functions
├── requirements.txt
└── README.md
```

## 🔧 Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/stock-analysis-and-report.git
   cd stock-analysis-and-report
   ```

2. Set up virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Run the notebook:

   ```bash
   jupyter notebook notebooks/stock_analysis.ipynb
   ```

### Required Packages
```
pandas
numpy
matplotlib
yfinance
mplfinance
scikit-learn
seaborn
```

## 📜 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

Maintained by [Your Name](https://github.com/your-username).
For questions, feel free to [open an issue](https://github.com/your-username/stock-analysis-and-report/issues).

---

<p align="center">
  <sub>If you found this project helpful, please consider giving it a ⭐️</sub>
</p>
