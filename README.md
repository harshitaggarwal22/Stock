# Market Muse — Stock Price Predictor

An aesthetic, dependency-free AIML project that trains a ridge-regression price forecaster directly in the browser.

## Run locally

From this folder, run:

```powershell
node server.js
```

Open `http://localhost:8000`.

## Deployment

The repository includes a GitHub Pages deployment workflow. In GitHub, open **Settings → Pages** and select **GitHub Actions** as the deployment source. Every push to `main` then deploys the site to:

`https://harshitaggarwal22.github.io/Stock/`

## Model details

- Feature engineering: latest close, 5/14-day SMA, RSI(14), 5-day momentum and realized volatility
- Standardization and L2-regularized linear regression trained with gradient descent
- The last 20% of feature rows is held out for RMSE, MAE and R² evaluation
- Forecast is generated recursively over the selected horizon with an uncertainty band based on holdout error

The included ticker selections are reproducible classroom datasets so the app works without an API key. Use the CSV upload to run the same pipeline on actual historical data. CSV files must include `Date` and `Close` columns and at least 50 rows.

## Pages

- `index.html` — Forecast dashboard and interactive price projection
- `lab.html` — Model benchmark and regression comparison workspace
- `data.html` — Local CSV quality checks and schema review
- `project.html` — Portfolio case study, methodology, and copyable resume description

> This is an educational project and does not provide investment advice.
