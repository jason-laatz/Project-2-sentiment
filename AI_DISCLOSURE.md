# AI Usage Disclosure and Reflection

## Tools Used

- Cursor IDE with LLM assistance
- Python ecosystem libraries (`streamlit`, `pandas`, `plotly`, `yfinance`, `vaderSentiment`)

## What AI Assisted With

- Scaffolding the Streamlit app structure and UI layout
- Implementing sentiment pipeline logic and source-reliability scoring
- Adding fallback sample data logic when live news endpoint fails
- Drafting documentation sections and rubric-aligned mapping
- Iterating on explanation text for per-headline interpretation output

## What I Verified Independently

- Application runs locally without crashing
- Ticker input parsing works with comma/space/semicolon formats
- Time-window control changes included headlines by date range
- Source filters and reliability threshold alter output rows as expected
- Sentiment scores and labels are generated for each headline
- Trend and source-mix visualizations render correctly
- Headline-level interpretation text aligns with visible article context

## Data Sources and Constraints

- Primary: Yahoo Finance headlines via `yfinance`
- Fallback: local `sample_news.json` dataset for reproducible demo when live endpoint fails in restricted network environments

## Reflection on AI Collaboration

AI was effective for rapidly building a functional prototype and structuring the app around rubric requirements. The main limitation was that generated logic can be too generic unless iteratively refined; this required manual validation and multiple revisions to improve interpretation specificity, date filtering behavior, and user-facing clarity.

## Academic Integrity Statement

All final submission materials were reviewed and validated by me. I can explain the financial assumptions, sentiment methodology, source-reliability approach, and implementation decisions in the application.

