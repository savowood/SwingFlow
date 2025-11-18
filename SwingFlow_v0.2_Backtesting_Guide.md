# SwingFlow v0.2 Strategy - Backtesting Guide

## Overview
SwingFlow v0.2 Strategy is the backtesting version of the SwingFlow indicator. It allows you to test the performance of your settings on historical data before using them in live trading.

## Installation

1. Open TradingView
2. Click **Pine Editor** at bottom
3. Click **New** → **Blank strategy**
4. Copy the entire code from `swingflow_v0.2_strategy.pine`
5. Paste into editor
6. Click **Save** (name it "SwingFlow v0.2 Strategy")
7. Click **Add to Chart**

**Note**: Use the **strategy** version for backtesting, use the **indicator** version for live trading signals.

## Backtesting Features

### Performance Statistics Table
When enabled, displays in top-right corner:
- **Total Trades**: Number of completed trades
- **Win Rate**: Percentage of winning trades
- **Winning Trades**: Count of profitable trades
- **Losing Trades**: Count of losing trades
- **Avg Win**: Average profit per winning trade ($)
- **Avg Loss**: Average loss per losing trade ($)
- **Profit Factor**: Total profit / Total loss (higher is better)
  - \> 2.0 = Excellent (Green)
  - 1.0-2.0 = Good (Yellow)
  - < 1.0 = Losing system (Red)

### Backtesting Settings

#### Enable Backtesting
Toggle on/off to control whether trades are executed (useful for viewing signals without trades)

#### Initial Capital
- **Default**: $10,000
- Set your starting account balance

#### Risk Per Trade
- **Default**: 100% (uses full account)
- **Recommended**: 10-25% for more realistic position sizing
- This determines what % of equity is risked per trade

#### TP1/TP2 Exits
- **TP1 (50% exit)**: Exit half position at first target
- **TP2 (full exit)**: Exit remaining position at final target
- Toggle independently to test different exit strategies

#### Show Performance Stats
Toggle the statistics table on/off

### Date Range Filter

Use this to test specific time periods:

1. Enable "Use Date Filter"
2. Set **Start Date** (e.g., Jan 1, 2023)
3. Set **End Date** (e.g., Dec 31, 2025)

This is useful for:
- Testing only recent market conditions
- Excluding anomalous periods (COVID crash, etc.)
- Testing different market regimes separately

## How to Run a Backtest

### Step 1: Load Historical Data
1. Select your ticker (e.g., VRA)
2. Select your timeframe (e.g., 5 minutes)
3. TradingView will load historical data

### Step 2: Configure Settings
1. Choose your **Trading Style** (Intraday, Swing, etc.)
2. Enable/disable **Entry Filters** based on what you want to test
3. Set **Risk Management** parameters
   - R:R Ratio (3:1 recommended)
   - Stop Loss Method
   - Stop Loss %

### Step 3: Run the Test
The strategy will automatically:
- Execute trades based on your signals
- Apply stops and take profits
- Track performance

### Step 4: Analyze Results

#### Built-in TradingView Metrics
At the bottom of the chart, TradingView shows:
- **Net Profit**: Total profit/loss
- **Total Closed Trades**: Number of completed trades
- **Percent Profitable**: Win rate
- **Profit Factor**: Risk/reward efficiency
- **Max Drawdown**: Largest peak-to-trough decline
- **Avg Trade**: Average profit per trade
- **Avg # Bars in Trade**: How long trades last

#### SwingFlow Stats Table
In top-right corner:
- Quick summary of key metrics
- Color-coded for easy interpretation
- Updates in real-time as you adjust settings

## Optimization Workflow

### 1. Baseline Test
Start with default settings:
```
Trading Style: Intraday
All filters: Enabled
R:R Ratio: 3:1
Stop Loss: 2% Percentage
```

Run the backtest and record:
- Net Profit
- Win Rate
- Profit Factor
- Max Drawdown

### 2. Test Trading Styles
Keep filters the same, but test each style:
- Scalping (1-5min charts)
- Intraday (5-15min charts)
- Swing (1hr-4hr charts)

Find which style works best for your ticker.

### 3. Filter Optimization
Once you find your best style, test removing filters one at a time:

**Test A**: Disable "Trend Filter"
- Did win rate improve or decline?
- More trades or fewer?

**Test B**: Disable "FVG Filter"
- How does this affect results?

**Test C**: Adjust "Histogram Jump Threshold"
- Try 10%, 15%, 20%, 25%
- Find optimal sensitivity

### 4. Risk Management Testing
Test different R:R ratios:
- 2:1 (more frequent wins, smaller gains)
- 3:1 (balanced)
- 4:1 (fewer wins, larger gains)
- 5:1 (rare wins, huge gains)

Test different stop methods:
- Percentage (consistent risk)
- Swing (structure-based)
- ATR (volatility-adjusted)
- VWAP (indicator-based)

### 5. Exit Strategy Testing
Test different combinations:
- Both TP1 and TP2 enabled (partial exits)
- Only TP2 enabled (full position to target)
- Vary the R:R ratio with each

## Example Optimization Session

### Ticker: VRA
**Timeframe**: 5-minute  
**Period**: Last 3 months

#### Test 1: Baseline
```
Style: Intraday
Filters: All enabled
R:R: 3:1
Stop: 2% Percentage

Results:
- Net Profit: $450
- Win Rate: 48%
- Profit Factor: 1.8
- Trades: 23
```

