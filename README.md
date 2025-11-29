# ⚔️ KatanaFlow: Quantitative Trend Analysis System

![Pine Script](https://img.shields.io/badge/Language-Pine%20Script%20v6-blue)
![Platform](https://img.shields.io/badge/Platform-TradingView-black)
![Type](https://img.shields.io/badge/Category-Algorithmic%20Trading-success)

<img width="2030" height="1180" alt="image" src="https://github.com/user-attachments/assets/7279da93-3479-4793-8cfb-b3f8d78cab0c" />
<img width="2037" height="1176" alt="image" src="https://github.com/user-attachments/assets/3053b322-18f4-4ab2-a560-ab9cd37bb1bd" />

> *Figure 1: KatanaFlow executing a trend reversal signal in Expert Mode.*

## 📖 Executive Summary
**KatanaFlow** is a proprietary technical analysis algorithm developed for **TradingView**, designed to address the common latency and false signal issues inherent in standard trend-following indicators.

Unlike traditional Moving Average crossovers, KatanaFlow implements a **Twin Range Filter (TRF)** architecture. This approach mathematically smooths market volatility to isolate the underlying trend, providing high-probability entry and exit points for both intraday scalping and swing trading strategies.

## 🚀 Technical Features

### 1. Advanced Noise Filtration (TRF)
The core engine utilizes a double-smoothed volatility filter. By calculating the deviation of price from its mean using varied periods, the algorithm effectively distinguishes between market "noise" (insignificant fluctuations) and genuine trend reversals.

### 2. Signal Integrity (Non-Repainting)
Designed with strict algorithmic reliability in mind:
* **Confirmation:** All signals (`KATA Long` / `KATA Short`) are confirmed strictly at the **bar close**.
* **Permanence:** Once a signal is printed on the chart, it is permanent. It does not repaint, shift, or vanish, ensuring validity for backtesting and historical analysis.

### 3. Modular Interface
The system offers two distinct visualization modes to suit different analytical needs:
* **Basic Mode:** A minimalist interface displaying only entry/exit signals, ideal for decluttered price action analysis.
* **Expert Mode:** Activates the full analytical suite, including TRF Bands (Dynamic Support/Resistance), Trendlines, and auxiliary Moving Averages for confluence verification.

### 4. Algorithmic Automation
The script is optimized for automated trading environments, featuring built-in `alertcondition()` functions compatible with third-party webhook services (e.g., 3Commas, Cryptohopper, or custom Python bots).

---

## 📺 System Demonstration

View the algorithm's performance in live market conditions:

[![KatanaFlow Analysis](https://img.youtube.com/vi/z4b2ntVZgUw/0.jpg)](https://www.youtube.com/watch?v=z4b2ntVZgUw)

> *Note: The video walkthrough provides a comprehensive overview of the signal logic.*

---

## ⚙️ Methodology & Logic

KatanaFlow determines trend directionality by comparing the current asset price against a dynamic volatility range. The mathematical smoothing logic is derived as follows:
```pine
// Volatility Smoothing Calculation
weighted_period = period * 2 - 1
average_range = ema(abs(x - x[1]), period)
smoothed_range = ema(average_range, weighted_period) * multiplier

The algorithm synthesizes two distinct timeframes (Fast & Slow) to establish a "Fair Value" equilibrium line.

Bullish Regime: Price sustains above the filter threshold.

Bearish Regime: Price sustains below the filter threshold.

🛠️ Deployment Instructions
Navigate to the KatanaFlow.pine file within this repository.

Copy the source code.

Launch TradingView and open the Pine Editor.

Paste the source code and select "Add to Chart".

🎛️ Configuration Parameters
Parameter	Default	Function
User Mode	Temel	Toggles between Basic (Signal only) and Expert (Full Suite) visualization.
Fast Period	12	Adjusts sensitivity for short-term volatility. Lower values increase signal frequency.
Slow Period	4	Adjusts sensitivity for the longer-term trend baseline.
Multiplier	1.0 / 2.0	Standard deviation multiplier for band expansion. Higher values reduce false positives.

E-Tablolar'a aktar

⚖️ Disclaimer
This software is for educational and analytical purposes only. Financial trading involves significant risk. Past performance of any trading system is not indicative of future results. Users should employ proper risk management strategies.

Developed by Hasan Mert Yavuz Computer Engineering Student & Algorithm Developer
