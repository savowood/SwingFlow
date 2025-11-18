# SwingFlow v0.1.1 - Installation Guide

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

## 📦 PACKAGE CONTENTS

This package contains SwingFlow v0.1.1 for Thinkorswim with the following files:

### Essential Files:
- **swingflow_v0.1.1.thinkscript** - The strategy code (INSTALL THIS)
- **README.md** - Package overview and quick start
- **CHANGELOG.md** - Complete version history
- **INSTALL.md** - This file

### Documentation:
- **THINKSCRIPT_UPDATE_SUMMARY.md** - Technical documentation
- **QUICK_REFERENCE_CARD.md** - One-page cheat sheet
- **BEFORE_AFTER_COMPARISON.md** - v0.1 vs v0.1.1 comparison

---

## ⚡ QUICK INSTALL (5 MINUTES)

### Step 1: Open Thinkorswim
Launch your Thinkorswim platform and log in

### Step 2: Access Studies
1. Click "Studies" button (top toolbar)
2. Select "Edit Studies..."
3. Click "Create..." button at bottom

### Step 3: Paste Code
1. Delete all default code in editor
2. Open `swingflow_v0.1.1.thinkscript` file
3. Copy ENTIRE file contents (Ctrl+A, Ctrl+C)
4. Paste into Thinkorswim editor (Ctrl+V)
5. Click "OK"

### Step 4: Name and Save
1. Dialog appears: "Save Study Filter"
2. Name it: **"SwingFlow v0.1.1"**
3. Click "OK"

### Step 5: Add to Chart
1. Find "SwingFlow v0.1.1" in Studies list
2. Check the box next to it
3. Click "OK"
4. ✅ DONE! Strategy is now active

---

## 🔍 VERIFY INSTALLATION

After installation, you should see:

✅ **EMA Lines:** Blue (9), Orange (20), Red (180)
✅ **VWAP Line:** Magenta solid line
✅ **VWAP Bands:** Light gray and dark gray dashed lines (NEW in v0.1.1)
✅ **Top Labels:** EMA Stack, VWAP, MACD, Volume, FVG, R:R
✅ **Entry Signals:** Green arrows when conditions met
✅ **Price Bubbles:** Green bubble showing Entry/Stop/Target (NEW in v0.1.1)
✅ **Fair Value Gaps:** Green or red shaded areas when present (NEW in v0.1.1)

---

## ⚙️ FIRST TIME CONFIGURATION

### Recommended Settings for Beginners:

1. Right-click chart → "Edit Studies..."
2. Click gear icon next to "SwingFlow v0.1.1"
3. Configure these key parameters:

```
Trading Style: Swing
useEmaFilter: yes
vwapPullbackType: Touch
volumeMultiplier: 1.5

# New Features (v0.1.1)
showFairValueGaps: yes
showVwapStdDev: yes
fvgMinSize: 0.1
vwapStdDev1: 1.0
vwapStdDev2: 2.0

# Risk Management
riskRewardRatio: 3.0
stopLossType: ATR-Based
atrMultiplier: 2.0
```

4. Click "OK" to apply

---

## 📊 TEST YOUR INSTALLATION

### Day 1: Observation
- [ ] Chart loads with all indicators
- [ ] EMA lines visible and color-coded
- [ ] VWAP and bands displaying (NEW)
- [ ] Fair Value Gaps appear when present (NEW)
- [ ] Top labels showing status
- [ ] Entry signals generate (green arrows)
- [ ] Price bubbles appear at signals (NEW)

### Day 2-3: Understanding
- [ ] Read QUICK_REFERENCE_CARD.md
- [ ] Understand each indicator
- [ ] Study Fair Value Gaps (NEW feature)
- [ ] Learn VWAP bands interpretation (NEW feature)
- [ ] Identify high-quality setups

### Week 1: Paper Trading
- [ ] Switch to Paper Money mode
- [ ] Take 5-10 practice trades
- [ ] Use new FVG and VWAP band features
- [ ] Track results in journal
- [ ] Adjust settings if needed

---

## 🔄 UPGRADING FROM v0.1

If you have SwingFlow v0.1 installed:

### Option 1: Clean Install (Recommended)
1. Remove old version from chart
2. Follow "Quick Install" steps above
3. Re-configure your custom settings

### Option 2: Side-by-Side
1. Keep old version installed
2. Install v0.1.1 with different name: "SwingFlow v0.1.1"
3. Compare on same or different charts
4. Remove old version when satisfied

### Settings Migration:
- All v0.1 settings are compatible with v0.1.1
- New settings have sensible defaults (all enabled)
- No action required unless you want to customize

---

## 🎯 WHAT'S NEW TO CONFIGURE

### Fair Value Gap Settings:
```
showFairValueGaps = yes      # Toggle display
fvgMinSize = 0.1            # Minimum gap size (0.1%)
```

**Customization Tips:**
- Increase `fvgMinSize` to 0.2-0.3 for fewer, larger gaps
- Decrease to 0.05 for more sensitivity
- Toggle off if chart too busy

### VWAP Standard Deviation Settings:
```
showVwapStdDev = yes        # Toggle bands
vwapStdDev1 = 1.0          # First standard deviation
vwapStdDev2 = 2.0          # Second standard deviation
```

