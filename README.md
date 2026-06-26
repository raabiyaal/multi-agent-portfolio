# Multi-Agent ETF Portfolio Generator

A multi-agent LLM pipeline that builds personalized ETF portfolios from real market data. Three specialized AI agents work sequentially; a market analyst, a risk assessor, and a portfolio constructor - each passing their output to the next to produce a final, investor-tailored allocation.

Built as a demonstration of agentic AI design applied to a real financial problem.

## The Problem

Generic investment advice ignores who the investor actually is. A 28-year-old software engineer and a 60-year-old approaching retirement should not hold the same portfolio. This pipeline personalizes recommendations by combining live market data with structured investor profiles, routing both through a chain of AI agents with distinct roles.

## How It Works

**Step 1 — Data Collection**
Pulls 2 years of daily price data for 43 ETFs across 11 sectors using `yfinance`. Computes key performance metrics per ETF including annualized return, volatility, Sharpe ratio, Sortino ratio, and max drawdown. Also fetches recent news headlines per ETF to surface sentiment signals.

**Step 2 — Investor Profiling**
Accepts a structured investor profile: age, risk tolerance, investment horizon, financial goals, income stability, and existing holdings. Four test profiles are included ranging from an aggressive 28-year-old to a conservative near-retiree.

**Step 3 — Market Analyst Agent**
Analyzes the ETF metrics table to identify top and bottom performers, sector-level trends, and risk-return tradeoffs. Produces a structured market analysis report that feeds into the next agent.

**Step 4 — Risk Assessment Agent**
Takes the investor profile and outputs a risk classification and target asset allocation (e.g. 85% equities / 10% bonds / 5% alternatives), with a plain-language explanation tailored to that investor's situation.

**Step 5 — Portfolio Construction Agent**
Synthesizes the market analysis and risk assessment alongside the full ETF universe to produce a final portfolio allocation in JSON format, with each ticker assigned a weight that sums to 100%.

## Sample Output

For an aggressive 28-year-old with a 30-year horizon, the pipeline recommended a growth-heavy tech and equity allocation (XLK, QQQ, SMH, IYW) with minimal bond exposure. For a conservative 60-year-old focused on capital preservation, it shifted toward bond ETFs (BND, SGOV, BNDX) and stable income vehicles.

## Tech Stack

- Python
- OpenAI API (GPT-4.1-mini)
- yfinance
- pandas, numpy
- matplotlib, seaborn

## Setup

1. Clone the repo
2. Install dependencies
```bash
pip install openai yfinance pandas numpy matplotlib seaborn python-dotenv
```
3. Add your OpenAI API key to a `.env` file

4. Run the notebook
