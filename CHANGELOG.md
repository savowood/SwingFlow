# SwingFlow - Changelog

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

## [0.1.1] - 2025-11-17

### 🎉 New Features

#### Fair Value Gap Detection
- **Bullish FVG Detection**: Automatically identifies upward price gaps (green shading)
  - Indicates strong momentum and potential support zones
  - Price often returns to "fill" these gaps
  - Visual green shading between gap boundaries
  
- **Bearish FVG Detection**: Automatically identifies downward price gaps (red shading)
  - Indicates strong downward momentum and potential resistance
  - Price often returns to test these zones
  - Visual red shading between gap boundaries

- **Customizable Settings**:
  - `showFairValueGaps` - Toggle FVG display on/off (default: yes)
  - `fvgMinSize` - Minimum gap size as percentage (default: 0.1%)

- **New Alerts**:
  - "Bullish Fair Value Gap Detected!" when bullish FVG forms
  - "Bearish Fair Value Gap Detected!" when bearish FVG forms

- **Enhanced Top Bar**:
  - New "FVG" label showing current gap status
  - Shows "Bullish ⬆" (green), "Bearish ⬇" (red), or "None" (gray)

#### VWAP Standard Deviation Bands
- **Multi-Level Bands**: Two levels of standard deviation bands around VWAP
  - 1σ bands (light gray dashed lines) - Normal volatility range
  - 2σ bands (dark gray dashed lines) - Extreme zones
  
- **Visual Shading**: Light gray cloud shading between VWAP and 1σ bands for easy identification

- **Customizable Settings**:
  - `showVwapStdDev` - Toggle VWAP bands display (default: yes)
  - `vwapStdDev1` - First standard deviation multiplier (default: 1.0)
  - `vwapStdDev2` - Second standard deviation multiplier (default: 2.0)

- **Trading Benefits**:
  - Identify overbought/oversold levels relative to VWAP
  - Gauge pullback depth
  - Determine entry/exit zones
  - Similar to Bollinger Bands but based on institutional VWAP level

### 🔧 Fixes

#### Label Display Fix
- **Issue**: Entry, Stop, and Target prices not displaying properly in ThinkScript v0.1
- **Solution**: Implemented proper label display using `AddChartBubble`
- **Result**: Green price bubble now appears at entry signals showing:
  - Entry price
  - Stop loss price
  - Take profit target price
- **Toggle**: Can be disabled with `showPriceLabels = no`

### 📚 Documentation

#### New Documentation Files
- **CHANGELOG.md** (this file) - Complete version history
- **THINKSCRIPT_UPDATE_SUMMARY.md** - Technical documentation for v0.1.1
- **QUICK_REFERENCE_CARD.md** - One-page cheat sheet
- **BEFORE_AFTER_COMPARISON.md** - Visual comparison guide

#### Updated Documentation
- **THINKORSWIM_GUIDE.md** - Updated with v0.1.1 features
- **SWINGFLOW_README.md** - Updated version references
- **README.md** - Updated with v0.1.1 information

### 🎨 Visual Improvements

#### Chart Elements Added
- Green shaded areas (Bullish Fair Value Gaps)
- Red shaded areas (Bearish Fair Value Gaps)
- Light gray dashed lines (VWAP ±1σ)
- Dark gray dashed lines (VWAP ±2σ)
- Light gray cloud shading (VWAP bands)
- Green price bubbles (Entry/Stop/Target)

#### Top Bar Labels Enhanced
- Added FVG status indicator
- Color-coded for quick visual reference
- All existing labels preserved

### ⚙️ Configuration

#### New Input Parameters
```thinkscript
# Fair Value Gaps
input showFairValueGaps = yes;
input fvgMinSize = 0.1;

# VWAP Standard Deviation
input showVwapStdDev = yes;
input vwapStdDev1 = 1.0;
input vwapStdDev2 = 2.0;

# Price Labels
input showPriceLabels = yes;
```

All new features are **enabled by default** but can be toggled off individually.

### 🚀 Performance

- No performance impact - all calculations are efficient
- Chart remains responsive
- All features optional for minimal chart clutter

### 📊 Compatibility

- **Platform**: Thinkorswim (ThinkScript)
- **Backward Compatible**: All v0.1 settings and functionality preserved
- **Upgrade Path**: Simply replace old script with v0.1.1

### 🎯 Trading Enhancements

#### New Trading Strategies Enabled

**FVG Bounce Strategy**:
1. Wait for bullish FVG to form (green area)
2. Price pulls back to FVG zone
3. Enter long on SwingFlow signal
4. Stop below FVG, target based on R:R

**VWAP Band Mean Reversion**:
1. Price hits 2σ lower band (extreme)
2. Wait for reversal confirmation
3. Enter on SwingFlow signal
4. Target VWAP or 1σ upper band

**Combined Setup** (Highest Probability):
1. Bullish FVG present
2. Price at VWAP 1σ lower band
3. SwingFlow signal appears
4. All indicators confirmed
5. Enter with conviction

---

## [0.1.0] - 2025-11-16

### 🎉 Initial Release

#### Core Features
- **Multi-Style Trading**: Intraday, Swing, Medium-Term, Long-Term
- **EMA Stack Confirmation**: 9/20/180 EMA setup for trend identification
- **VWAP Pullback Detection**: Three modes (Touch, Cross, Within Range)
- **MACD Confirmation**: Momentum verification
- **Multiple Filters**: Optional RSI, Stochastic, Bollinger Bands
- **Volume Confirmation**: Adjustable volume multiplier
- **Price Action Recognition**: Bullish engulfing, hammer, bullish candle patterns

