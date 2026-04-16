# PVSRA × BTMM Suite

![Indicator Preview](https://www.tradingview.com/x/cXIONU3b/)

## Sources

* **Traders Reality PVSRA Library:** [https://www.tradingview.com/script/8zgJTM9u-Traders-Reality-Lib/](https://www.tradingview.com/script/8zgJTM9u-Traders-Reality-Lib/)
* **Steve Mauro - Beat the Market Maker (BTMM):** [https://beatthemarketmaker.com/](https://beatthemarketmaker.com/)

---

## Overview

**Vector Candles × Market Maker Cycle** is a personal all-in-one overlay indicator that fuses the **Traders Reality PVSRA vector candle engine** with the structural price levels, session boxes, and range tools central to **Steve Mauro's Beat the Market Maker (BTMM)** methodology.

Rather than loading multiple separate indicators, this consolidates everything onto a single clean overlay: PVSRA candle coloring, EMA structure, market session High/Low boxes, key daily/weekly levels, ADR/AWR/AMR ranges, pivot points, M Levels, and psychological levels, all configurable from one settings panel.

---

## Why This Build

This is a **personal build**, stripped to exactly what is needed for daily BTMM-style trading and nothing more.

* **PVSRA candle coloring** as the primary volume confirmation engine
* **BTMM session boxes** (Asia, EU Brinks, London, US Brinks, New York) with live High/Low tracking and range metrics
* **ADR, AWR, AMR** range levels calculated from the Traders Reality library, with 50% midpoints and optional metric labels
* **EMA structure** (5/13/50/200/800) for trend context
* **Pivot Points and M Levels** for intraday decision zones
* **Psychological levels** based on weekly Sydney/Tokyo session logic

Everything is wired to display only on relevant timeframes. Session boxes and range levels auto-hide on higher timeframes where they add no value.

---

## Core Features

### PVSRA Vector Candle Coloring

* **Vector candles:** volume >= 200% of 10-bar average, or candle where `spread × volume` is the highest of the last 10 bars.
  * Bull bars: **Green** | Bear bars: **Red**
* **Semi-vector candles:** volume >= 150% of 10-bar average.
  * Bull bars: **Blue** | Bear bars: **Violet**
* **Non-vector candles:** no volume anomaly detected.
  * Bull bars: **Light Gray** | Bear bars: **Dark Gray**

### EMA Lines

* 5, 13, 50, 200, 800 period EMAs
* Individual toggle and color per EMA
* Right-edge rolling labels for each active line

### Market Session Boxes (BTMM)

Live High/Low boxes that expand each bar with optional session name labels and a session metric label at close:

* **Asia:** 17:00 to 01:00 New York time
* **EU Brinks:** 08:00 to 09:00 London time
* **London:** 08:00 to 17:00 London time
* **US Brinks:** 09:00 to 10:00 New York time
* **New York:** 09:30 to 13:00 New York time

Additional session options:
* Optional **High/Low lines** and **mid-line** on the Asia session, each with independent color and style. Mid-line defaults to orange, high/low to gray. Lines extend to the end of the current day, matching the Daily Open and ADR lines.
* Session **range metrics** label showing range in pips/ticks, currency value, or percent.
* IANA-timezone based (`America/New_York`, `Europe/London`), so DST switches automatically year-round.
* Weekend session toggle for crypto and 24hr instruments.

### Key Price Levels

* **Daily Open (DO):** line + label, extend option, historical stepline plot
* **Previous Day High / Low (PDH / PDL):** intraday only, extend option
* **Previous Week High / Low (PWH / PWL):** up to daily timeframe, extend option
* All levels support Dotted / Dashed / Solid line styles and independent colors

### Average Daily / Weekly / Monthly Ranges

Three range families (ADR with 14-day default, AWR with 4-week default, AMR with 6-month default), each with:

* High and Low lines from the Traders Reality `adrHiLo` calculation
* Optional **50% midpoint** lines
* Range measured from either the period's Open (static) or running High/Low (dynamic)
* **Metric label** showing the range value and a **3× multiplier** alongside it
* Range displayed as pips/ticks, currency value, or percent
* Extend lines option and configurable lookback length

### Time Separators

* Day and week vertical separator lines
* Day name labels (Mon/Tue/Wed/Thu/Fri) centred on each day, using the NYSE session midpoint for stocks and the midpoint of the 24h daily candle for forex, crypto, and other instruments
* Configurable lookback window, line width, color, and style
* Auto-hides above configurable timeframe thresholds for both lines and labels independently

### Pivot Points and M Levels (Intraday Only)

* **Pivot Point (P):** classic daily pivot
* **Resistance and Support:** R1/R2/R3 and S1/S2/S3, each level set toggled independently
* **M Levels (M0 through M5):** midpoints between pivot zones, Steve Mauro's BTMM intraday decision areas
* Independent colors for resistance vs support lines
* Extend option and optional labels per level

### Psychological Levels (Intraday Only)

* Weekly High/Low psychological levels via Sydney/Tokyo session logic (Traders Reality library)
* Supported timeframes: 1m, 3m, 5m, 15m, 30m, 1h
* Optional historical stepline plot
* Independent colors for High and Low

---

## Customization Options

**Chart Scaling**
* Scale help tooltip toggle

**Candle Colors**
* Vector Red, Green, Blue, Violet colors
* Non-vector Up/Down colors

**EMA Lines**
* Per-EMA show toggle and color for 5, 13, 50, 200, 800

**Daily Open**
* Show line/label, historical opens, color, Dotted/Dashed/Solid line style, extend option

**PDH/PDL + PWH/PWL**
* Show lines/labels, independent colors, Dotted/Dashed/Solid styles, extend options

**Time Separators**
* Day/week lines, day labels, colors, styles, widths, lookback (weeks), TF hide thresholds

**ADR / AWR / AMR**
* Show, 50% levels, metric type, lookback length, color, style, and extend (per range family)

**Market Sessions**
* Master toggle, session labels, weekend toggle, metric type (Range/Currency/Percent), TF metric hide threshold

**Session Configuration (per session)**
* Show/hide, custom name, box color, text color, session time
* Asia session adds: High/Low lines (color + style) and mid-line (color + style)

**Pivot Points**
* Show pivot/labels, line color, label color, R1/R2/R3 and S1/S2/S3 toggles, line style, extend

**M Levels**
* Show M0 through M5 (and labels), line color, label color, style, extend

**Psychological Levels**
* Show levels/labels/historical plot, High color, Low color

---

## Timeframe Behavior

* **All timeframes:** EMA lines
* **Intraday (1m to 4h):** Session boxes, ADR, AWR, Time Separators
* **Intraday only:** Daily Open, PDH/PDL, Pivot Points, M Levels
* **Intraday + Daily:** PWH/PWL
* **Intraday 3min and above:** AMR
* **1m, 3m, 5m, 15m, 30m, 1h only:** Psychological Levels

---

## Credits

* **Traders Reality Library** - PVSRA engine, ADR/AWR/AMR calculations, pivot drawing, psychological levels: [TradersReality/Traders_Reality_Lib](https://www.tradingview.com/script/8zgJTM9u-Traders-Reality-Lib/)
* **Steve Mauro - Beat the Market Maker (BTMM)** - session box structure, M Levels, ADR/AWR/AMR range methodology, key level framework
* **Version:** Pine Script v6
