# TradingView Indicators

*Basic set of indicators for TradingView based on PineScript v6*

| | |
|---------|------|
| Release | 2020-08-05 |
| Update | 2025-12-29 |
| Author | sajjetti |
| Email | contact@sajjetti.ai |

## Index

- [Chande Momentum Oscillator (CMO)](#chande-momentum-oscillator-cmo)
- [Double Smoothed Stochastic (DSS)](#double-smoothed-stochastic-dss)
- [Double Smoothed Stochastic MTF (DSS MTF)](#double-smoothed-stochastic-mtf-dss-mtf)
- [Exponential Moving Average (EMA)](#exponential-moving-average-ema)
- [High Minus Low (HML)](#high-minus-low-hml)
- [Moving Average (MA)](#moving-average-ma)
- [Moving Average Convergence Divergence (MACD)](#moving-average-convergence-divergence-macd)
- [Momentum (MOM)](#momentum-mom)
- [Rolling Moving Average (RMA)](#rolling-moving-average-rma)
- [Relative Strength Index (RSI)](#relative-strength-index-rsi)
- [Stochastic (STO)](#stochastic-sto)
- [Stochastic Williams %R](#stochastic-williams-r)
- [SuperTrend (STR)](#supertrend-str)
- [Triangular Moving Average (TMA)](#triangular-moving-average-tma)
- [Williams %R (W%R)](#williams-r-wr)

---

## Chande Momentum Oscillator (CMO)

**File:** `4 - CMO (v6).pine`

The Chande Momentum Oscillator was developed by Tushar Chande in 1994 and introduced in his book "The New Technical Trader". Unlike RSI which uses ratios, CMO measures momentum by calculating the difference between the sum of gains and losses, then dividing by their total sum. This creates an oscillator that moves between -100 and +100, with zero as the centerline.

CMO is particularly useful for identifying overbought and oversold conditions, as well as divergences between price and momentum. Values above +50 indicate overbought conditions, while values below -50 suggest oversold conditions.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 9 | Lookback period for momentum calculation |
| Smooth | 1 | Smoothing period applied to final value |

---

## Double Smoothed Stochastic (DSS)

**File:** `4 - DSS (v6).pine`

The Double Smoothed Stochastic was developed by William Blau and introduced in his 1993 book "Momentum, Direction, and Divergence". It applies exponential smoothing twice to the standard stochastic calculation, resulting in a smoother oscillator that filters out market noise while maintaining responsiveness to significant price movements.

DSS oscillates between 0 and 100, with readings above 80 considered overbought and below 20 considered oversold. The double smoothing makes it particularly effective for identifying trend direction and potential reversal points.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Fast Length | 3 | Period for fast EMA smoothing |
| Slow Length | 9 | Period for slow EMA smoothing |
| Smooth | 1 | Additional smoothing period |

---

## Double Smoothed Stochastic MTF (DSS MTF)

**File:** `4 - DSS MTF (v6).pine`

The Multi-Timeframe version of the Double Smoothed Stochastic allows traders to view DSS values from higher timeframes on their current chart. This is essential for multi-timeframe analysis, enabling traders to align entries on lower timeframes with the trend direction on higher timeframes.

For example, viewing the 60-minute DSS on a 15-minute chart helps filter out counter-trend trades and improves overall signal quality by ensuring alignment with the broader market direction.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Timeframe | 60 | Higher timeframe to pull DSS data from |
| Source | close | Price data to analyze |
| Fast Length | 3 | Period for fast EMA smoothing |
| Slow Length | 9 | Period for slow EMA smoothing |
| Smooth | 1 | Additional smoothing period |

---

## Exponential Moving Average (EMA)

**File:** `4 - EMA (v6).pine`

The Exponential Moving Average gives more weight to recent prices, making it more responsive to new information compared to the Simple Moving Average. Developed in the 1960s for use in technical analysis, the EMA has become one of the most widely used indicators for trend identification and support/resistance levels.

The weighting multiplier for the most recent price is calculated as 2/(period+1), causing the EMA to react faster to price changes than an SMA of the same length. Traders commonly use EMAs of 9, 21, 50, and 200 periods for different trading timeframes.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 9 | Number of periods for EMA calculation |
| Smooth | 1 | Additional smoothing period |

---

## High Minus Low (HML)

**File:** `4 - HML (v6).pine`

High Minus Low is a simple volatility indicator that calculates the average range of price movement by measuring the difference between the high and low of each bar over a specified period. This provides traders with a clear view of market volatility and potential price expansion or contraction.

HML is useful for setting stop-loss levels, identifying breakout potential, and adjusting position sizes based on current market volatility. Higher values indicate increased volatility, while lower values suggest consolidation.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Length | 9 | Lookback period for averaging |

---

## Moving Average (MA)

**File:** `4 - MA (v6).pine`

The Simple Moving Average is the most fundamental technical indicator, calculating the arithmetic mean of prices over a specified period. First used in the early 20th century, the SMA remains essential for identifying trends, support/resistance levels, and generating trading signals through crossovers.

The SMA treats all prices equally within the lookback period, creating a smooth line that filters out short-term fluctuations. Common periods include 20 (monthly), 50 (quarterly), and 200 (yearly) for different analytical perspectives.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 9 | Number of periods for averaging |
| Smooth | 1 | Additional smoothing period |

---

## Moving Average Convergence Divergence (MACD)

**File:** `4 - MACD (v6).pine`

The MACD was developed by Gerald Appel in the late 1970s and has become one of the most popular momentum indicators. It calculates the difference between two exponential moving averages (typically 12 and 26 periods) and plots this against a signal line (typically 9-period EMA of the MACD line).

MACD generates signals through crossovers between the MACD line and signal line, zero-line crossovers, and divergences with price. The histogram visualization shows the difference between the MACD and signal lines, making momentum shifts easy to identify.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Fast Length | 12 | Period for fast EMA |
| Slow Length | 26 | Period for slow EMA |
| Signal Length | 9 | Period for signal line EMA |
| Fast Smooth | 1 | Smoothing for fast EMA |
| Slow Smooth | 1 | Smoothing for slow EMA |

---

## Momentum (MOM)

**File:** `4 - MOM (v6).pine`

Momentum is one of the oldest and simplest technical indicators, measuring the rate of change in price over a specified period. It calculates the difference between the current price and the price N periods ago, providing a direct measure of price velocity.

Positive momentum indicates upward price movement, while negative momentum shows downward movement. The indicator oscillates around zero, with crossovers of the zero line often used as trend change signals. Divergences between momentum and price can signal potential reversals.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 10 | Lookback period for momentum |
| Smooth | 1 | Smoothing period applied to result |

---

## Rolling Moving Average (RMA)

**File:** `4 - RMA (v6).pine`

The Rolling Moving Average, also known as Wilder's Smoothing or Modified Moving Average, was developed by J. Welles Wilder Jr. and introduced in his 1978 book "New Concepts in Technical Trading Systems". It uses a smoothing factor of 1/length rather than 2/(length+1) used by EMA, resulting in a smoother output.

RMA is the foundation for several Wilder indicators including RSI and ATR. Its smoother nature makes it less reactive to price spikes but more reliable for identifying sustained trends. The RMA places approximately 86% weight on historical values versus 14% on new data for a 14-period calculation.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 9 | Number of periods for RMA calculation |
| Smooth | 1 | Additional smoothing period |

---

## Relative Strength Index (RSI)

**File:** `4 - RSI (v6).pine`

The Relative Strength Index was developed by J. Welles Wilder Jr. and introduced in his 1978 book "New Concepts in Technical Trading Systems". RSI measures the speed and magnitude of recent price changes to evaluate overbought or oversold conditions, oscillating between 0 and 100.

Traditional interpretation considers RSI above 70 as overbought and below 30 as oversold. However, RSI is also valuable for identifying divergences, failure swings, and trend confirmation. The indicator uses RMA (Wilder's smoothing) in its calculation for consistency with Wilder's original formula.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 14 | Lookback period for RSI calculation |
| Smooth | 1 | Smoothing period applied to RSI |

---

## Stochastic (STO)

**File:** `4 - STO (v6).pine`

The Stochastic Oscillator was developed by George Lane in the 1950s. It compares a security's closing price to its price range over a specified period, based on the premise that prices tend to close near the high during uptrends and near the low during downtrends.

The indicator consists of two lines: %K (fast) and %D (slow, which is a moving average of %K). Readings above 80 indicate overbought conditions, while readings below 20 suggest oversold conditions. Crossovers between %K and %D generate trading signals.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| K Length | 14 | Lookback period for %K calculation |
| K Smooth | 3 | Smoothing period for %K |
| D Period | 3 | Period for %D signal line |

---

## Stochastic Williams %R

**File:** `4 - Stochastic W%R (v6).pine`

Stochastic Williams %R combines elements of both the Stochastic Oscillator and Williams %R indicators. It applies stochastic smoothing to the Williams %R calculation, creating a hybrid oscillator that benefits from the characteristics of both indicators.

This combination provides smoother signals than standard Williams %R while maintaining its sensitivity to price extremes. The %K and %D lines allow for crossover signals similar to the standard Stochastic, but with the Williams %R foundation.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| K Length | 10 | Lookback period for Williams %R |
| K Smooth | 5 | Smoothing period for %K |
| D Period | 5 | Period for %D signal line |

---

## SuperTrend (STR)

**File:** `4 - STR (v6).pine`

SuperTrend is a trend-following indicator developed by Olivier Seban. It uses Average True Range (ATR) to calculate dynamic support and resistance levels that adapt to market volatility. The indicator plots a line that switches between acting as support (below price) and resistance (above price).

When price closes above the SuperTrend line, it turns bullish (typically green), indicating an uptrend. When price closes below, it turns bearish (typically red), signaling a downtrend. The ATR multiplier controls the distance of the bands from price, with higher values creating wider bands suitable for volatile markets.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data for trend calculation |
| Positive Multiplier | 3 | ATR multiplier for upper band |
| Negative Multiplier | 3 | ATR multiplier for lower band |
| Length | 10 | ATR calculation period |

---

## Triangular Moving Average (TMA)

**File:** `4 - TMA (v6).pine`

The Triangular Moving Average applies double smoothing by calculating a simple moving average of a simple moving average. This creates an extremely smooth line that places the most weight on the middle portion of the data series, forming a triangular weighting pattern.

TMA is slower to react than SMA or EMA but provides cleaner trend identification with fewer false signals. It's particularly useful on noisy charts or for longer-term trend analysis where responsiveness is less important than smoothness.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 9 | Period for TMA calculation |
| Smooth | 1 | Additional smoothing period |

---

## Williams %R (W%R)

**File:** `4 - W%R (v6).pine`

Williams %R was developed by Larry Williams in 1973. It measures the level of the close relative to the highest high over a lookback period, expressed as a negative percentage from 0 to -100. The indicator is essentially an inverted Stochastic Oscillator.

Readings from 0 to -20 indicate overbought conditions, while readings from -80 to -100 indicate oversold conditions. Williams %R is particularly effective at identifying potential reversals when price reaches extreme levels and begins to turn.

**Settings:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| Source | close | Price data to analyze |
| Length | 14 | Lookback period for high/low range |
| Smooth | 1 | Smoothing period applied to result |

---

## Changelog

### 2.0.0 - 2025-12-29
* Updated all indicators from PineScript v4 to v6
* Added version format `[Vx.x|ps6]` to indicator titles
* Added input groups with industry standard parameters
* Added color constants section to all indicators
* Standardized function naming and documentation
* **New:** Chande Momentum Oscillator (CMO)
* **New:** Double Smoothed Stochastic MTF (DSS MTF)
* **New:** Stochastic Williams %R

### 1.0.0 - 2020-08-05
* Initial release with 12 indicators
* PineScript v4

## Version

- Original release: PineScript v4 (August 2020)
- Current version: **PineScript v6** (December 2025)
- Version format: `[Vx.x|ps6]`

## Links

- [TradingView Profile](https://www.tradingview.com/u/stmd/#published-scripts)
- [Sajjetti AI](https://sajjetti.ai)
