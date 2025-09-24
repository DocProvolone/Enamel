# 🦷 Enamel – MetaTrader 5 Expert Advisor

[![Made with MQL5](https://img.shields.io/badge/Made%20with-MQL5-blue.svg)](https://www.mql5.com/en/docs)   
[![GitHub stars](https://img.shields.io/github/stars/DocProvolone/Enamel.svg?style=social)](https://github.com/DocProvolone/Enamel/stargazers)

---

## 🔍 Introduction
**Enamel** is a free, open-source Expert Advisor for **MetaTrader 5 (MT5)**.  
It is designed to **trade selected USD pairs, using a "Trend Pullback" strategy, giving users full customization over its parameters both in trading logic and risk management**.

✅ Free to use  
✅ Open-source and fully customizable  
✅ Live-tested  
✅ Robust & full of security features  
✅ Plug & play with MT5  

---

## 📦 Installation

You can either compile your own version of the Enamel Expert Advisor, giving you the choice to select how to compile it and modify everything in its logic (using the ` .mq5 ` file in the repository),
or install the pre-compiled `.ex5` Expert Advisors using the instructions below.

### 📦 Installing using the precompiled EA


1. Clone this repository or download the `.zip`:  
   ```bash
   git clone https://github.com/DocProvolone/Enamel
2. Select a version compatible with your CPU:  
      The EA is compiled for both AVX2 capable processors (a more optimized, faster and more energy hungry version)  
      and non-comptabile X64 processors.  
      You can check your producer supported instructions set using free tools such as CPU-Z from CPUID (link to official website: https://www.cpuid.com/softwares/cpu-z.html )  
      If in doubt, or don't want to check your producer compatibility, use the X64 version.  
3. Copy the selected EA file (either AVX2 or X64) into your MT5 Experts folder:  
   ` MQL5/Exeprts/ `  
4. Restart MetaTrader 5 (or right-click Navigator → Refresh).  
5. The EA will appear under Navigator → Expert Advisors.  
✅ You now have succesfully installed the Expert Advisor! You can check below how to use and optimize it.

### 💻 Compiling your own EA  
1. Clone this repository or download the `.zip`:  
   ```bash
   git clone https://github.com/DocProvolone/Enamel  
2. Open MetaEditor 5 and locate your ` .mq5 ` file using the navigator menu.  
3. Feel free to customize and apply any sorts of modifications you'd like!  
4. In the upper menu, select "compile".  
5. You will be asked if you' d like or not to "Optimize" before compiling, you can find out more about MQL5 on-IDE optimization here: https://www.metatrader5.com/en/metaeditor/help/mql5storage/projects#properties  
6. You should now choose which instruction set to use for compiling.  
   MQL5 offers 3 different Intel Advanced Vector Extensions (AVX) instruction sets or a X64 regular one. You can find out more on Intel's official website  
   If wondering about your producer instructions sets compatibility, you can use free tools such as CPU-Z (link: https://www.cpuid.com/softwares/cpu-z.html )  
7. After compiling successfully, you can now use and optimize the EA!  

---

## 📩 Using the EA  

⚠️ **Caution:** It is highly recommended to first tune and optimize parameters BEFORE using the EA. It is also *highgly* recommended to first test the EA in a DEMO scenario for several time before switching to live-trading.  
    Expert Advisors are a magnificent and powerfull tool, use them with responsibility.  
    ---  
    ## 🔢 Input parameters  
    Enamel is full of input parameters that you can either optimize using MetaTtrader's built-in strategy tester, or finding the best values for your trading manually.  
    Below is a detailed table of the input parameters found in the latest version of the Enamel EA.  

    
      | Group | Input | Description |
      |---|---|---|
      | 🔐LiveLock | AllowLiveTrading | Enable or disable live trading (safety toggle). |
      | 🚧Indicators Settings | TimeFrame | Timeframe used for most indicators and trading logic. |
      | 🚧Indicators Settings | FastEMAPeriod | Period for the fast EMA in trend detection. |
      | 🚧Indicators Settings | SlowEMAPeriod | Period for the slow EMA in trend detection. |
      | 🚧Indicators Settings | RSIPeriod | Period for RSI calculation. |
      | 🚧Indicators Settings | RSIOverbought | Upper RSI threshold to detect overbought conditions. |
      | 🚧Indicators Settings | RSIOversold | Lower RSI threshold to detect oversold conditions. |
      | 🚧Indicators Settings | MACDFastEMA | Fast EMA for MACD. |
      | 🚧Indicators Settings | MACDSlowEMA | Slow EMA for MACD. |
      | 🚧Indicators Settings | MACDSignalEMA | Signal line period (SMA) for MACD. |
      | 🚧Indicators Settings | ATRPeriod | ATR period used for SL, TP, and filters. |
      | 🚧Indicators Settings | ATRMultiplier | Multiplier applied to ATR to define stop loss distance. |
      | 🚧Indicators Settings | ADXPeriod | Period for ADX used to detect trending vs ranging market. |
      | 🚧Indicators Settings | ADXThreshold | Minimum ADX value to consider market as trending. |
      | 🚧Indicators Settings | BBPeriod | Period for Bollinger Bands used in regime detection. |
      | 🚧Indicators Settings | BB_Width_ Threshold | Minimum normalized width between BBands to consider market volatile/trending. |
      | 🚧Indicators Settings | UseCandle Confirmation | Whether to require large candle body (vs ATR) as confirmation before entry. |
      | 🚧Indicators Settings | MinCandleBody ATRRatio | Minimum candle body size as ratio of ATR to confirm signal. |
      | 🚧Indicators Settings | UseHTFTrendFilter | Enable higher timeframe trend filter (EMA-based). |
      | 🚧Indicators Settings | HTFTrendTimeframe | Higher timeframe used for trend filter. |
      | 🚧Indicators Settings | HTFTrendEMA Period | EMA period for HTF trend filter. |
      | 🕗Trading Hours Settings | UseTradeHours | Enable time-based trading restrictions. |
      | 🕗Trading Hours Settings | TradeHourStart | Start hour for trade window (0–23). |
      | 🕗Trading Hours Settings | TradeHourEnd | End hour for trade window (0–23). |
      | 🕗Trading Hours Settings | UseTradeTimeout | Enable trade timeout feature. |
      | 🕗Trading Hours Settings | TimeoutBars | Number of bars after which a trade is closed if still open. |
      | 🕗Trading Hours Settings | UseFridayFilter | Avoid opening trades late on Fridays. |
      | 🕗Trading Hours Settings | FridayCutoffHour | Hour after which no new trades will be opened on Fridays. |
      | 💱Risk Management | UseReverseSignal Exit | Close trade early if a reverse signal occurs. |
      | 💱Risk Management | LotSize | Fixed lot size when dynamic lot sizing is disabled. |
      | 💱Risk Management | UseDynamicLot Sizing | Enable dynamic lot sizing based on risk %. |
      | 💱Risk Management | RiskPercent | Risk per trade as % of account balance. |
      | 💱Risk Management | MaxAllowedLot | Maximum allowed lot size to prevent over-sizing. |
      | 💱Risk Management | UsePartialExit | Enable partial position closure when certain profit threshold is reached. |
      | 💱Risk Management | PartialExitPercent | Percentage of position to close during partial exit. |
      | 💱Risk Management | PartialTriggerATR | How many ATRs of profit to trigger partial exit. |
      | 💱Risk Management | UseAdaptiveTP | Use TP that adjusts based on SL and market volatility. |
      | 💱Risk Management | TPRatio | Ratio of TP to SL (used when adaptive TP is enabled). |
      | 💱Risk Management | UseTrailingStop | Enable stepped trailing stop logic. |
      | 💱Risk Management | TrailingStepPips | Minimum distance in pips to move trailing stop after price moves. |
      | 💱Risk Management | MaxDrawdownPercent | Prevent new trades if drawdown exceeds this % of account balance. |
      | 💱Risk Management | MaxSpreadPips | Maximum spread in pips allowed for trade entry. |
      | 💱Risk Management | UseBreakEven | Enable breakeven logic after trade moves in favor. |
      | 💱Risk Management | BreakEvenTriggerATR | Profit threshold (in ATR) to trigger breakeven move. |
      | 💱Risk Management | BreakEvenBufferPips | Buffer in pips added to breakeven stop placement. |
      | ❔Misc. | EnableDebugLogs | Print extra logs for debugging (may affect performance). |
      | 🔮MAGIC | MagicNumber | Unique magic number for tracking EA trades. |
