# SwingFlow v0.1 - Quick Start Guide

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

## ⚡ QUICK INSTALLATION

1. Open TradingView → Pine Editor (bottom panel)
2. Click "Create" → New Indicator
3. Copy/paste code from `swingflow_v0.1.pine`
4. Click "Save" → Name it "SwingFlow v0.1"
5. Click "Add to Chart"

---

## 🎯 BEST SETTINGS BY MARKET

### 📈 STOCKS (Day Trading)
```
Trading Style: Intraday
Chart: 5 minute
EMA Stack Filter: ✓ ON
VWAP Mode: Touch
Volume Multiplier: 1.5x
Risk:Reward: 3:1
```

### 💰 CRYPTO
```
Trading Style: Swing
Chart: 1 Hour or 4 Hour
EMA Stack Filter: ✓ ON
VWAP Mode: Cross Below Then Above
Stop Loss: ATR 2.0x
Risk:Reward: 3:1
Trailing Stop: ✓ ON
```

### 💱 FOREX
```
Trading Style: Swing
Chart: 1 Hour or Daily
EMA Stack Filter: ✓ ON
VWAP Mode: Within Range (0.5%)
Stop Loss: ATR 1.5x
Risk:Reward: 3:1 to 5:1
```

### 📊 FUTURES
```
Trading Style: Intraday/Swing
Chart: 15 min or 1 Hour
EMA Stack Filter: ✓ ON
VWAP Mode: Touch
Stop Loss: ATR 1.5-2.0x
Risk:Reward: 2:1 to 3:1
```

---

## 📊 UNDERSTANDING THE CHART

**Lines on Chart:**
- **Blue Line** = 9 EMA (fast trend)
- **Orange Line** = 20 EMA (medium trend)
- **Red Line** = 180 EMA (long-term trend)
- **Purple Circles** = VWAP (key pullback level)
- **Green Triangle** = BUY SIGNAL
- **Red Line (in trade)** = Stop Loss
- **Green Line (in trade)** = Take Profit

**Dashboard (Top Right):**
Shows real-time status of all indicators and filters

---

## ✅ WHAT MAKES A GOOD TRADE

**Perfect Setup Checklist:**
1. ✓ EMA Stack Bullish (9 > 20 > 180)
2. ✓ Price pulls back to VWAP or 9/20 EMA
3. ✓ MACD shows bullish momentum
4. ✓ Volume above average
5. ✓ Bullish candle pattern forms
6. ✓ Green triangle appears

**Only trade when you see the green triangle!**

---

## ⚙️ RECOMMENDED BEGINNER SETTINGS

**Start with these and don't change anything else:**

```
✓ Trading Style: Swing
✓ Position Size: 25% (conservative)
✓ EMA Stack Filter: ON
✓ VWAP Mode: Touch
✓ MACD Confirmation: ON
✓ Volume Filter: ON (1.2x multiplier)
✓ Risk:Reward: 3:1
✓ Stop Loss: ATR-Based (1.5x)
✓ Trailing Stop: ON
✓ RSI Filter: OFF (for now)
✓ Stochastic Filter: OFF (for now)
✓ Bollinger Bands: OFF (for now)
```

---

## 🚨 COMMON MISTAKES TO AVOID

❌ **Don't:** Change default EMAs (9/20/180)
✅ **Do:** Keep them as-is - they work!

❌ **Don't:** Trade every signal
✅ **Do:** Wait for high-quality setups only

❌ **Don't:** Use 100% position size when starting
✅ **Do:** Start with 25-50% until profitable

❌ **Don't:** Move your stop loss further away
✅ **Do:** Accept the loss and move on

❌ **Don't:** Revenge trade after a loss
✅ **Do:** Take a break and analyze what happened

---

## 📈 BACKTESTING CHECKLIST

Before going live:

- [ ] Test on at least 6 months of data
- [ ] Check Profit Factor > 1.5
- [ ] Verify Win Rate > 45%
- [ ] Max Drawdown should be < 25%
- [ ] Test on your specific instruments
- [ ] Paper trade for 30+ days
- [ ] Keep a trading journal

