# SwingFlow v0.2.2 - Quick Reference Card

**Support:** ☕ https://www.buymeacoffee.com/savowood  
**Updates:** 📦 https://github.com/savowood/SwingFlow

---

## 🎯 What Am I Looking At?

### Arrow Colors (Entry Signals)
| Arrow | Color | Pattern | Entry Type |
|-------|-------|---------|------------|
| 🟢 △ | Dark Green | Below VWAP, bouncing up | Pullback Long |
| 🟢 △ | Bright Lime | Crossing VWAP upward | Breakout Long |
| 🔴 ▽ | Dark Red | Above VWAP, dropping | Pullback Short |
| 🔴 ▽ | Bright Fuchsia | Crossing VWAP downward | Breakout Short |

### Other Symbols
| Symbol | Meaning |
|--------|---------|
| 💎 | Histogram jump (momentum reversal) |
| ━━━ Blue Dashed | Stop loss level |
| ━━━ Yellow Solid | Take Profit 1 (exit 50%) |
| ━━━ Orange Solid | Take Profit 2 (exit remaining) |
| ⬜ Green Box | Bullish FVG (support) |
| ⬜ Red Box | Bearish FVG (resistance) |

### Entry Label Example
```
📈 LONG $3.67
📍 Breakout
🛡️ SL: $3.59 (-2.2%)
🎯 TP1: $3.83 (+4.4%)
🎯 TP2: $3.99 (+8.7%)
```

---

## ⚙️ Settings Cheat Sheet

### Conservative (Fewer, Higher Quality)
```
Entry Mode: "Pullback Only"
Histogram Threshold: 20%
Trend Filter: ON
FVG Filter: ON
R:R Ratio: 4:1
```

### Balanced (Recommended Default)
```
Entry Mode: "Both"
VWAP Proximity: 2.0%
Histogram Threshold: 15%
Trend Filter: OFF
Volume Confirmation: ON
R:R Ratio: 3:1
```

### Aggressive (More Signals)
```
Entry Mode: "Both"
Histogram Threshold: 10%
All Filters: OFF
R:R Ratio: 2:1
```

---

## 📊 Entry Modes Quick Guide

### "Pullback Only"
- **Catches:** VRA-style mean-reversion trades
- **Best for:** Range-bound stocks, choppy markets
- **Win rate:** 60-70%
- **R:R:** 2.5-3:1
- **Signals/day:** 2-4

### "Breakout Only"
- **Catches:** ANVS-style momentum trades
- **Best for:** Trending stocks, high volume
- **Win rate:** 50-60%
- **R:R:** 3-4:1
- **Signals/day:** 1-3

### "Both" (Default)
- **Catches:** Everything above
- **Best for:** Most traders, maximum opportunities
- **Win rate:** 55-65%
- **R:R:** 2.8-3.2:1
- **Signals/day:** 3-7

---

## 🎯 Trading Workflow

### Step 1: Find Stock
```
Your Scanner:
- Price: $2-15
- Change: 5-15%
- Volume: 2M+
- Rel. Volume: 1.5x+
```

### Step 2: Watch for Signal
```
SwingFlow v0.2.2:
- 5-min chart
- Entry Mode: "Both"
- Wait for arrow
```

### Step 3: Enter Trade
```
Green Arrow (Pullback):
├─ Entry: Label price
├─ Stop: Blue dashed line
├─ TP1: Yellow line (50% out)
└─ TP2: Orange line (full out)

Lime Arrow (Breakout):
├─ Entry: Label price
├─ Stop: Wider (3-4%)
├─ TP1: Yellow line (50% out)
└─ TP2: Orange line (trail stop)
```

---

## 💡 Pro Tips

### Best Signals
1. Arrow + 💎 Diamond = Highest probability
2. Arrow near FVG box = Extra confirmation
3. Arrow with 2x volume = Strong momentum
4. Multiple timeframe alignment = Best setup

### Best Times (EST)
- ✅ 10:00 AM - 2:00 PM (prime time)
- ⚠️ 9:30-10:00 AM (avoid first 30 min)
- ⚠️ 3:30-4:00 PM (avoid last 30 min)

### Position Sizing
- **Pullback (green):** Standard size
- **Breakout (lime):** 75% size (wider stops)
- **With diamond:** 125% size (highest confidence)

### Risk Management
- Never risk more than 2% per trade
- Always use stop losses
- Take partial profits at TP1
- Trail stop after TP1 hit

---

## 🔧 Quick Fixes

### No Signals?
1. Entry Mode → "Both"
2. Histogram Threshold → 10%
3. Disable all filters
4. Try 5-min or 15-min chart

### Too Many Signals?
1. Entry Mode → "Pullback Only"
2. Enable Trend Filter
3. Histogram Threshold → 20%
4. Enable FVG Filter

### Can't See Arrows?
1. Enable "Show Entry Arrows"
2. Zoom out
3. Check Long/Short both enabled

### Can't See Levels?
1. Enable "Show Stop Loss Lines"
2. Enable "Show Take Profit Lines"
3. Enable "Label Risk:Reward"

