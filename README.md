## Overview

This repository contains two independent analyses of Bitcoin option markets. The project explores both model-based option pricing and arbitrage-based option strategies using real market data.

The first part applies the Heston–Nandi GARCH(1,1) option pricing framework to model time-varying volatility and derive theoretical option prices for Bitcoin options. The second part focuses on box spread construction and screening, a classical options strategy that can reveal potential violations of no-arbitrage pricing conditions.

Together, the analyses illustrate how quantitative methods can be used to study derivatives pricing, volatility dynamics, and potential arbitrage opportunities in cryptocurrency option markets.

## Repository Structure

Heston-Nandi GARCH(1,1)_BTC_option_pricing.ipynb

Box_Spread_construction.ipynb

Box_Spread_Screener.ipynb

BTC.csv (for Heston-Nandi GARCH(1,1)_BTC_option_pricing.ipynb)
Bitcoin-close_ts (for Heston-Nandi GARCH(1,1)_BTC_option_pricing.ipynb)

VIX_calls.csv (for Box_Spread_construction.ipynb)
VIX_puts.csv (for Box_Spread_construction.ipynb)

new_all_box_spreads.csv (for Box_Spread_Screener.ipynb)


The CSV files are included to ensure full reproducibility of the analysis.

## Notebook Descriptions

# Heston–Nandi GARCH Option Pricing

This notebook applies the Heston–Nandi GARCH(1,1) model to price Bitcoin options.

The workflow includes:

estimating conditional volatility using Bitcoin return data

calibrating the Heston–Nandi GARCH model

deriving theoretical option prices

comparing model-implied prices with observed market prices

The model captures time-varying volatility dynamics, which are particularly important in cryptocurrency markets.

Box Spread Construction

This notebook constructs box spread option strategies from available option contracts.

A box spread consists of:

long call with strike K1

short call with strike K2​

long put with strike K2

short put with strike K1

This combination replicates a risk-free payoff equal to K2−K1 at maturity.

The notebook identifies valid option combinations and computes the resulting spread payoffs.

Box Spread Screener

This notebook scans constructed box spreads to detect potential arbitrage opportunities.

The screener evaluates:

box spread pricing

implied returns

deviations from theoretical no-arbitrage values

It highlights spreads that may indicate mispricing in option markets.

Requirements

The notebooks rely on standard Python libraries:

numpy
pandas
scipy
matplotlib
statsmodels