#### Test 2: Disable Trend Filter
```
Same as above, but Trend Filter OFF

Results:
- Net Profit: $620
- Win Rate: 45%
- Profit Factor: 2.1
- Trades: 31
```
**Finding**: More trades, slightly lower win rate, but better profit factor!

#### Test 3: Lower Histogram Threshold
```
Same as Test 2, but Threshold: 10%

Results:
- Net Profit: $580
- Win Rate: 42%
- Profit Factor: 1.9
- Trades: 45
```
**Finding**: Too many signals, decreased performance. 15% was better.

#### Test 4: Adjust R:R
```
Best settings from Test 2, but R:R: 4:1

Results:
- Net Profit: $520
- Win Rate: 38%
- Profit Factor: 2.3
- Trades: 31
```
**Finding**: Higher profit factor but lower total profit. 3:1 was better for this ticker.

### Final Optimized Settings
```
Trading Style: Intraday
VWAP Cross: ✅
MACD Histogram Expansion: ✅
Volume Confirmation: ✅
Trend Filter: ⬜ (DISABLED)
FVG Filter: ⬜
Histogram Jump: ✅ (15%)
R:R Ratio: 3:1
Stop Loss: 2% Percentage
```

## Important Notes

### Backtesting Limitations
1. **Past performance ≠ future results**: Markets change
2. **Overfitting**: Don't optimize too much for historical data
3. **Slippage**: Real trades have slippage, backtests assume perfect fills
4. **Commission**: Strategy includes 0.1% commission, adjust if yours differs
5. **Liquidity**: Backtests don't account for low liquidity

### Best Practices
1. **Test on multiple tickers**: Don't optimize for just one
2. **Test different time periods**: Bull markets, bear markets, choppy markets
3. **Out-of-sample testing**: Optimize on 70% of data, validate on remaining 30%
4. **Walk-forward analysis**: Test on rolling windows (e.g., optimize on 6 months, test on next month)
5. **Paper trade first**: Even with good backtest, paper trade before going live

### Red Flags in Backtests
⚠️ **Warning signs of overfitting:**
- Win rate > 70%
- Profit factor > 5
- Only works on one ticker
- Works on one period but not others
- Too many filters/conditions

⚠️ **Unrealistic results:**
- 100% win rate (impossible)
- Consistent wins with no drawdowns
- Returns that seem too good to be true

## Comparing Indicator vs Strategy

### Indicator Version (swingflow_v0.2.pine)
✅ Use for live trading  
✅ Real-time alerts  
✅ Clean chart display  
✅ Manual trade execution  

### Strategy Version (swingflow_v0.2_strategy.pine)
✅ Use for backtesting  
✅ Performance statistics  
✅ Automatic trade execution (in backtest)  
✅ Optimization testing  
❌ Don't use for live trading (use indicator version instead)

## Sample Backtest Report Format

After optimizing, document your findings:

```markdown
# SwingFlow v0.2 Backtest Report

**Ticker**: VRA
**Timeframe**: 5-minute
**Period**: Sept 1 - Nov 18, 2025
**Initial Capital**: $10,000

## Settings
- Trading Style: Intraday
- Trend Filter: Disabled
- Histogram Threshold: 15%
- R:R Ratio: 3:1
- Stop Loss: 2% Percentage

## Results
- Total Trades: 31
- Winning Trades: 14 (45%)
- Losing Trades: 17 (55%)
- Net Profit: $620 (6.2% return)
- Profit Factor: 2.1
- Avg Win: $82
- Avg Loss: $38
- Max Drawdown: $280 (2.8%)
- Largest Win: $156
- Largest Loss: $68

## Key Findings
- Disabling trend filter increased trade count by 35%
- 15% histogram threshold was optimal (10% = too noisy, 20% = too few)
- 3:1 R:R provided best balance
- Most wins occurred 10:00 AM - 2:00 PM EST
- Avoid trading first 30 min and last hour

## Next Steps
1. Paper trade for 2 weeks with these settings
2. Monitor win rate (target: >45%)
3. Track if live results match backtest
4. Re-optimize monthly based on market conditions
```

## Troubleshooting

**Q: Strategy shows no trades**
- Check date filter (may be outside range)
- Verify "Enable Backtesting" is ON
- Ensure at least one direction (Long/Short) is enabled
- Check if filters are too restrictive

**Q: Unrealistic profit/loss**
- Verify commission settings (default 0.1%)
- Check slippage (default 2 ticks)
- Ensure risk per trade isn't set to 100% (use 10-25%)

**Q: Stats table not showing**
- Enable "Show Performance Stats"
- Ensure you're on the last bar (zoom out if needed)
- Try refreshing the chart

**Q: Results differ from indicator**
- Strategy executes at close of signal bar
- Indicator shows signal in real-time
- This timing difference is normal

---

## Quick Start Checklist

- [ ] Load SwingFlow v0.2 Strategy in TradingView
- [ ] Select ticker and timeframe
- [ ] Set "Initial Capital" to your account size
- [ ] Set "Risk Per Trade" to 10-25%
- [ ] Enable "Show Performance Stats"
- [ ] Run baseline test with default settings
- [ ] Record results (Net Profit, Win Rate, Profit Factor)
- [ ] Test different Trading Styles
- [ ] Optimize filters one at a time
- [ ] Test different R:R ratios
- [ ] Document final optimized settings
- [ ] Paper trade before going live

Happy backtesting! 📊