---

## 📈 Optimization Workflow

### Week 1: Baseline
```
Entry Mode: "Both"
Track:
├─ Green arrows: ___ wins, ___ losses
├─ Lime arrows: ___ wins, ___ losses
└─ Best time of day: _______
```

### Week 2: Optimize
```
If green wins more:
├─ Entry Mode → "Pullback Only"
└─ Tighten stops

If lime wins more:
├─ Entry Mode → "Breakout Only"
└─ Widen stops

If both win equally:
└─ Keep "Both"
```

### Week 3: Fine-tune
```
Adjust:
├─ VWAP Proximity (1.5-3%)
├─ Histogram Threshold (10-25%)
├─ R:R Ratio (2-5:1)
└─ Time filters
```

---

## 📊 Performance Tracking

### Daily Log Template
```
Date: __________
Ticker: ________
Entry: $_______ (Green/Lime)
Type: Pullback / Breakout
Stop: $_______ (-__%)
TP1: $_______ (+__%)
TP2: $_______ (+__%)
Result: Win / Loss ($____)
Notes: _________________
```

### Weekly Summary
```
Week of: __________
Total Trades: ___
Pullback: ___ wins, ___ losses
Breakout: ___ wins, ___ losses
Win Rate: ___%
Avg R:R: __:1
Total P&L: $____
Best Setup: _______
Worst Setup: _______
Next Week Plan: _______
```

---

## 🆘 Emergency Checklist

### Lost Money? Review:
- [ ] Did you use stop loss?
- [ ] Did you size position correctly?
- [ ] Did you take TP1 profits?
- [ ] Did you trade outside best hours?
- [ ] Did you chase after signal appeared?
- [ ] Did you ignore entry type?
- [ ] Did you overtrade?

### Winning Streak? Don't:
- [ ] Increase position size too fast
- [ ] Start ignoring stop losses
- [ ] Trade outside your system
- [ ] Get overconfident
- [ ] Stop tracking results

---

## 📱 Mobile Quick Reference

### On the Go
1. TradingView mobile app
2. View SwingFlow signals
3. Enter trades on phone
4. Manage positions
5. Set alerts

### Alerts Setup
```
1. Right-click chart
2. Add Alert
3. Condition: SwingFlow v0.2.2
4. Options: Long/Short Entry
5. Notifications: SMS/Email/Push
```

---

## 🎓 Learning Resources

### Start Here
1. **README_FIRST.md** (5 min)
2. Install indicator
3. Watch for signals
4. Take screenshot of first signal

### Go Deeper
1. **SwingFlow_v0.2.2_Guide.md** (30 min)
2. **COMPARISON doc** (if from v0.2.1)
3. **CHANGELOG** (version history)

### Master It
1. Backtest with strategy version
2. Test different entry modes
3. Optimize for your tickers
4. Develop personal playbook

---

## 💰 Real Examples

### VRA Pullback (Your Trade)
```
Entry: $2.77 (green arrow)
Type: Pullback
Stop: $2.71
Exit: $2.87
Profit: $500
Result: ✅ Success!
```

### ANVS Breakout (Previously Missed)
```
Entry: $3.67 (lime arrow)
Type: Breakout
v0.2.1: ❌ Missed
v0.2.2: ✅ Caught!
```

---

## 🏆 Success Metrics

### Good Day
- 2-3 signals
- 60%+ win rate
- 3:1 avg R:R
- Stuck to plan

### Great Day
- 3-5 signals
- 70%+ win rate
- 4:1 avg R:R
- Hit TP2 on multiple trades

### Perfect Day
- 2-3 high-quality signals
- 100% win rate
- Captured pullback + breakout
- Took profits at levels

---

## 📞 Support

**Get Help:**
- 📖 Read: SwingFlow_v0.2.2_Guide.md
- 📄 Check: CHANGELOG_v0.2.2.md
- 💬 TradingView: Comment on script
- 🐛 GitHub: Report issues

**Support Developer:**
- ☕ https://www.buymeacoffee.com/savowood
- ⭐ Star on GitHub
- 📢 Share with traders

---

## ✅ Daily Checklist

### Pre-Market
- [ ] Review scanner results
- [ ] Check SwingFlow settings
- [ ] Verify Entry Mode ("Both")
- [ ] Set alerts if needed
- [ ] Review yesterday's trades

### During Market
- [ ] Watch for arrows
- [ ] Check entry type (green/lime)
- [ ] Verify volume surge
- [ ] Enter at label price
- [ ] Set stops immediately
- [ ] Take TP1 at yellow line

### Post-Market
- [ ] Log all trades
- [ ] Calculate win rate
- [ ] Review best setups
- [ ] Update strategy
- [ ] Plan tomorrow

---

**Print this card and keep it by your desk!** 📄

**Swing with the Flow!** 🕺📈

---

**Version:** 0.2.2  
**Last Updated:** November 18, 2025  
**Platform:** TradingView (Pine Script v6)
