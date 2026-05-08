# Reproducing the data

All data comes from the FastF1 Python library.

## Setup

`pip install fastf1 pandas numpy matplotlib seaborn scikit-learn xgboost`

`brew install libomp # macOS only`

## Running the notebook

`jupyter notebook f1_tyre.ipynb`

The first execution of Section 1 ("Data Collection") downloads the data from the F1 live-timing servers and caches it locally to `fastf1_cache/`. Subsequent runs will read from the cache.