---

## 🎓 30-DAY LEARNING PATH

**Week 1: Learn**
- Install strategy
- Watch educational videos (see Educational Resources in main README)
- Understand each indicator
- Run backtests on different instruments

**Week 2-3: Practice**
- Paper trade with demo account
- Take screenshots of every trade
- Journal why you entered/exited
- Review dashboard signals

**Week 4: Refine**
- Analyze your paper trading results
- Identify which setups work best for YOU
- Make minor adjustments if needed
- Prepare for live trading

**Month 2+: Execute**
- Start with small position sizes (25%)
- Gradually increase as you prove consistency
- Keep detailed records
- Review and improve monthly

---

## 💡 QUICK TIPS

1. **Best Trading Times (Stocks):**
   - 9:30-11:00 AM EST (market open)
   - 2:00-3:30 PM EST (afternoon session)

2. **Best Crypto Times:**
   - High volatility during US trading hours
   - Watch for overnight gaps/moves

3. **Risk Management:**
   - Never risk more than 2% per trade
   - Use the strategy's built-in stops
   - Don't fight the market

4. **Quality > Quantity:**
   - 3 great trades/week > 20 mediocre trades

5. **When in Doubt, Stay Out:**
   - If setup doesn't look perfect, skip it

---

## 📱 SETTING UP ALERTS

1. Right-click on chart → "Add Alert"
2. Condition: Select "SwingFlow v0.1"
3. Choose alert type (any/once per bar)
4. Set up notifications (email/SMS/app)
5. Never miss a signal!

---

## 🔍 TROUBLESHOOTING

**Problem: No signals appearing**
- Solution: Disable optional filters (RSI, Stochastic, Bollinger)
- Lower volume multiplier to 1.0x
- Check if EMA stack filter is too restrictive

**Problem: Too many losing trades**
- Solution: Enable EMA Stack filter
- Increase Risk:Reward to 4:1
- Add RSI or Stochastic filter
- Only trade with volume multiplier 1.5x+

**Problem: Getting stopped out too often**
- Solution: Increase ATR multiplier to 2.0x
- Use "Recent Low" stop method instead
- Trade less volatile instruments

---

## 📚 WHAT'S INCLUDED

1. **swingflow_v0.1.pine** - The main strategy script
2. **SWINGFLOW_README.md** - Complete user guide (this file)
3. **ADVANCED_CUSTOMIZATION.md** - Expert customization guide

---

## ⚖️ IMPORTANT DISCLAIMER

- This is educational software (Version 0.1 - Initial Release)
- Trading involves substantial risk
- Past performance ≠ future results
- Always use proper risk management
- Never trade with money you can't afford to lose
- Consider consulting a financial advisor

---

## 🎯 YOUR FIRST WEEK CHECKLIST

**Day 1:**
- [ ] Install strategy on TradingView
- [ ] Load it on a chart (recommended: SPY on 5min)
- [ ] Familiarize yourself with the dashboard
- [ ] Watch the strategy in replay mode

**Day 2-3:**
- [ ] Run backtests on 3+ different instruments
- [ ] Study the entry signals (green triangles)
- [ ] Note when EMA stack is bullish vs bearish
- [ ] Observe VWAP pullback patterns

**Day 4-5:**
- [ ] Set up recommended beginner settings
- [ ] Start paper trading
- [ ] Take 2-3 trades following signals
- [ ] Screenshot and journal each trade

**Day 6-7:**
- [ ] Review your paper trades
- [ ] Calculate win rate and avg R:R
- [ ] Identify what felt comfortable
- [ ] Plan for week 2

---

## 🚀 READY TO START?

1. Install the strategy
2. Use beginner settings (above)
3. Paper trade for 30 days minimum
4. Journal every trade
5. Review weekly
6. Scale up when profitable

**Remember:** This is version 0.1 - we're just getting started! Your feedback and experience will help shape future versions.

---

**Good luck and trade smart! 📈**

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)
