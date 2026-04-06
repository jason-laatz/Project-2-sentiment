# DRIVER Documentation - Project 2 (Path B Sentiment Analyzer)

## D - Discover and Define

### Problem
Build an investment sentiment analyzer that accepts stock tickers and produces actionable sentiment context using recent text data.

### Project Requirements (Path B)

1. Accept one or more tickers
2. Retrieve recent news/social text
3. Analyze sentiment (positive/negative/neutral)
4. Output sentiment score/trend/signal
5. Adjustable time window
6. Source filter/weight controls
7. Display individual source items with scores
8. Sentiment-over-time visualization

### Constraints

- Network-level instability for live Yahoo Finance news endpoint in local environment
- Need reproducible app behavior for recording and grading

## R - Represent

### System Design

- Input layer: ticker parser + sidebar controls
- Data layer: live news fetch + local fallback dataset
- NLP layer: VADER sentiment scoring and label mapping
- Quality layer: source-type classification and reliability scoring
- Analytics layer: weighted sentiment aggregation and trend grouping
- Presentation layer: KPI cards, line chart, bar chart, headline table, ticker-level interpretation

### Key Data Objects

- `NewsItem` dataclass
- DataFrame columns for score, label, reliability, and interpretation

## I - Implement

### Features Implemented

- Streamlit app with ticker/time/source controls
- Sentiment scoring and class labels per headline
- Per-headline interpretation with catalyst-based logic
- Weighted sentiment signal
- Time-window filter and source/reliability filters
- Plotly trend and source-mix visualizations
- Fallback `sample_news.json` with multiple periods (7/30/90-day demos)
- Ticker fetch status panel and filter row counts for transparency

### Files

- `app.py`
- `requirements.txt`
- `sample_news.json`
- `README.md`

## V - Validate

### Functional Validation

- App starts and runs locally
- Dependency imports succeed
- Ticker parser accepts comma/space/semicolon formats
- Window/filter controls change displayed dataset
- Charts and table update from filtered data
- Syntax and lints checked during development

### Financial/Interpretation Validation

- Sentiment used as an auxiliary signal, not standalone recommendation
- Interpretation text restricted to observed headline/summary content and explicit heuristic rules

## E - Evolve

### Iterations Performed

- Improved ticker parsing and duplicate handling
- Added explicit run button and status table
- Added fallback dataset for robustness when live endpoint fails
- Expanded sample data across multiple dates to show time-window effects
- Refined interpretations from generic to catalyst-specific 1-2 sentence outputs
- Improved transparency with active date-range and row count feedback

### Next Improvements

- Add second live news API (key-based) for stronger production reliability
- Add sentiment confidence band and source-level uncertainty indicators
- Add export to CSV for analyst workflow integration

## R - Reflect

### What Worked Well

- Heuristic + sentiment blend is explainable and easy to defend in a project video
- UI controls align directly to rubric checklist items
- Fallback data strategy preserves demo quality under network/API issues

### What Was Challenging

- Live news endpoint reliability and inconsistent metadata fields
- Avoiding repetitive interpretation text across similar headlines

### Key Learning

Strong finance AI applications need both model output and process transparency. Controls, caveats, and validation signals are essential for credibility and grading outcomes.

