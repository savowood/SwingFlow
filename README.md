# SwingFlow v0.1.2

## Overview

These improved versions of SwingFlow address the visual clutter and usability issues present in the default settings. The scripts now provide clean, actionable swing levels right out of the box.

## Key Improvements

### 1. **Better Default Settings**
- **Swing Length increased to 25** (from ~9-14): Shows only significant swing points
- **Touch Sensitivity set to 0.5**: Balanced between strict and lenient
- **Minimum 2 touches required**: Filters noise, shows confirmed levels
- **Maximum 5 levels displayed**: Prevents chart clutter
- **Background coloring OFF by default**: Keeps chart clean and readable

### 2. **Enhanced Visualization**
- **Simplified color scheme**: Green (support) and Red (resistance) only
- **Line styles indicate strength**: Solid lines = 3+ touches, Dashed = 2 touches
- **Cleaner labels**: Show touch count only, not overwhelming information
- **Automatic level cleanup**: Old/broken levels removed automatically

### 3. **Smarter Level Management**
- **Swing strength filtering**: Only displays swings that have proven significance
- **Automatic prioritization**: Shows most-touched levels when too many exist
- **Breakout detection**: Removes levels after clear price breakthrough
- **Inactivity removal**: Cleans up levels not touched recently (50 bars default)

## Installation

### TradingView (Pine Script)

1. Open TradingView and navigate to the Pine Editor
2. Click "New" to create a new indicator
3. Copy the entire contents of `swingflow_tradingview_improved.pine`
4. Paste into the Pine Editor
5. Click "Save" and give it a name (e.g., "SwingFlow v0.1.2")
6. Click "Add to Chart"

### Thinkorswim (ThinkScript)

1. Open Thinkorswim
2. Go to Charts > Studies > Edit Studies
3. Click "Create" at the bottom
4. Copy the entire contents of `swingflow_thinkorswim_improved.txt`
5. Paste into the thinkScript editor
6. Click "OK" and give it a name (e.g., "SwingFlow v0.1.2")
7. The study will automatically be added to your chart

## Usage Guide

### Default Settings Explained

| Setting | Default | Purpose |
|---------|---------|---------|
| Swing Detection Length | 25 | Higher = fewer, major swings only |
| Minimum Swing Strength | 0.3 | Filters weak swing points |
| Touch Sensitivity | 0.5 | Balanced touch detection |
| Minimum Touches | 2 | Shows confirmed levels only |
| Maximum Swing Levels | 5 | Limits chart clutter |
| Show Background | OFF | Keeps chart clean |

### Visual Indicators

**Line Colors:**
- 🟢 **Green** = Support level (swing low)
- 🔴 **Red** = Resistance level (swing high)

**Line Styles:**
- **Solid line** = Strong level (3+ touches)
- **Dashed line** = Developing level (2 touches)
- **Thicker lines** = More touches = Stronger level

**Labels:**
- Show number of touches (e.g., "3 touches")
- Yellow highlight (TOS) = Price currently near level

### Customization Tips

**For Day Trading (More Levels):**
```
Swing Detection Length: 15-20
Maximum Swing Levels: 7-8
Minimum Touches: 2
```

**For Swing Trading (Fewer, Stronger Levels):**
```
Swing Detection Length: 30-40
Maximum Swing Levels: 3-4
Minimum Touches: 3-4
```

**For Volatile Assets (Crypto, Small Caps):**
```
Touch Sensitivity: 0.7-1.0
Swing Detection Length: 20-25
```

**For Low Volatility Assets (Blue Chips, Bonds):**
```
Touch Sensitivity: 0.3-0.4
Swing Detection Length: 25-30
```

## Best Practices

### 1. **Start with Defaults**
- Don't adjust settings immediately
- Let the indicator run for at least 20-30 bars
- Evaluate if levels make sense for your timeframe

### 2. **Timeframe Recommendations**
- **5-minute charts**: Best for scalping, use lower swing length (15-20)
- **15-minute to 1-hour**: Optimal for default settings
- **Daily charts**: Increase swing length to 30-40 for major levels

### 3. **Trading Strategies**

