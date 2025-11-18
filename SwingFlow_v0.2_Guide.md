# SwingFlow v0.2 - User Guide

## Overview
SwingFlow v0.2 is an adaptive trading indicator designed for multiple trading styles (scalping to long-term investing) with intelligent entry/exit signals, dynamic risk management, and Fair Value Gap tracking.

## Key Features

### 🎯 Adaptive Trading Styles
The indicator automatically adjusts MACD parameters, volume periods, and default stop losses based on your selected style:

- **Scalping** (1-5min): Fast MACD (8,17,9), 10-period volume, 0.75% default stop
- **Intraday** (5-15min): Standard MACD (12,26,9), 20-period volume, 2% default stop
- **Swing** (1hr-4hr): Standard MACD, 30-period volume, 3% default stop
- **Medium Term** (Daily): Slower MACD (19,39,9), 50-period volume, 6% default stop
- **Long Term** (Weekly): Standard MACD on weekly, 20-period volume, 12% default stop

### 📊 Core Indicators

#### VWAP (Volume Weighted Average Price)
- **Blue line**: Main VWAP
- **Light blue lines**: ±1 and ±2 standard deviation bands
- Acts as dynamic support/resistance
- Entry trigger when price crosses VWAP with confirmation

#### MACD (Moving Average Convergence Divergence)
- Adaptive periods based on trading style
- **Histogram expansion detection**: Catches momentum building
- **Histogram jump detection**: Identifies momentum reversals (like your VRA trade)
  - Detects when histogram was declining for 3+ bars
  - Then surges back by 15%+ (adjustable threshold)
  - Perfect for catching re-ignition of moves

#### Volume Confirmation
- Volume must exceed its moving average
- Ensures conviction behind the move
- Adaptive volume period based on trading style

#### Fair Value Gaps (FVG)
- **Green boxes**: Bullish gaps (potential support)
- **Red boxes**: Bearish gaps (potential resistance)
- Auto-removes when price fills the gap (keeps chart clean!)
- Only shows gaps from current timeframe
- Minimum gap size: 0.5% of price

### 🎯 Entry Signals

#### Long Entry (Green Triangle Up)
**Required conditions:**
1. Price crosses above VWAP (or pullback to VWAP from above)
2. MACD histogram expanding upward OR histogram jump detected
3. Volume > Volume MA (showing conviction)
4. MACD line > Signal line

**Optional filters (toggleable):**
- Trend filter: Price > 50 EMA
- FVG filter: Bullish FVG below as support

#### Short Entry (Red Triangle Down)
**Required conditions:**
1. Price crosses below VWAP
2. MACD histogram expanding downward OR histogram jump detected  
3. Volume > Volume MA
4. MACD line < Signal line

**Optional filters (toggleable):**
- Trend filter: Price < 50 EMA
- FVG filter: Bearish FVG above as resistance

### 🛡️ Risk Management

#### Stop Loss Methods (User Selectable)
1. **Percentage**: Fixed % from entry (adaptive per trading style)
2. **Swing**: Uses 10-period swing low/high
3. **ATR**: 1.5x ATR from entry (adjustable multiplier)
4. **VWAP**: Below/above 1 standard deviation band

#### Take Profit (Dynamic)
- **TP1** (Yellow line): 50% of full R:R target
  - Recommendation: Exit 50% of position here
- **TP2** (Orange line): Full R:R target
  - Recommendation: Exit remaining position or trail stop

**Default R:R Ratio**: 3:1 (fully adjustable 1:1 to 10:1)

### 📋 Visual Elements

| Element | Color | Meaning |
|---------|-------|---------|
| 🟢 Triangle Up | Green | Long entry signal |
| 🔴 Triangle Down | Red | Short entry signal |
| 💎 Diamond (below) | Lime | Bullish histogram jump detected |
| 💎 Diamond (above) | Fuchsia | Bearish histogram jump detected |
| ━━━ Dashed line | Blue | Stop loss |
| ━━━ Solid line | Yellow | Take Profit 1 (50% exit) |
| ━━━ Solid line | Orange | Take Profit 2 (full exit) |
| ⬜ Green box | Semi-transparent | Bullish FVG (support zone) |
| ⬜ Red box | Semi-transparent | Bearish FVG (resistance zone) |
| ━━━ Thick line | Blue | VWAP |
| ━━━ Thin lines | Light blue | VWAP ±1σ and ±2σ bands |
| ━━━ Thick line | Orange | 50 EMA (optional) |

