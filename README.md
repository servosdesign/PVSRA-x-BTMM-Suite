# PVSRA × BTMM Suite

![Indicator Preview](https://www.tradingview.com/x/mShofwzR/)

## Sources

* **Traders Reality PVSRA Library:** [https://www.tradingview.com/script/TradersReality/](https://www.tradingview.com/script/TradersReality/)
* **Steve Mauro - Beat the Market Maker (BTMM):** [https://beatthemarketmaker.com/](https://beatthemarketmaker.com/)

## Overview

**PVSRA × BTMM Suite** is a personal all-in-one overlay indicator that fuses the **Traders Reality PVSRA vector candle engine** with the structural price levels, session boxes, and range tools central to **Steve Mauro's Beat the Market Maker (BTMM)** methodology.

Rather than loading multiple separate indicators, this consolidates everything onto a single clean overlay: PVSRA candle coloring, EMA structure, market session High/Low boxes, key daily/weekly levels, ADR/AWR/AMR ranges, pivot points, M Levels, and psychological levels, all configurable from one settings panel.

## Why This Build

This is a **personal build** stripped to exactly what is needed for daily BTMM-style trading, nothing more.

* **PVSRA candle coloring** as the primary volume confirmation engine
* **BTMM session boxes** (Asia, EU Brinks, London, US Brinks, New York) with live High/Low tracking and range metrics
* **ADR, AWR, AMR** range levels calculated from the Traders Reality library, with 50% midpoints and optional metric labels
* **EMA structure** (5/13/50/200/800) for trend context
* **Pivot Points and M Levels** for intraday decision zones
* **Psychological levels** based on weekly Sydney/Tokyo session logic

Everything is wired to display only on relevant timeframes. Session boxes and range levels auto-hide on higher timeframes where they add no value.

## Core Features

### PVSRA Vector Candle Coloring

* **Vector candles:** volume >= 200% of 10-bar average, or candle where `spread × volume` is the highest of the last 10 bars
  * Bull bars: **Green** | Bear bars: **Red**
* **Semi-vector candles:** volume >= 150% of 10-bar average
  * Bull bars: **Blue** | Bear bars: **Violet**
* **Non-vector candles:** no volume anomaly detected
  * Bull bars: **Light Gray** | Bear bars: **Dark Gray**

### EMA Lines

* 5, 13, 50, 200, 800 period EMAs
* Individual toggle and color per EMA
* Right-edge rolling labels for each active line

### Market Session Boxes (BTMM)

Live High/Low boxes that expand each bar with optional session name labels and a session metric label at close:

* **Asia:** 21:00–05:00 UTC+0
* **EU Brinks:** 08:00–09:00 London time
* **London:** 08:00–17:00 London time
* **US Brinks:** 14:00–15:00 New York time
* **New York:** 14:30–18:00 New York time

Additional session options:
* Optional **mid-line** per session (Asia only by default) with configurable color and style
* Session **range metrics** label: Range in pips/ticks, currency value, or percent
* DST-aware London and New York timezones, auto-switching between GMT+0 and GMT+1
* Weekend session toggle for crypto and 24hr instruments

### Key Price Levels

* **Daily Open (DO):** line and label with extend option and historical stepline plot
* **Previous Day High / Low (PDH / PDL):** intraday only, with extend option
* **Previous Week High / Low (PWH / PWL):** up to daily timeframe, with extend option
* All levels support Dotted, Dashed, or Solid line styles and independent colors

### Average Daily / Weekly / Monthly Ranges

Three range families: ADR (14-day default), AWR (4-week default), AMR (6-month default). Each includes:

* High and Low lines from the Traders Reality `adrHiLo` calculation
* Optional **50% midpoint** lines
* Range measured from either the period's Open (static) or running High/Low (dynamic)
* **Metric label** showing the range value and a **3x multiplier** alongside it
* Range displayed as pips/ticks, currency value, or percent
* Extend lines option and configurable lookback length

### Time Separators

* Day and week vertical separator lines
* Day name labels (Mon/Tue/Wed/Thu/Fri) centred inside each regular trading hours session
* Configurable lookback window, line width, color, and style
* Auto-hides above configurable timeframe thresholds for both lines and labels independently

### Pivot Points and M Levels (Intraday Only)

* **Pivot Point (P):** classic daily pivot
* **Resistance and Support:** R1/R2/R3 and S1/S2/S3, each level set toggled independently
* **M Levels (M0–M5):** midpoints between pivot zones, Steve Mauro's BTMM intraday decision areas
* Independent colors for resistance vs support lines
* Extend option and optional labels per level

### Psychological Levels (Intraday Only)

* Weekly High/Low psychological levels via Sydney/Tokyo session logic (Traders Reality library)
* Supported timeframes: 1m, 3m, 5m, 15m, 30m, 1h
* Optional historical stepline plot
* Independent colors for High and Low

## Customization Options

**Chart Scaling**
* Scale help tooltip toggle

**Candle Colors**
* Vector Red, Green, Blue, Violet colors
* Non-vector Up/Down colors

**EMA Lines**
* Per-EMA show toggle and color for 5, 13, 50, 200, 800

**Daily Open**
* Show line/label, historical opens, color, extend option

**PDH/PDL + PWH/PWL**
* Show lines/labels, independent colors, Dotted/Dashed/Solid styles, extend options

**Time Separators**
* Day/week lines, day labels, colors, styles, widths, lookback (weeks), TF hide thresholds

**ADR / AWR / AMR**
* Show, 50% levels, metric type, lookback length, color, style, and extend per range family

**Market Sessions**
* Master toggle, session labels, weekend toggle, metric type (Range/Currency/Percent), TF metric hide threshold

**Session Configuration (per session)**
* Show/hide, custom name, box color, text color, session time, mid-line with color and style

**Pivot Points**
* Show pivot/labels, line color, label color, R1/R2/R3 and S1/S2/S3 toggles, line style, extend

**M Levels**
* Show M0–M5/labels, line color, label color, style, extend

**Psychological Levels**
* Show levels/labels/historical plot, High color, Low color

## Timeframe Behavior

* **All timeframes:** EMA lines
* **Intraday (1m–4h):** Session boxes, ADR, AWR, Time Separators
* **Intraday only:** Daily Open, PDH/PDL, Pivot Points, M Levels
* **Intraday + Daily:** PWH/PWL
* **Intraday 3min+:** AMR
* **1m, 3m, 5m, 15m, 30m, 1h only:** Psychological Levels

## Credits

* **Traders Reality Library** - PVSRA engine, ADR/AWR/AMR calculations, pivot drawing, psychological levels: [TradersReality/Traders_Reality_Lib](https://www.tradingview.com/script/TradersReality/)
* **Steve Mauro - Beat the Market Maker (BTMM)** - session box structure, M Levels, ADR/AWR/AMR range methodology, key level framework
* **Version:** Pine Script v6