#### Risk Management
- **ATR-Based Stops**: Adaptive stop loss based on volatility
- **Percentage Stops**: Fixed percentage stop loss option
- **Recent Low Stops**: Structure-based stop placement
- **Customizable R:R**: Adjustable risk:reward ratio (default 3:1)
- **Multiple Stop Types**: Choose best fit for trading style

#### Visualization
- **EMA Lines**: Color-coded trend identification
- **VWAP Line**: Institutional support/resistance level
- **Entry Signals**: Green arrow indicators
- **Top Bar Labels**: Real-time indicator status
- **Clean Interface**: Professional chart display

#### Alerts
- Entry signal alerts
- Sound notifications
- Configurable alert types

#### Documentation
- Complete user guide (SWINGFLOW_README.md)
- Quick start guide (QUICK_START_GUIDE.md)
- Platform comparison (PLATFORM_COMPARISON.md)
- Thinkorswim-specific guide (THINKORSWIM_GUIDE.md)
- Advanced customization (ADVANCED_CUSTOMIZATION.md)
- Optimization guide (OPTIMIZATION_GUIDE.md)

#### Platform Support
- TradingView (Pine Script v5)
- Thinkorswim (ThinkScript)

---

## Version Numbering

SwingFlow follows semantic versioning:
- **Major.Minor.Patch** (e.g., 0.1.1)
  - **Major**: Breaking changes, major feature overhauls
  - **Minor**: New features, backward-compatible additions
  - **Patch**: Bug fixes, small improvements

---

## Upgrade Guide

### From v0.1 to v0.1.1 (Thinkorswim)

**Easy Upgrade Path:**

1. **Backup Current Settings** (optional):
   - Take screenshot of your input settings
   - Note any customizations

2. **Remove Old Version**:
   - Right-click chart → Edit Studies
   - Find "SwingFlow v0.1"
   - Click X to remove

3. **Install v0.1.1**:
   - Studies → Edit Studies → Create
   - Copy entire v0.1.1 script
   - Paste and save as "SwingFlow v0.1.1"
   - Add to chart

4. **Verify New Features**:
   - Check for VWAP bands (gray dashed lines)
   - Look for FVG shading (green/red areas)
   - Confirm price bubbles at signals
   - Review new FVG label in top bar

5. **Reconfigure** (if needed):
   - Re-enter any custom settings
   - Adjust new parameters:
     - `showFairValueGaps` (default: yes)
     - `showVwapStdDev` (default: yes)
     - `fvgMinSize` (default: 0.1)
     - `vwapStdDev1` (default: 1.0)
     - `vwapStdDev2` (default: 2.0)

**All original v0.1 functionality is preserved!**

---

## Known Issues

### v0.1.1
- None reported

### v0.1.0
- ✅ **Fixed in v0.1.1**: ThinkScript label display issue
  - Entry/Stop/Target prices not showing properly
  - Resolved with AddChartBubble implementation

---

## Planned Features

### v0.2.0 (Planned)
- Multi-timeframe confirmation
- Time-of-day filters
- Session-based VWAP (London, NY, Asian)
- Order block detection
- Enhanced pattern recognition

### v0.3.0 (Planned)
- FVG fill detection and alerts
- Automatic fibonacci levels on FVGs
- Liquidity zone visualization
- Smart Money Concepts integration
- Enhanced ICT methodology features

### v1.0.0 (Future)
- Machine learning optimization
- Market regime detection
- Advanced position sizing
- Multiple take-profit levels
- Full automation support
- Mobile app integration

---

## Contributing

Found a bug or have a feature request?

**Report Issues:**
- Describe the issue clearly
- Include Thinkorswim version
- Provide chart timeframe and symbol
- Screenshot if possible

**Suggest Features:**
- Explain the use case
- Describe expected behavior
- Note any similar implementations

---

## Support

**Documentation:**
- SWINGFLOW_README.md - Complete guide
- THINKORSWIM_GUIDE.md - Platform-specific guide
- QUICK_START_GUIDE.md - Fast setup
- CHANGELOG.md - This file

**Community:**
- TradingView community
- r/thinkscript subreddit
- TD Ameritrade forums

**Developer Support:**
☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

## License

SwingFlow is provided for personal trading use.

**Permitted:**
- ✅ Personal trading use
- ✅ Educational purposes
- ✅ Modification for personal use
- ✅ Sharing with attribution

**Not Permitted:**
- ❌ Commercial redistribution
- ❌ Selling as your own
- ❌ Removing attribution

---

## Acknowledgments

**Inspired by:**
- Ross Cameron (Warrior Trading) - VWAP and pullback strategies
- Joovier - Institutional trading concepts
- ICT (Inner Circle Trader) - Fair Value Gap methodology
- SMC (Smart Money Concepts) - Market structure analysis

**Built for:**
- Retail traders seeking institutional-level tools
- Systematic traders wanting proven strategies
- Part-time traders needing clear signals
- Anyone who wants to "Swing with the Flow"

---

**Thank you for using SwingFlow!**

**Swing with the Flow!** 🕺📈

**Support the developer:** ☕ [Buy me a Coffee](https://buymeacoffee.com/savowood)

---

**Last Updated:** November 17, 2025  
**Current Version:** 0.1.1  
**Platform:** Thinkorswim (ThinkScript)
