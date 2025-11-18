# SwingFlow ThinkScript - Quick Reference Card
## New Features Added

---

## 🎯 WHAT'S NEW

### 1. Label Fix ✅
- Entry, Stop, and Target prices now display correctly
- Shows as green bubble below entry candle
- Appears when long signal triggers

### 2. Fair Value Gaps (FVG) ✅
- **Green shading** = Bullish FVG (support zone)
- **Red shading** = Bearish FVG (resistance zone)
- Default: ON
- Adjustable minimum gap size

### 3. VWAP Standard Deviation Bands ✅
- **1σ bands** = Light gray dashed (inner)
- **2σ bands** = Dark gray dashed (outer)
- Default: 1.0σ and 2.0σ
- Fully customizable

---

## 📊 VISUAL GUIDE

```
Chart Layout:

High
 ↑
 |  ═══ VWAP 2σ Upper (dark gray dash)
 |  ─── VWAP 1σ Upper (light gray dash)
 |  ███ VWAP Line (magenta solid)
 |  ─── VWAP 1σ Lower (light gray dash)
 |  ═══ VWAP 2σ Lower (dark gray dash)
 ↓
Low

░░░ = Bullish FVG (green shaded area)
▓▓▓ = Bearish FVG (red shaded area)
⬆ = Long entry signal (green arrow)
💬 = Price bubble (Entry/Stop/Target)
```

---

## ⚙️ NEW INPUT SETTINGS

### Fair Value Gap Settings:
```
showFairValueGaps = yes     [ON by default]
fvgMinSize = 0.1           [0.1% minimum gap]
```

### VWAP StdDev Settings:
```
showVwapStdDev = yes       [ON by default]
vwapStdDev1 = 1.0         [1st deviation]
vwapStdDev2 = 2.0         [2nd deviation]
```

---

## 🎯 TRADING STRATEGIES

### Strategy 1: FVG Bounce Play
1. Bullish FVG forms (green area)
2. Price pulls back to FVG zone
3. Look for long signal
4. Enter with stop below FVG
5. Target: VWAP or R:R target

### Strategy 2: VWAP Mean Reversion
1. Price hits 2σ lower band
2. Wait for reversal signal
3. Enter long at VWAP or 1σ
4. Target: VWAP or 1σ upper
5. Stop: Below 2σ

### Strategy 3: Combined Setup
1. Bullish FVG + Price at 1σ lower
2. SwingFlow green arrow appears
3. All indicators confirmed
4. Strong volume present
5. ENTER LONG (highest probability)

---

## 🔔 NEW ALERTS

1. **Long Entry:** "SwingFlow: LONG Entry Signal!"
2. **Bullish FVG:** "Bullish Fair Value Gap Detected!"
3. **Bearish FVG:** "Bearish Fair Value Gap Detected!"

---

## 📍 NEW LABEL

Top bar now shows:
```
FVG: Bullish ⬆   [Green]
FVG: Bearish ⬇   [Red]
FVG: None        [Gray]
```

---

## 💡 QUICK TIPS

### Fair Value Gaps:
- ✅ Bigger gaps = more significant
- ✅ Price often returns to fill gaps
- ✅ Green gaps = support zones
- ✅ Red gaps = resistance zones

### VWAP Bands:
- ✅ 1σ = normal volatility range
- ✅ 2σ = extended moves
- ✅ Beyond 2σ = extreme (reversal likely)
- ✅ Use for position sizing

### Combining Both:
- ✅ FVG + VWAP band = powerful combo
- ✅ Wait for confirmation signal
- ✅ Best entries at intersection zones

---

## 🚀 BEST PRACTICES

**DO:**
- ✅ Wait for confirmation signals
- ✅ Use FVGs as support/resistance
- ✅ Check distance from VWAP bands
- ✅ Combine with volume
- ✅ Paper trade new features first

**DON'T:**
- ❌ Trade every FVG
- ❌ Ignore VWAP bands
- ❌ Enter at extreme 2σ levels without confirmation
- ❌ Skip risk management
- ❌ Overtrade

---

## 🎨 CUSTOMIZATION IDEAS

### Conservative (Fewer FVGs):
```
fvgMinSize = 0.3
```

### Aggressive (More FVGs):
```
fvgMinSize = 0.05
```

### Wider VWAP Bands:
```
vwapStdDev1 = 1.5
vwapStdDev2 = 3.0
```

### Tighter VWAP Bands:
```
vwapStdDev1 = 0.75
vwapStdDev2 = 1.5
```

---

## 📋 INSTALLATION CHECKLIST

- [ ] Open Thinkorswim
- [ ] Studies → Edit Studies → Create
- [ ] Copy updated script
- [ ] Save as "SwingFlow v0.1 Updated"
- [ ] Add to chart
- [ ] Verify FVGs visible (green/red areas)
- [ ] Verify VWAP bands visible (gray dashes)
- [ ] Test signals on paper account
- [ ] Adjust settings to preference
- [ ] Ready to trade!

---

## 🆘 TROUBLESHOOTING

**No FVGs showing?**
→ Check showFairValueGaps = yes
→ Try lower fvgMinSize (0.05)
→ Use 5min+ timeframe

**VWAP bands too tight?**
→ Normal during low volatility
→ Will expand when market moves

**Too many FVGs?**
→ Increase fvgMinSize (0.2 or 0.3)
→ Focus on larger timeframes

**Bubbles not showing?**
→ Wait for long signal (green arrow)
→ Check showPriceLabels = yes

---

## 📞 SUPPORT

**Documentation:**
- [THINKSCRIPT_UPDATE_SUMMARY.md] - Full details
- [THINKORSWIM_GUIDE.md] - General guide
- [SWINGFLOW_README.md] - Strategy overview

**Developer:**
☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

**Version:** 0.1 Updated  
**Date:** November 17, 2025  
**Platform:** Thinkorswim (ThinkScript)

**Swing with the Flow!** 🕺📈
