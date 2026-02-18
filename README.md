# Pandas & NumPy Workshop — Signal and Backtesting using Vectors

**Rutgers Quant Finance Club**

A hands-on workshop where you build a **Mean-Reversion trading strategy** from scratch using Pandas for signal generation and pure NumPy for high-performance vectorized backtesting.

---

## What You'll Learn

| Concept | Tools |
|---|---|
| Fetching & cleaning market data | `yfinance`, `pandas` |
| Rolling statistics & Z-Score signals | `pandas.rolling()` |
| Trade signal generation (Long / Short / Flat) | `numpy.where()` |
| Avoiding look-ahead bias with `.shift()` | `pandas` |
| Vectorized backtesting with log returns | `numpy` |
| Sharpe ratio calculation | `numpy` |
| Equity curve visualization | `matplotlib` |

## Repository Structure

```
pandas_numpy_workshop/
├── workshop.ipynb            # Student worksheet (fill-in-the-blank exercises)
├── workshop_solution.ipynb   # Completed solution notebook
└── README.md
```

- **`workshop.ipynb`** — The main worksheet. Code cells contain scaffolded exercises with hints and comments guiding you to complete each step.
- **`workshop_solution.ipynb`** — The fully completed version for reference after attempting the workshop.

## Getting Started

### Prerequisites

- Python 3.10+
- Jupyter Notebook or JupyterLab

### Installation

```bash
# Clone the repo
git clone https://github.com/Rutgers-Quant-Finance-Club/pandas_numpy_workshop.git
cd pandas_numpy_workshop

# Install dependencies
pip install pandas numpy matplotlib yfinance jupyter
```

### Running the Workshop

```bash
jupyter notebook workshop.ipynb
```

### Or Open in GitHub Codespaces

No local setup needed — you can run everything in the browser:

1. Go to the [repository on GitHub](https://github.com/Rutgers-Quant-Finance-Club/pandas_numpy_workshop)
2. Click the green **Code** button → **Codespaces** tab → **Create codespace on main**
3. Once the environment loads, open `workshop.ipynb` and start coding

## Workshop Outline

### 1. Getting the Data
Pull 5 years of SPY closing prices from Yahoo Finance using `yfinance`.

### 2. Building Signals (Bollinger Bands / Z-Score)
Compute a rolling SMA and standard deviation, then calculate a **Z-Score** to measure how far the current price deviates from its mean.

### 3. Generating Trades
Use `np.where()` to create trade signals:
- **Long (+1)** when Z-Score < −2 (oversold)
- **Short (−1)** when Z-Score > 2 (overbought)
- **Flat (0)** otherwise

Shift signals forward by one day to avoid look-ahead bias.

### 4. Vectorized Backtesting
Extract data to raw NumPy arrays and compute:
- **Log returns** for the market
- **Strategy returns** = position × market returns
- **Cumulative returns** via `np.exp(np.cumsum(...))`
- **Annualized Sharpe Ratio**

### 5. Visualizing Results
Plot the strategy equity curve against a buy-and-hold SPY benchmark.

## Dependencies

| Package | Purpose |
|---|---|
| `pandas` | Data manipulation & rolling statistics |
| `numpy` | Vectorized math & backtesting |
| `matplotlib` | Plotting equity curves |
| `yfinance` | Fetching historical market data |

## License

This project is maintained by the [Rutgers Quant Finance Club](https://github.com/Rutgers-Quant-Finance-Club).
