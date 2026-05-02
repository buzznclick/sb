# Ride Log

A static GitHub Pages site that charts mountain bike ride data over time — distance, elevation, gear shifts, BTC price, and AUD/CNY exchange rate on a single interactive multi-line chart.

## Live site

Hosted on GitHub Pages. Updates within ~2 minutes of any commit.

## What it tracks

| Column | Description |
|--------|-------------|
| Distance (km) | Ride distance from Garmin |
| Elevation (m) | Elevation gain |
| Gear Shifts | SRAM AXS RD shift count |
| BTC Price (USD) | Bitcoin price at time of ride |
| AUD/CNY Rate | Exchange rate at time of ride |

All five series share the same date axis with independent Y axes, so wildly different scales don't interfere with each other.

## Features

- Date range sliders to zoom into any window of rides
- Stat cards (totals / averages) that update to match the visible range
- Click any legend item to toggle a series on/off
- Points auto-hide when more than 50 rides are in view

## Adding a ride

1. Open `rides.csv` on GitHub and click the pencil edit icon
2. Append a row: `YYYY-MM-DD,dist,elev,gear,btc,fx`
3. Commit — the site updates automatically

Rides with no gear data (different bike, no AXS unit) use `gear=0` and are excluded from the chart. `btc` and `fx` can be `0` if unknown.

## Stack

- Vanilla HTML/CSS/JS — no build step, no dependencies to install
- [Chart.js 4.4.1](https://www.chartjs.org/) via cdnjs
- `rides.csv` is fetched at page load — the repo is also the CMS