**Customization Tips:**
- Standard settings (1.0 and 2.0) work for most markets
- Increase for less sensitive bands in low volatility
- Decrease for more sensitive bands in high volatility

---

## 🐛 TROUBLESHOOTING

### "Script won't compile"
**Cause:** Incomplete code copy or syntax error
**Fix:**
1. Ensure you copied ENTIRE script
2. Delete any leftover default code
3. Check for extra characters at start/end
4. Try copying again from original file

### "No Fair Value Gaps showing"
**Cause:** Normal - gaps don't always exist
**Fix:**
1. Check `showFairValueGaps = yes`
2. Try 5-minute or higher timeframe
3. Look at volatile stocks (TSLA, NVDA, etc.)
4. Lower `fvgMinSize` to 0.05
5. Gaps are event-driven - be patient

### "VWAP bands not visible"
**Cause:** Setting disabled or low volatility
**Fix:**
1. Check `showVwapStdDev = yes`
2. Verify `showVwap = yes`
3. Bands may be tight in low volatility (normal)
4. Check line colors aren't same as background

### "No price bubbles at signals"
**Cause:** Setting disabled or no signals yet
**Fix:**
1. Check `showPriceLabels = yes`
2. Wait for entry signal (green arrow)
3. Bubbles only appear when signal triggers

### "Chart too cluttered"
**Solution:** Toggle off optional features:
```
showVwapStdDev = no        # Remove VWAP bands
showFairValueGaps = no     # Remove FVG shading
showBollingerBands = no    # Keep BB off
```

---

## 📱 MOBILE INSTALLATION

### Thinkorswim Mobile:
1. Open Thinkorswim mobile app
2. Go to Studies
3. Find "SwingFlow v0.1.1" (if installed on desktop)
4. Study syncs automatically
5. Add to mobile charts

**Note:** Study must be created on desktop first, then syncs to mobile.

---

## ✅ POST-INSTALLATION CHECKLIST

**Immediate (First 10 minutes):**
- [ ] Strategy installed and showing on chart
- [ ] All visual elements displaying correctly
- [ ] Top labels showing indicator status
- [ ] New features visible (FVG, VWAP bands)
- [ ] Alerts configured (optional)

**First Day:**
- [ ] Read QUICK_REFERENCE_CARD.md
- [ ] Understand new FVG feature
- [ ] Learn VWAP bands interpretation
- [ ] Observe signals in real-time

**First Week:**
- [ ] Read THINKSCRIPT_UPDATE_SUMMARY.md
- [ ] Paper trade 5-10 setups
- [ ] Test new features
- [ ] Adjust settings to preference
- [ ] Build confidence

**First Month:**
- [ ] 20+ paper trades completed
- [ ] Consistent profitability shown
- [ ] Trading plan documented
- [ ] Ready for live trading

---

## 🎓 NEXT STEPS

### Immediate (Today):
1. ✅ Install SwingFlow v0.1.1
2. ✅ Verify all features working
3. ✅ Read QUICK_REFERENCE_CARD.md

### This Week:
1. Read THINKSCRIPT_UPDATE_SUMMARY.md
2. Watch strategy on live charts
3. Study Fair Value Gap formations
4. Understand VWAP band behavior

### This Month:
1. Paper trade consistently
2. Journal every trade
3. Focus on A+ setups only
4. Master new features

### Month 2+:
1. Start live with small positions
2. Risk only 1% per trade
3. Scale up gradually
4. Continue improving

---

## 📚 DOCUMENTATION MAP

**Start Here:**
- README.md - Package overview
- INSTALL.md - This file
- QUICK_REFERENCE_CARD.md - Daily reference

**Deep Dive:**
- THINKSCRIPT_UPDATE_SUMMARY.md - Complete technical docs
- CHANGELOG.md - Version history
- BEFORE_AFTER_COMPARISON.md - v0.1 vs v0.1.1

**Original Documentation** (in full repository):
- SWINGFLOW_README.md - Complete strategy guide
- THINKORSWIM_GUIDE.md - Platform-specific guide
- PLATFORM_COMPARISON.md - Platform selection
- ADVANCED_CUSTOMIZATION.md - Expert modifications

---

## 📞 SUPPORT

**Installation Issues:**
- Review this file carefully
- Check Thinkorswim documentation
- TD Ameritrade support: 1-800-672-2098

**Strategy Questions:**
- Read THINKSCRIPT_UPDATE_SUMMARY.md
- Check QUICK_REFERENCE_CARD.md
- Review CHANGELOG.md for features

**Feature Requests:**
- See CHANGELOG.md for planned features
- Community feedback welcome

---

## 🎉 YOU'RE ALL SET!

Installation complete! You now have:
- ✅ SwingFlow v0.1.1 installed
- ✅ Fair Value Gap detection active
- ✅ VWAP Standard Deviation bands enabled
- ✅ Enhanced price labels working
- ✅ Complete documentation package

**Next:** Read QUICK_REFERENCE_CARD.md and start paper trading!

**Swing with the Flow!** 🕺📈

---

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

**Version:** 0.1.1  
**Release Date:** November 17, 2025  
**Platform:** Thinkorswim (ThinkScript)
