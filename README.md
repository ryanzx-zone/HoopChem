# NBA Lineup Synergy Analytics

A front-office style analytics system for measuring NBA lineup chemistry and player synergy.

## Project Goal

Identify which player combinations perform better or worse than expected, find hidden "glue" players, and analyze how lineup chemistry changes across contexts.

## Key Questions This System Answers

1. Which 5-man lineups outperform their expected rating?
2. Which players consistently improve teammate efficiency?
3. Which star pairings hurt spacing or ball movement?
4. Which bench lineups punch above their weight?
5. How does lineup performance change by opponent/game state?

## Tech Stack

- **Data Source**: nba_api (Python)
- **Processing**: Python, Pandas, PySpark (later)
- **Storage**: PostgreSQL (analytics), MongoDB (graph relationships)
- **Visualization**: Power BI
- **Cloud**: AWS (stretch goal)

## Project Structure

```
nba-lineup-synergy/
├── notebooks/           # Exploration and learning
├── src/
│   ├── ingestion/       # Data pulling from nba_api
│   ├── processing/      # Lineup stint detection, metrics
│   ├── models/          # Data models and schemas
│   └── analytics/       # Synergy calculations
├── data/
│   ├── raw/             # Raw API responses
│   └── processed/       # Cleaned lineup data
├── sql/                 # Database schemas
├── tests/               # Unit tests
└── docs/                # Architecture diagrams, notes
```

## Getting Started

```bash
# Create virtual environment
python -m venv venv
venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Start with the exploration notebook
jupyter notebook notebooks/01_explore_playbyplay.ipynb
```

## Learning Path

1. **Week 1**: Understand play-by-play data structure
2. **Week 2**: Build lineup stint detection logic
3. **Week 3**: Calculate basic lineup metrics
4. **Week 4**: Add database layer and synergy metrics
5. **Week 5+**: Graph model, streaming, dashboards

## Why This Project?

Traditional plus/minus is noisy and ignores context. This system:
- Accounts for lineup combinations, not just individuals
- Adjusts for opponent strength and game state
- Models synergy as a graph problem
- Uses real data engineering patterns (not just pandas scripts)