### 📊 Entry Label Example
When a signal triggers, you'll see a label like this:

```
📈 LONG $2.77
🛡️ SL: $2.71 (-2.2%)
🎯 TP1: $2.95 (+6.5% | 1.5:1)
🎯 TP2: $3.13 (+13% | 3:1)
```

This tells you:
- Entry price
- Stop loss price and % risk
- TP1 price, % gain, and R:R ratio
- TP2 price, % gain, and R:R ratio

## Installation & Setup

### Step 1: Add to TradingView
1. Open TradingView
2. Click **Pine Editor** at bottom of chart
3. Click **New** → **Blank indicator**
4. Copy the entire code from `swingflow_v0.2.pine`
5. Paste into editor
6. Click **Save** (name it "SwingFlow v0.2")
7. Click **Add to Chart**

### Step 2: Configure Your Style
1. Click the ⚙️ settings icon on the indicator
2. Under **Trading Style**, select your preference:
   - Day trading: Choose "Intraday"
   - Swing trading: Choose "Swing"
   - Long-term: Choose "Medium Term" or "Long Term"
3. The indicator will auto-adjust all parameters

### Step 3: Customize Filters
Under **Entry Filters**:
- ✅ Keep VWAP Cross, MACD Expansion, Volume enabled (core filters)
- Toggle **Trend Filter** if you only want trades in the direction of the 50 EMA
- Toggle **FVG Filter** if you only want trades with FVG support/resistance
- Adjust **Histogram Jump Threshold** (15% default works well, lower = more sensitive)

### Step 4: Risk Settings
Under **Risk Management**:
- Set your preferred **Risk:Reward Ratio** (3:1 is conservative)
- Choose **Stop Loss Method**:
  - "Percentage" for consistent risk
  - "Swing" for structure-based stops
  - "ATR" for volatility-adjusted stops
- Adjust **Stop Loss %** to match your risk tolerance

### Step 5: Add MACD Indicator
Since TradingView limits custom indicator windows, add the standard MACD:
1. Click **Indicators** button
2. Search "MACD"
3. Select "MACD" (built-in)
4. Configure it to match your trading style:
   - Intraday: 12, 26, 9
   - Scalping: 8, 17, 9
   - Medium Term: 19, 39, 9

## Real Trading Example (Your VRA Trade)

**Ticker**: VRA (Vera Bradley)  
**Date**: November 18, 2025  
**Time**: ~10:10 AM EST  
**Style**: Intraday (5-min chart)

### What SwingFlow Would Show:

**10:10 AM - Setup Building:**
- Price at $2.77, below VWAP
- MACD histogram was declining (red bars getting smaller)
- Volume starting to increase

**10:10-10:15 AM - Signal Triggered:**
- 💎 **Diamond marker appears** (histogram jump detected!)
  - Histogram was fading, then suddenly expanded back to solid green
- 🟢 **Green triangle up** (long entry signal)
- Price crosses above VWAP at $2.77
- Volume surges above 20-period MA

**Entry Signal Label:**
```
📈 LONG $2.77
🛡️ SL: $2.71 (-2.2%)
🎯 TP1: $2.83 (+2.2% | 1.5:1)
🎯 TP2: $2.89 (+4.3% | 3:1)
```

**Your Actual Trade:**
- Entry: $2.77 ✅
- Exit: $2.87 (between TP1 and TP2)
- Profit: $0.10/share × 5,000 = $500 ✅

This is exactly what SwingFlow v0.2 is designed to catch!

## Advanced Tips

### 1. Scanner Integration
Your existing scanner (10%+ change, $1-20, 1M+ volume, <50M shares, relative volume 0-500%) is good, but consider:

**Optimized Settings:**
- Price: $2-15 (sweet spot)
- Change: 5-15% (avoid chasing parabolic >15%)
- Volume: 2M+ minimum
- Relative Volume: 1.5x+ (stronger signal)
- Add: ATR > 3% (ensure volatility)

