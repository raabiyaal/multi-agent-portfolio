# Multi Agent Portfolio

A multi-agent LLM pipeline that generates personalized ETF investment portfolios based on individual investor profiles. Three specialized AI agents collaborate — a market analyst, a risk assessor, and a portfolio constructor — to analyze real market data and produce tailored recommendations.

## How It Works

1. **Data Collection** — Pulls 2 years of historical price data for 43 ETFs across 11 sectors using `yfinance`, computes performance metrics (Sharpe ratio, volatility, max drawdown, etc.), and fetches recent news headlines per ETF
2. **User Profiling** — Accepts investor profiles with age, risk tolerance, investment horizon, goals, and interests
3. **Market Analyst Agent** — Analyzes ETF metrics to identify sector trends and top/bottom performers
4. **Risk Assessment Agent** — Evaluates the investor profile and recommends a target asset allocation
5. **Portfolio Construction Agent** — Synthesizes the above to produce a final ETF allocation summing to 100%

## Sectors Covered

Technology, Healthcare, Energy, Financials, Real Estate, Consumer, Industrials, Bonds, International, ESG/Sustainable, Artificial Intelligence

## Tech Stack

- Python
- OpenAI API (GPT-4.1)
- yfinance
- pandas, numpy
- matplotlib, seaborn

## Setup

1. Clone the repo
2. Install dependencies
```bash
