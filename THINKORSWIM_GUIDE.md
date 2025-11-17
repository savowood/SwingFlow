# SwingFlow v0.1 - Thinkorswim Guide
## Installation & Usage for TD Ameritrade Platform

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

## 📋 TABLE OF CONTENTS

1. [Prerequisites](#prerequisites)
2. [Installation Steps](#installation-steps)
3. [Configuration Guide](#configuration-guide)
4. [Understanding the Display](#understanding-the-display)
5. [Setting Up Alerts](#setting-up-alerts)
6. [Trading Workflow](#trading-workflow)
7. [Differences from Pine Script Version](#differences-from-pine-script-version)
8. [Troubleshooting](#troubleshooting)

---

## 🎯 PREREQUISITES

### What You Need:
- ✅ TD Ameritrade account (free to open)
- ✅ Thinkorswim platform installed (free download)
- ✅ Basic familiarity with Thinkorswim interface
- ✅ The ThinkScript file: `swingflow_v0.1.thinkscript`

### Platform Download:
- **Desktop:** https://www.tdameritrade.com/tools-and-platforms/thinkorswim/desktop.html
- **Mobile:** Available on iOS and Android app stores
- **Web:** https://trade.thinkorswim.com (limited features)

---

## 📥 INSTALLATION STEPS

### Step 1: Open Thinkorswim

1. Launch Thinkorswim platform
2. Log in with your TD Ameritrade credentials
3. Let the platform fully load

### Step 2: Access Studies (Indicators)

**Desktop Version:**
1. Click on the **"Studies"** button (top toolbar)
2. OR: Click **"Charts" → "Studies"**
3. OR: Right-click on chart → **"Studies..."**

**Alternative Method:**
1. Press **Ctrl+T** (Windows) or **Cmd+T** (Mac)

### Step 3: Create Custom Study

1. In Studies window, click **"Edit Studies"** button
2. Click **"Create..."** at the bottom
3. A code editor window will open

### Step 4: Add the Script

1. **DELETE** all default code in the editor
2. Open `swingflow_v0.1.thinkscript` file
3. **Copy** the entire script
4. **Paste** into Thinkorswim editor
5. Click **"OK"** to save

### Step 5: Name Your Study

1. A dialog will appear: "Save Study Filter"
2. Name it: **"SwingFlow v0.1"**
3. Click **"OK"**

### Step 6: Add to Chart

1. Your study should now appear in the Studies list
2. Find it in the left panel (may need to scroll)
3. **Check the box** next to "SwingFlow v0.1"
4. Study will be added to your chart
5. Click **"OK"** to close Studies window

---

## ⚙️ CONFIGURATION GUIDE

### Opening Settings:

1. Right-click on chart
2. Select **"Edit Studies..."**
3. Find **"SwingFlow v0.1"** in the list
4. Click the **gear icon** (⚙️) next to it
5. Configure parameters

### Key Settings by Market:

#### 📈 STOCKS (Day Trading)
```
tradingStyle: Intraday
useEmaFilter: yes
vwapPullbackType: Touch
volumeMultiplier: 1.5
stopLossType: ATR-Based
atrMultiplier: 1.5
riskRewardRatio: 3.0
```

#### 💰 CRYPTO
```
tradingStyle: Swing
useEmaFilter: yes
vwapPullbackType: Cross Below Then Above
volumeMultiplier: 1.2
stopLossType: ATR-Based
atrMultiplier: 2.0
riskRewardRatio: 3.0
```

#### 💱 FOREX
```
tradingStyle: Swing
useEmaFilter: yes
vwapPullbackType: Within Range
vwapRangePercent: 0.5
volumeMultiplier: 1.2
stopLossType: ATR-Based
atrMultiplier: 1.5
riskRewardRatio: 3.0 to 5.0
```

#### 📊 FUTURES
```
tradingStyle: Intraday or Swing
useEmaFilter: yes
vwapPullbackType: Touch
volumeMultiplier: 1.2
stopLossType: ATR-Based
atrMultiplier: 1.5-2.0
riskRewardRatio: 2.0 to 3.0
```

### Recommended Beginner Settings:
```
tradingStyle: Swing
useEmaFilter: yes (checked)
useVwap: yes (checked)
useMacdConfirmation: yes (checked)
useRsi: no (unchecked)
useStochastic: no (unchecked)
useBollinger: no (unchecked)
useVolumeFilter: yes (checked)
volumeMultiplier: 1.2
riskRewardRatio: 3.0
stopLossType: ATR-Based
atrMultiplier: 1.5
```

---

## 📊 UNDERSTANDING THE DISPLAY

### Chart Elements:

1. **Blue Line** - EMA 9 (Fast trend)
2. **Orange Line** - EMA 20 (Medium trend)
3. **Red Line** - EMA 180 (Long-term trend)
4. **Purple/Magenta Line** - VWAP (Key pullback level)
5. **Green Arrow Up** ⬆️ - BUY SIGNAL
6. **Light Green Cloud** - Highlights signal bars

### Top Labels (Status Display):

The labels at the top of your chart show:

| Label | Meaning |
|-------|---------|
| **EMA Stack: Bullish ✓** | Price is above all EMAs in proper order |
| **EMA Stack: Bearish ✗** | EMAs not aligned or price below |
| **VWAP: Active ✓** | Pullback condition met |
| **VWAP: Waiting** | No pullback detected yet |
| **MACD: Bullish ✓** | Momentum is positive |
| **MACD: Bearish ✗** | Momentum is negative |
| **RSI: 45.2** | Current RSI value (if enabled) |
| **Volume: Strong ✓** | Above average volume |
| **Volume: Weak** | Below threshold |
| **R:R = 3.0:1** | Your risk:reward ratio setting |

### Display Settings:

You can toggle visibility of elements:

```
showEmas: yes/no - Show/hide EMA lines
showVwap: yes/no - Show/hide VWAP line
showBollingerBands: yes/no - Show/hide BB (if enabled)
showSignalArrows: yes/no - Show/hide buy arrows
showPriceLabels: yes/no - Show/hide top labels
```

---

## 🔔 SETTING UP ALERTS

### Desktop Alerts:

1. Right-click on chart
2. Select **"Create Alert..."**
3. In alert window:
   - **Condition:** Select "Study Alert"
   - **Study:** Choose "SwingFlow v0.1"
   - **Alert Type:** Choose how you want to be notified
     - ✅ Play sound
     - ✅ Show popup
     - ✅ Send push notification (requires mobile app)
4. Click **"Create"**

### Mobile Push Notifications:

1. Download Thinkorswim mobile app
2. Log in with same credentials
3. Go to **Settings → Notifications**
4. Enable **"Alert Notifications"**
5. Desktop alerts will now push to your phone!

### Email Alerts:

1. In alert creation window
2. Check **"Send email"**
3. Enter your email address
4. Click **"Create"**

### SMS Alerts:

Thinkorswim doesn't directly support SMS, but you can use:
- Email-to-SMS gateway (e.g., your-number@vtext.com for Verizon)
- Or use mobile push notifications instead

---

## 💼 TRADING WORKFLOW

### Step 1: Chart Setup (One-time)

1. Open Thinkorswim
2. Load your instrument (stock, ETF, crypto, etc.)
3. Set timeframe:
   - **Intraday trading:** 5-minute chart
   - **Swing trading:** 1-hour or 4-hour chart
   - **Position trading:** Daily chart
4. Add SwingFlow study
5. Configure settings for your style
6. Set up alerts

### Step 2: Monitoring

**Active Monitoring:**
- Watch for green arrows ⬆️
- Check top labels for confirmation
- All indicators should be "green" or "✓"

**Passive Monitoring:**
- Set up alerts
- Wait for notification
- Check chart when alerted

### Step 3: Trade Execution

When you get a signal:

1. **Verify Signal:**
   - Green arrow present ✅
   - EMA Stack bullish ✅
   - VWAP pullback confirmed ✅
   - MACD bullish ✅
   - Volume strong ✅

2. **Calculate Position:**
   - Note current price
   - Strategy suggests stop loss based on your settings
   - Calculate position size (risk 1-2% of capital)

3. **Enter Trade:**
   - **Right-click chart** → "Trade"
   - Or use Active Trader window
   - Or use TD Ameritrade mobile app
   - Enter: BUY order at market or limit

4. **Set Stop Loss:**
   - Based on your stop loss type setting
   - **ATR-Based:** Current price - (ATR × multiplier)
   - **Percentage:** Current price × (1 - stop%)
   - **Recent Low:** Below recent swing low
   
5. **Set Take Profit:**
   - Risk amount × Risk:Reward ratio
   - If risking $100, target $300 (3:1 ratio)

### Step 4: Trade Management

**Using Thinkorswim:**
1. Right-click your position → "Create closing order..."
2. Set bracket orders (stop + target)
3. Adjust as needed

**Trailing Stop:**
- Manually adjust stop as price moves in your favor
- Move stop to breakeven after 1R profit
- Continue trailing based on price action

---

## 📊 STRATEGY TESTING (BACKTESTING)

### ThinkOnDemand (Simulated Trading):

1. Click **"Tools" → "thinkOnDemand"**
2. Select a past date
3. "Replay" the market with your strategy
4. See how signals perform
5. **Note:** This is manual review, not automated backtesting

### Paper Money (Practice Account):

1. Switch to **"Paper Money"** mode (top-right toggle)
2. Trade with fake money
3. Test the strategy risk-free
4. Track your results for 30+ days
5. Switch back to live when consistently profitable

### Strategy Performance Tracking:

Thinkorswim doesn't have built-in backtest like TradingView, but you can:

1. Use **ThinkBack** feature (Tools → ThinkBack)
2. Manually track trades in a journal
3. Export trade history to Excel
4. Calculate win rate, avg R:R, etc.

---

## 🔄 DIFFERENCES FROM PINE SCRIPT VERSION

### What's the Same:
- ✅ All core logic (EMA stack, VWAP pullback, MACD, etc.)
- ✅ Same settings and parameters
- ✅ Same entry signals
- ✅ Same risk management calculations
- ✅ Same visual indicators

### What's Different:

| Feature | Pine Script (TradingView) | ThinkScript (Thinkorswim) |
|---------|--------------------------|---------------------------|
| **Strategy vs Study** | Can run as strategy with auto-backtest | Study only (no auto-backtest) |
| **Dashboard** | Built-in performance table | Labels at top of chart |
| **Position Tracking** | Automatic position management | Manual trade execution |
| **Backtesting** | Full automated backtesting | Manual review with ThinkOnDemand |
| **Alerts** | Web/mobile/email | Desktop/mobile/email |
| **Trailing Stop** | Automatic in backtest | Must manually adjust |

### ThinkScript Limitations:

- ❌ No automatic strategy execution
- ❌ No built-in backtesting engine
- ❌ No position size calculator built-in
- ❌ No automatic trailing stops

### ThinkScript Advantages:

- ✅ Direct integration with TD Ameritrade
- ✅ One-click trading from charts
- ✅ Professional-grade charting
- ✅ Real-time data (with live account)
- ✅ Paper Money for practice
- ✅ Better order execution tools

---

## 🐛 TROUBLESHOOTING

### "Study does not compile" Error:

**Cause:** Syntax error or missing code

**Fix:**
1. Make sure you copied the ENTIRE script
2. Check you deleted all default code before pasting
3. Ensure no extra characters at beginning/end
4. Try copying again from the original file

### No Arrows/Signals Appearing:

**Cause:** Filters too restrictive or wrong timeframe

**Fix:**
1. Check your timeframe matches trading style
2. Disable optional filters (RSI, Stochastic, Bollinger)
3. Lower volume multiplier to 1.0
4. Try on a known trending stock (like SPY)

### EMAs/VWAP Not Showing:

**Cause:** Display settings or chart issue

**Fix:**
1. Edit study settings
2. Check: `showEmas = yes`, `showVwap = yes`
3. Make sure chart is on price view (not volume)
4. Check line colors aren't same as background

### Labels Crowding Chart:

**Cause:** Too many labels enabled

**Fix:**
1. Edit study settings
2. Set `showPriceLabels = no` to hide top labels
3. Or manually resize label area

### Wrong Signals on Crypto/Forex:

**Cause:** Volume data may be limited

**Fix:**
1. Disable volume filter: `useVolumeFilter = no`
2. Rely more on price action and EMAs
3. Use futures instead of spot for better data

### Strategy Not Working Well:

**Cause:** Market conditions or settings mismatch

**Fix:**
1. Test in Paper Money first
2. Adjust lookback period for your timeframe
3. Review last 20 signals manually
4. May need to customize for specific instruments

---

## 💡 TIPS FOR SUCCESS

### 1. Chart Organization

**Create Multiple Workspaces:**
- Workspace 1: Day trading (5-min charts)
- Workspace 2: Swing trading (1H/4H charts)
- Workspace 3: Long-term (Daily charts)

**Save Layouts:**
- Tools → Application Settings → Save Workspace

### 2. Quick Access

**Add to Favorites:**
1. Right-click study in Studies list
2. Select "Add to favorites"
3. Access quickly from toolbar

### 3. Multi-Symbol Monitoring

**Create Watchlist:**
1. Add symbols you trade
2. Link chart to watchlist
3. Click through symbols quickly
4. Strategy updates automatically

### 4. Mobile Trading

**On Thinkorswim Mobile:**
1. Charts → Studies → Add Study
2. Find "SwingFlow v0.1"
3. Add to chart
4. Get alerts on the go
5. Trade directly from phone

### 5. Integration with Active Trader

**For Fast Execution:**
1. Open Active Trader window
2. Link to chart (chain link icon)
3. When signal appears, one-click trade
4. Set bracket orders instantly

---

## 📚 RECOMMENDED LEARNING PATH

### Week 1: Setup & Familiarization
- [ ] Install Thinkorswim platform
- [ ] Add SwingFlow study
- [ ] Watch signals on paper money
- [ ] Learn the platform interface
- [ ] Set up alerts

### Week 2-3: Paper Trading
- [ ] Switch to Paper Money mode
- [ ] Take 10+ trades following signals
- [ ] Track results in journal
- [ ] Adjust settings as needed
- [ ] Practice order entry/exit

### Week 4: Evaluation
- [ ] Review paper trading results
- [ ] Calculate win rate and avg R:R
- [ ] Identify best setups
- [ ] Fine-tune settings
- [ ] Decide if ready for live

### Month 2+: Live Trading
- [ ] Start with small position sizes
- [ ] Risk only 1% per trade
- [ ] Build confidence over time
- [ ] Continue journaling
- [ ] Review weekly performance

---

## 🔗 HELPFUL RESOURCES

### TD Ameritrade Resources:
- **ThinkScript Learning Center:** https://tlc.thinkorswim.com/center/reference/thinkScript
- **Video Tutorials:** https://www.youtube.com/user/TDAmeritrade
- **Support:** 1-800-672-2098

### Community:
- **r/thinkscript** subreddit
- **ThinkorSwim Discord servers**
- **TD Ameritrade community forums**

### Related Guides:
- [SWINGFLOW_README.md](SWINGFLOW_README.md) - Strategy methodology
- [QUICK_START_GUIDE.md](QUICK_START_GUIDE.md) - Quick reference
- [ADVANCED_CUSTOMIZATION.md](ADVANCED_CUSTOMIZATION.md) - Advanced modifications

---

## 🆚 PINE SCRIPT vs THINKSCRIPT COMPARISON

### When to Use TradingView (Pine Script):
- ✅ Want automated backtesting
- ✅ Need detailed performance metrics
- ✅ Strategy optimization
- ✅ Multiple timeframe analysis
- ✅ Creating public indicators
- ✅ Lower-cost solution

### When to Use Thinkorswim (ThinkScript):
- ✅ TD Ameritrade customer
- ✅ Want direct trading integration
- ✅ Need professional charting
- ✅ Real-time Level 2 data
- ✅ Advanced order types
- ✅ U.S. stocks/options focus

### Best of Both Worlds:
Many traders use BOTH:
1. **TradingView:** Strategy development and backtesting
2. **Thinkorswim:** Live trading and execution

---

## ❓ FAQ

**Q: Can I automate trades with ThinkScript?**  
A: No, ThinkScript is for analysis only. You must manually enter trades.

**Q: Does this work on Thinkorswim mobile?**  
A: Yes! The study works on mobile, though configuration is easier on desktop.

**Q: Can I share this with friends?**  
A: Yes, share the .thinkscript file. They can import it the same way.

**Q: Will this work on TD Ameritrade's regular platform?**  
A: No, only on Thinkorswim. The regular web platform doesn't support custom studies.

**Q: How much does Thinkorswim cost?**  
A: It's FREE with a TD Ameritrade account (even $0 balance accounts).

**Q: Can I modify the script?**  
A: Yes! Edit Studies → select the study → click gear icon → edit code.

**Q: What if I get different signals than TradingView?**  
A: Small differences are normal due to data providers. The logic is the same.

**Q: Does this work for options?**  
A: This is designed for stocks/ETFs/futures. For options, use on underlying asset.

---

## 🎯 QUICK START CHECKLIST

- [ ] TD Ameritrade account open
- [ ] Thinkorswim platform downloaded and installed
- [ ] SwingFlow script copied
- [ ] Study created in Thinkorswim
- [ ] Study added to chart
- [ ] Settings configured for your market
- [ ] Alerts set up
- [ ] Paper Money mode activated
- [ ] First signal observed
- [ ] Trading plan documented

---

## 📞 SUPPORT

**For Strategy Questions:**
- Review: [SWINGFLOW_README.md](SWINGFLOW_README.md)
- Educational Resources: Ross Cameron, Joovier on YouTube

**For Platform Help:**
- TD Ameritrade Support: 1-800-672-2098
- ThinkScript Documentation: tlc.thinkorswim.com

**Support the Developer:**
☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

**Good luck with Thinkorswim trading! 🚀📈**

Remember: Start with Paper Money, track your results, and only go live when consistently profitable!
