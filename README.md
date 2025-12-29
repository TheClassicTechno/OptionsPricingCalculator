# Options-Optimizer
note: moved project over from my old github account
made in Dec 2024

Developed advanced options pricing calculator using financial mathematical models i.e. Black-Scholes, Monte Carlo. I also integrated option pricing, volatility analysis, rate adjustments to deliver calculations for both European call and put options.

 To help users calculate theoretical prices and sensitivities (Greeks) for financial options using established quantitative models. 

## Features

- **Option Price Calculation:**  
  Computes European call and put option prices using the Black-Scholes formula.

- **Monte Carlo Simulation:**  
  Estimates option prices through stochastic modeling and variance reduction techniques.

- **Greeks Calculation:**  
  Offers Delta, Gamma, Vega, Theta, and Rho, helping analyze risk and sensitivity.

- **Live Market Data Integration:**  
  Utilizes the `yfinance` API to fetch real-time stock prices, ensuring calculations use up-to-date information.

## Technologies Used

- **Python** as the core language for computational finance and web development.
- **Flask** powers the web server interface.
- **NumPy** and **SciPy** for numerical and statistical computations.
- **gunicorn** for production-ready web hosting.
- **yfinance** for retrieving live stock market data.

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/TheClassicTechno/OptionsPricingCalculator.git
   cd OptionsPricingCalculator
   ```
2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Start the web server locally using Flask or deploy via gunicorn:
```bash
# For local development
flask run

# For production
gunicorn finanapp:app
```

By default, the application will be served at `http://localhost:5000/`.

## Folder Structure

- `finanapp.py` - Main Flask application serving the web interface.
- `formula.py` - Contains all numerical functions for option and Greeks calculations.
- `static/` - Static files for the web UI.
- `templates/` - HTML templates for the web interface.
- `requirements.txt` - Python package dependencies.
- `Procfile` - Process configuration for cloud deployment (e.g., Heroku).

## Models Implemented

- **Black-Scholes Model** for European options pricing.
- **Monte Carlo Simulation** for both call and put options.
- **Custom Greek Calculators** for sensitivity analysis.

## Example: Black-Scholes Call Option Calculation

```python
from formula import black_scholes_call

# Example parameters
S = 150  # Current stock price
K = 160  # Strike price
T = 0.5  # Time to expiry (years)
r = 0.01 # Risk-free interest rate
sigma = 0.2 # Volatility

call_price = black_scholes_call(S, K, T, r, sigma)
print(f"Call Option Price: {call_price}")
```

