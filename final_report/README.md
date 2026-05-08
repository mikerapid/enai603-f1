# 603 Racing Group — Final Submission

**Team:** Kevin Zong (115265318), Michael Obajemu (114202291)

## Files

- `f1_tyre.ipynb`: Main project notebook.
- `fastf1_cache/`: Local cache of raw F1 session data downloaded from the FastF1 live-timing API. The notebook reads from this cache. If missing, it will be regenerated.

## Reproducing the data

The raw data is too big to push to our Github repo so we're including these instructions on how to grab the data.

All data comes from the [FastF1 Python library](https://docs.fastf1.dev/).

### Setup

```bash
pip install fastf1 pandas numpy matplotlib seaborn scikit-learn xgboost
brew install libomp   # macOS only — required by xgboost
```

### Running the notebook

```bash
jupyter notebook f1_tyre.ipynb
```

The first execution of Section 1 ("Data Collection") will read from the included `fastf1_cache/` directory if present, or download ~50 MB of session data from the F1 live-timing servers (5–10 minutes) if the cache is missing. Subsequent runs read from the cache and start instantly.

The notebook pulls both full F1 seasons (2024 and 2025). This gives us 48 race sessions covering 24 unique circuits. The exact rounds are listed in the `ROUNDS` array in Section 1.
