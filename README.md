# MGMT 490 Project 2 - Path B Sentiment Analyzer

This app is a stock sentiment analyzer that takes one or more tickers, pulls recent market news, scores sentiment, evaluates source reliability, and visualizes sentiment trends over time.

It is designed to align with **MGMT 49000 Project 2 (Path B)** rubric requirements.

## Features

- Accepts one or more ticker symbols (comma separated, e.g., `AAPL,MSFT,NVDA`)
- Retrieves recent, up-to-date headlines for each ticker using `yfinance`
- Scores sentiment for each headline using VADER (`positive`, `negative`, `neutral`)
- Displays ticker-level and headline-level sentiment outputs
- Lets user adjust:
  - Time window (`7` to `90` days)
  - Source type filter (`wire`, `major_financial_media`, `analysis_platform`, `aggregator`, `other`)
  - Reliability threshold (`1` to `5`)
  - Source weighting scheme (slider per source type)
- Shows visualizations:
  - Weighted sentiment trend over time
  - Source type distribution
- Includes source reliability scoring and short interpretation of what sentiment may imply for the ticker

## Rubric Mapping (Path B)

1. **Accept ticker input** -> sidebar ticker input field  
2. **Retrieve recent text data** -> Yahoo Finance headlines via `yfinance.Ticker().news`  
3. **Analyze sentiment** -> VADER sentiment score + class label  
4. **Output score/trend/signal** -> average sentiment, weighted average, signal text  
5. **Adjust time window** -> days slider (7-90)  
6. **Filter/weight by source type** -> source filter + source weights  
7. **Display individual sources with scores** -> headline-level data table with source and scores  
8. **Show sentiment-over-time visualization** -> Plotly line chart  

## Reliability Method (Transparent Rules)

Reliability is scored as a simple rule-based proxy using source-type categories:

- `wire` -> 5
- `major_financial_media` -> 4
- `analysis_platform` -> 3
- `aggregator` -> 2
- `other` -> 2

This is intentionally interpretable and easy to explain in your video.

## How to Run
Installation & Setup
Follow these steps to run the Sentiment Analyzer locally:
1. Prerequisites
 - Ensure you have Python 3.9+ installed on your machine.
 - You will also need a stable internet connection for the initial library installation and for pulling live market news.
2. Clone the Repository
 - Open your terminal and run the following commands to download the project and navigate into the directory:
git clone https://github.com/jason-laatz/Project-2-sentiment.git
cd Project-2-sentiment
3. Install Dependencies
   It is recommended to use a virtual environment.
   Install the required libraries (Streamlit, Pandas, Plotly, yfinance, and VADER) using the provided requirements file:
   pip install -r requirements.txt
4. Launch the ApplicationStart the Streamlit server to open the app in your default web browser:
   streamlit run app.py


## Project Documentation (Submission-Ready)

- `AI_DISCLOSURE.md` - required AI usage disclosure and reflection
- `DRIVER_DOCUMENTATION.md` - D/R/I/V/E/R process log for this project
- `sample_news.json` - fallback dataset used when live Yahoo Finance news is unavailable

These files are included so you can submit a repo that already has required documentation artifacts.


## Limitations

- News-only sentiment can miss context from earnings calls/filings/social channels.
- Headline sentiment may not reflect full article nuance.
- Source reliability scoring is heuristic, not a ground-truth credibility model.
- Sentiment should be combined with fundamentals, valuation, and risk analysis.

## AI Usage Disclosure

- AI tools used: Cursor + LLM assistant
- Tasks AI assisted with: code scaffolding, UI structuring, refactoring, documentation drafting
- What you validated independently: ticker retrieval behavior, score interpretation, filter behavior, chart correctness



