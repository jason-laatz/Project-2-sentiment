# MGMT 490 - Project 2 (Path B) Sentiment Analyzer

A Streamlit application that analyzes stock-related headlines, scores sentiment, and shows how time horizon and source-quality assumptions affect interpretation.

This project was built for **MGMT 49000: AI Finance Application** and aligns with **Project 2, Path B** requirements.

## Overview

The app allows users to:

- Input one or more ticker symbols (for example: `AAPL MSFT NVDA TSLA`)
- Retrieve recent headline text (live via `yfinance`, with fallback sample data)
- Score each headline using VADER sentiment (`positive`, `neutral`, `negative`)
- View per-headline source, reliability score, and interpretation
- Adjust analysis assumptions:
  - Time window (`7` to `90` days)
  - Source-type filter
  - Minimum reliability threshold
  - Source weighting sliders
- View sentiment visualizations:
  - Weighted sentiment trend over time
  - Source-type distribution

## Quick Start

### 1) Clone the repository

```bash
git clone https://github.com/jason-laatz/Project-2-sentiment.git
cd Project-2-sentiment
```

### 2) Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 3) Run the app

```bash
python -m streamlit run app.py
```

Open the local URL shown in your terminal (typically `http://localhost:8501`).

## Troubleshooting

- **`python` not recognized**: use `py` instead of `python`.
- **Port already in use**: run `python -m streamlit run app.py --server.port 8502`.
- **No live headlines returned**: the app automatically uses `sample_news.json` fallback data.
- **Package import errors**: rerun `python -m pip install -r requirements.txt`.

## Path B Rubric Mapping

1. Ticker input -> sidebar ticker input
2. Text data retrieval -> Yahoo Finance headlines (`yfinance`) + fallback sample data
3. Sentiment analysis -> VADER score and label
4. Output score/trend/signal -> KPI metrics and ticker-level bias
5. Adjustable time window -> `7` to `90` day slider
6. Source filter/weight controls -> source filter + weight sliders
7. Individual source-level scores -> headline table
8. Sentiment-over-time visualization -> Plotly trend chart

## Reliability Framework

Source reliability is modeled using transparent rule-based categories:

- `wire` -> 5
- `major_financial_media` -> 4
- `analysis_platform` -> 3
- `aggregator` -> 2
- `other` -> 2

This framework is intentionally simple and explainable for academic use.

## Repository Structure

- `app.py` - main Streamlit app
- `requirements.txt` - dependencies
- `sample_news.json` - fallback headline dataset used for reproducible demos
- `AI_DISCLOSURE.md` - AI usage disclosure and reflection
- `DRIVER_DOCUMENTATION.md` - D/R/I/V/E/R workflow documentation

## Limitations

- Headline sentiment does not fully capture article-level nuance.
- Source reliability scoring is heuristic, not a ground-truth credibility model.
- Sentiment should be used as a supplementary signal alongside fundamentals and valuation.