**Support/Resistance Bounces:**
1. Wait for price to touch a level (2+ touches minimum)
2. Look for reversal candlestick patterns
3. Confirm with volume increase
4. Enter on next bar with stop below/above level

**Breakout Trading:**
1. Identify strong level (3+ touches, solid line)
2. Wait for decisive break with high volume
3. Enter on retest of broken level
4. Stop loss on opposite side of level

**Range Trading:**
1. Identify clear support and resistance
2. Trade between levels when range-bound
3. Exit positions near opposing level
4. Watch for breakout signals

### 4. **Combining with Other Indicators**

**Volume:**
- High volume at level = Stronger significance
- Volume increase on breakout = Confirms move

**RSI/MACD:**
- Divergence at swing level = Higher probability reversal
- Momentum confirmation improves success rate

**Moving Averages:**
- Swing levels near major MAs = Added significance
- Use MAs for trend context

## Troubleshooting

### Issue: No levels showing up
**Solution:** 
- Reduce "Minimum Touches" to 1
- Lower "Minimum Swing Strength" to 0.2
- Decrease "Swing Detection Length" to 15-20

### Issue: Too many levels displayed
**Solution:**
- Reduce "Maximum Swing Levels" to 3
- Increase "Minimum Touches" to 3-4
- Increase "Swing Detection Length" to 30-35

### Issue: Levels appear in wrong places
**Solution:**
- Adjust "Touch Sensitivity" (try 0.3 for strict, 0.7 for lenient)
- Ensure adequate bar history loaded (100+ bars minimum)
- Check timeframe is appropriate for settings

### Issue: Levels don't update
**Solution:**
- Refresh chart (TradingView: F5, TOS: Restart)
- Verify "Show Inactive Swings" is OFF for auto-cleanup
- Check "Bars Before Removing Swing" isn't too high

## Advanced Features

### Custom Alerts (TradingView)

The script includes built-in alert conditions:
1. Right-click chart > Add Alert
2. Select "SwingFlow v0.1.2"
3. Choose "SwingFlow Level Touch"
4. Set your notification preferences

### Background Coloring (Optional)

To enable subtle background zones:
1. Turn ON "Show Background Color"
2. Adjust "Background Transparency" to 95-98%
3. Green zone = Near support
4. Red zone = Near resistance

### Additional Levels (Thinkorswim)

The TOS script includes code for additional levels:
- Already enabled for levels 3-4
- Adjust "maxSwingLevels" parameter to show more
- Note: Too many levels can slow TOS performance

## Performance Notes

### TradingView
- Uses ~200-300 lines maximum
- Efficient on all timeframes
- No performance issues on standard charts

### Thinkorswim
- Optimized for TOS limitations
- Use 4 levels or fewer for best performance
- May lag slightly on tick charts with high volume

## Changelog

### v0.1.2 (Current)
- Fixed array bounds error (Index out of bounds bug)
- Added comprehensive safety checks for all array access
- Added bounds validation in touch detection loop
- Added array size checks in visualization section
- Added safety checks in background coloring and alerts
- Improved error handling throughout the script
- Increased default swing length from ~10 to 25
- Added minimum swing strength filter (0.3)
- Implemented maximum levels cap (5 default)
- Changed touch sensitivity from ~0.3 to 0.5
- Disabled background coloring by default
- Added automatic level cleanup
- Improved sorting algorithm
- Simplified color scheme to green/red only
- Enhanced label readability
- Added line style variation based on touch count
- Optimized performance

### v0.1.1 (Previous)
- Initial improved version
- Basic swing detection enhancements
- Added level filtering

### v0.1.0 (Original)
- Basic swing detection
- Multiple ATR periods
- Full rainbow color scheme
- No level filtering
- No automatic cleanup

## Support and Feedback

For issues, suggestions, or questions:
- Check the troubleshooting section first
- Review TradingView/TOS documentation for platform-specific issues
- Test different timeframes and settings combinations

## License

These scripts are provided as-is for personal trading use. Modify and adapt as needed for your trading strategy.

---

**Important Disclaimer:** These indicators are for educational and informational purposes only. Always use proper risk management and never trade with money you cannot afford to lose. Past performance of support/resistance levels does not guarantee future results.
