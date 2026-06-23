# OpenLift

[![Python](https://img.shields.io/badge/python-3.9--3.12-blue)](pyproject.toml)
[![License](https://img.shields.io/badge/license-MIT-black)](LICENSE)

OpenLift is an open-source incrementality platform for marketing teams. It helps you design geo-lift tests, match control markets, estimate Bayesian counterfactual lift, and turn the result into a decision: scale, hold, cut, or retest.

It is built for the questions attribution dashboards cannot answer cleanly:

- Did this campaign create incremental revenue or conversions?
- Which markets should be used as test and control geos?
- Was the experiment strong enough to trust?
- What should the next experiment be?
- How should spend change if the result is positive, weak, or negative?

## What OpenLift Does

- **Geo-lift measurement**: Bayesian synthetic control with posterior lift estimates and credible intervals.
- **Experiment design**: geo matching, holdout recommendations, power analysis, MDE, and duration planning.
- **Decision output**: evidence tier, limitations, recommended next action, and business impact summary.
- **Economics**: incremental CAC, ROAS, profit, budget scenarios, and payback period curves.
- **Creative intelligence**: analyzes creative-level lift from campaign or creative performance data.
- **Next experiment planner**: recommends the next geo, channel, duration, MDE, and expected lift range.
- **Scorecard memory**: stores local experiment history and summarizes cumulative evidence over time.
- **Reporting**: generates Markdown and HTML experiment reports.
- **Connectors**: CSV, Google Sheets, Google Ads, and Meta Ads connector interfaces.

## Install

Python 3.10 or 3.11 is recommended.

```bash
git clone https://github.com/daramolaworks-create/openlift.git
cd openlift
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Poetry is also supported:

```bash
poetry install
```

## Run The App

```bash
streamlit run app.py
```

The Streamlit app includes:

- Experiment Runner
- Geo Matcher
- Power Analysis
- Multi-Cell testing
- Creative Lift
- Next Experiment
- Scorecard

## Expected Data

At minimum, OpenLift needs long-format geo time-series data:

| column | description | example |
| --- | --- | --- |
| `date` | daily or weekly timestamp | `2026-01-01` |
| `geo` | market, region, city, or country | `London` |
| `outcome` | KPI to measure | `revenue`, `orders`, `conversions` |

Recommended optional columns:

| column | description |
| --- | --- |
| `spend` | media spend or other input metric |
| `treatment` | test/control flag |
| `period` | pre/post flag |
| `channel` | marketing channel |
| `creative_id` | creative or asset identifier |

## Quick UI Walkthrough

1. Launch the app with `streamlit run app.py`.
2. Upload a CSV or connect a supported data source.
3. Map the date, geo, outcome, and optional spend columns.
4. Use Geo Matcher to choose a test market and control markets.
5. Run the experiment.
6. Review posterior lift, evidence strength, economics, budget recommendation, and next action.
7. Save the result to the Scorecard for cumulative evidence tracking.

## CLI Usage

```bash
openlift init
openlift run examples/geo_lift_basic/experiment.yaml --out results.json
openlift report results.json
```

## Example Notebook

A runnable example is available at:

[examples/notebooks/01_geo_lift_demo.ipynb](examples/notebooks/01_geo_lift_demo.ipynb)

## Documentation

- [Methodology](docs/methodology.md)
- [Assumptions](docs/assumptions.md)
- [Theory](docs/theory.md)
- [Beta onboarding](docs/beta_onboarding.md)

## Project Status

OpenLift is in active product development. The core measurement, design, diagnostics, economics, reporting, scorecard, and creative-lift workflows are implemented. Some connector paths require real platform credentials, and production deployment hardening is still expected before use in sensitive commercial workflows.

## License

MIT.
