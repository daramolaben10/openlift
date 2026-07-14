# OpenLift Product Roadmap

This roadmap captures practical next steps for OpenLift based on the current product surface: geo-lift measurement, experiment design, economics, creative lift, scorecard memory, reporting, and connector interfaces.

## Current Strengths

- Bayesian geo-lift measurement with posterior lift estimates and credible intervals.
- Experiment design support for geo matching, holdout recommendations, power analysis, MDE, and duration planning.
- Decision output that connects measurement to business action: scale, hold, cut, or retest.
- Economics layer for incremental CAC, ROAS, profit, budget scenarios, and payback curves.
- Reporting workflows for Markdown and HTML outputs.
- Connector interfaces for CSV, Google Sheets, Google Ads, and Meta Ads.

## Near-Term Priorities

1. Harden connector setup paths with clearer credential validation and failure messages.
2. Add a reproducible sample dataset that exercises the Streamlit app, CLI, and report generation path.
3. Expand regression coverage around geo matching, evidence-tier assignment, and economics calculations.
4. Add deployment notes for teams running OpenLift in shared analytics environments.
5. Document known limitations for low-volume geos, short test windows, noisy seasonality, and overlapping campaigns.

## Quality Checklist

Before a release, verify:

- `streamlit run app.py` starts successfully.
- The example notebook runs from a clean environment.
- `openlift init`, `openlift run`, and `openlift report` work with the example experiment file.
- Markdown and HTML reports render expected lift, uncertainty, economics, limitations, and next action.
- Connector interfaces fail safely when credentials are missing or incomplete.

## Product Direction

OpenLift should stay opinionated: it is not just a measurement package, it is a decision system for incrementality. The best next improvements are the ones that reduce ambiguity for a marketing team deciding whether to scale, hold, cut, or retest.
