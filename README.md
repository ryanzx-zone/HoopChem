# HoopChem 🏀

**NBA lineup synergy analytics engine — measuring player chemistry beyond box scores.**

Traditional stats like plus/minus and net rating are noisy and treat players as independent units. But basketball is a team sport — the same player can look elite in one lineup and invisible in another. HoopChem identifies which player combinations actually work and why.

## The Problem

Front offices need to answer questions that box scores can't:

- Which 5-man lineups outperform their expected rating?
- Who are the hidden "glue guys" that elevate teammates without scoring?
- Which star pairings hurt spacing or ball movement?
- Which bench units punch above their weight?
- How does lineup chemistry change against different opponents?

## What This Project Does

HoopChem processes NBA play-by-play data to:

1. **Track lineup stints** — Detect substitutions and track exactly which 5 players are on court at every moment
2. **Calculate lineup metrics** — Points, possessions, offensive/defensive rating per lineup combination
3. **Model synergy** — Compare actual lineup performance vs. expected (based on individual player stats)
4. **Surface insights** — Identify over/under-performing lineups and player pairings

## Architecture

```
nba_api → Python/Pandas → PostgreSQL → Power BI
              ↓
         PySpark (scale)
              ↓
         MongoDB (graph storage)
```

| Tool | Purpose |
|------|---------|
| **nba_api** | Pull official NBA play-by-play and game data |
| **Python/Pandas** | Lineup stint detection, metric calculations |
| **PostgreSQL** | Structured storage for analytics queries |
| **PySpark** | Process full historical seasons at scale |
| **MongoDB** | Store player-pair synergy as graph relationships |
| **Power BI** | Dashboards for lineup performance and chemistry maps |

## Key Metrics

- **Lineup Net Rating** — Points scored minus points allowed per 100 possessions
- **Expected Net Rating** — Predicted performance based on individual player ratings
- **Synergy Score** — Actual minus expected (positive = chemistry boost)
- **Player Lift** — How much a player improves teammates' efficiency when on court together

## Project Structure

```
hoopchem/
├── notebooks/           # Exploration and analysis
├── src/
│   ├── ingestion/       # Pull data from nba_api
│   ├── processing/      # Lineup stint detection
│   └── analytics/       # Synergy calculations
├── sql/                 # Database schemas
├── data/                # Raw and processed data (not committed)
└── docs/                # Architecture diagrams
```

## Getting Started

```bash
# Clone the repo
git clone https://github.com/yourusername/hoopchem.git
cd hoopchem

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Start exploring
jupyter notebook notebooks/01_explore_playbyplay.ipynb
```

## Data Source

This project uses [nba_api](https://github.com/swar/nba_api), a Python client for NBA.com's API. All data is pulled directly from official NBA sources.

**Note:** Be respectful of rate limits when pulling data. The ingestion scripts include appropriate delays.

## Sample Insights

*Coming soon — screenshots of dashboards and example findings*

## Roadmap

- [x] Project structure and data modeling
- [ ] Lineup stint detection from play-by-play
- [ ] Basic lineup metrics (net rating, possessions)
- [ ] PostgreSQL pipeline
- [ ] Expected vs actual lineup performance
- [ ] Player-pair synergy graph
- [ ] Power BI dashboards
- [ ] PySpark for historical backfill

## Why I Built This

This is a portfolio project demonstrating end-to-end data engineering skills:

- **Data modeling** — Designing schemas for complex relationships
- **ETL pipelines** — Ingesting, transforming, and loading real-world data
- **SQL** — Analytics queries and aggregations
- **Python** — Data processing and business logic
- **Domain expertise** — Translating basketball questions into technical solutions

## License

MIT License — see [LICENSE](LICENSE) for details.

---

Built with 🏀 and ☕