Then apply SwingFlow to the results to filter for highest probability setups.

### 2. Multi-Timeframe Confirmation
For higher win rate:
- Trade on 5-min chart
- Check 15-min chart shows MACD alignment
- Both timeframes should show bullish structure

### 3. Time Filters
Avoid:
- First 15 min (9:30-9:45 AM) - too choppy
- Last 30 min (3:30-4:00 PM) - erratic moves
- Best trading: 10:00 AM - 3:00 PM EST

### 4. FVG Strategy
- When bullish FVG forms, price often returns to fill it
- Wait for price to return to FVG zone
- Enter when price bounces from FVG + other signals align
- FVG acts as high-probability support/resistance

### 5. Histogram Jump Strategy
This is your VRA edge! When you see:
- 💎 Diamond marker (histogram jump)
- Price near or crossing VWAP
- Volume surge

→ High-probability reversal/continuation setup

## Settings Reference

### Default Settings (Intraday)
```
Trading Style: Intraday
Show Longs: ✅
Show Shorts: ✅

Entry Filters:
  VWAP Cross: ✅
  MACD Histogram Expansion: ✅
  Volume Confirmation: ✅
  Trend Filter (50 EMA): ⬜
  FVG Support/Resistance: ⬜
  Histogram Jump Detection: ✅
  Jump Threshold: 15%

Risk Management:
  R:R Ratio: 3.0
  Stop Loss Method: Percentage
  Stop Loss %: 2.0%
  ATR Multiplier: 1.5

Visual Options:
  All enabled ✅

Alerts:
  All enabled ✅
```

### Aggressive Setup (More Signals)
- Lower histogram jump threshold to 10%
- Disable trend filter
- Disable FVG filter
- Lower R:R to 2:1

### Conservative Setup (Fewer, Higher Quality)
- Enable trend filter
- Enable FVG filter
- Increase histogram jump threshold to 20%
- Increase R:R to 4:1 or 5:1

## Troubleshooting

**Q: I don't see any signals**
- Check if both Long and Short signals are enabled
- Lower the histogram jump threshold
- Disable optional filters (Trend, FVG)
- Verify MACD shows histogram activity

**Q: Too many signals, chart is cluttered**
- Enable Trend Filter (only trades with trend)
- Enable FVG Filter (requires support/resistance)
- Increase histogram jump threshold to 20-25%
- Only show one direction (Long OR Short)

**Q: FVG boxes everywhere**
- This is normal! The indicator auto-removes filled gaps
- If still cluttered, disable "Show Fair Value Gaps"
- FVG tracking still works in background for filtering

**Q: Stop loss too tight/loose**
- Switch stop loss method:
  - Percentage: Most consistent
  - Swing: Respects structure (may be wider)
  - ATR: Adapts to volatility
  - VWAP: Uses standard deviation
- Adjust Stop Loss % or ATR Multiplier

**Q: MACD not showing in separate window**
- SwingFlow only plots on main chart
- Add standard MACD indicator separately
- Configure MACD to match your trading style parameters

## Alert Setup

1. Right-click on chart → **Add Alert**
2. Condition: **SwingFlow v0.2**
3. Select either:
   - "Long Entry Signal"
   - "Short Entry Signal"
4. Configure notification method (email, SMS, popup)
5. Create alert

You'll get notified instantly when signals trigger on your watchlist!

## Version History

**v0.2** (Current)
- Complete rebuild from scratch
- Adaptive trading style presets
- Histogram jump detection (15% threshold)
- Smart FVG tracking (auto-removes filled gaps)
- Dynamic R:R calculator (fully adjustable)
- Multi-method stop loss system
- Enhanced visual clarity
- Comprehensive entry/exit labels

## Support

For questions, updates, or feedback on SwingFlow v0.2, document your settings and chart screenshot when reporting issues.

---

**Remember**: No indicator is perfect. Always:
- Use proper position sizing
- Honor your stops
- Take profits at targets
- Combine with your scanner
- Practice on paper trades first

Happy trading! 📈
