# Data Analytics Portfolio: Adedeji M. Olugboja

Five end-to-end analytics projects. Each starts from a business question and a simulated decision-maker, and each ships SQL, Python, tests, a written recommendation, a self-contained dashboard, and a Power BI star-schema export. Every repo rebuilds from scratch with `make all` in under five minutes, with no network access.

## Synthetic data statement

All data in these repositories is synthetic. Each repo generates its data with a seeded script (`src/generate_data.py`, seed 42), and none of it describes real patients, members, customers, providers, or organizations. The generators plant known effects and realistic defects (duplicates, late-arriving records, mixed codes and formats, broken hierarchies). Each README has a **Validation** section that compares what was planted with what the analysis recovered. Findings describe the simulated systems, not real-world facts.

## Projects

| # | Repository | Business question | Core skills |
|---|---|---|---|
| 1 | [health-plan-member-retention-cohorts](https://github.com/DOT2015/health-plan-member-retention-cohorts) | Which new Medicare Advantage members leave in their first 12 months, and which onboarding steps in the first 90 days are linked to staying? | Cohort retention from enrollment spans, funnel analysis, Kaplan–Meier and Cox models with censoring, outreach staffing sizing |
| 2 | [appointment-reminder-ab-test-no-shows](https://github.com/DOT2015/appointment-reminder-ab-test-no-shows) | Does a two-way SMS reminder with one-tap rescheduling reduce no-shows and unfilled slots enough to justify rollout, and for which patients? | Experiment design and power, SRM detection, CUPED, guardrail metrics, segment effects with multiple-testing control, cost/benefit rollout decision |
| 3 | [claims-payment-integrity-outlier-detection](https://github.com/DOT2015/claims-payment-integrity-outlier-detection) | Which providers' billing patterns are unusual enough versus specialty peers to justify review, and which 25 belong in next quarter's queue? | Claims header/line modeling, case-mix adjustment, empirical Bayes shrinkage, robust z-scores, review-queue ROI |
| 4 | [contact-center-volume-forecast-staffing](https://github.com/DOT2015/contact-center-volume-forecast-staffing) | How many agents are needed per 30-minute interval over the next 13 weeks to answer 80% of calls in 60 seconds, and what does the February price notice add? | Time-series forecasting with rolling-origin backtests, event regressors, Erlang C staffing, hiring and overtime sizing |
| 5 | [saas-revenue-metrics-layer-data-quality](https://github.com/DOT2015/saas-revenue-metrics-layer-data-quality) | What is our true Net Revenue Retention, and why do Sales, Finance, and Product report three different numbers? | Governed metric definitions, reconciliation bridges, recursive SQL, bootstrap CIs, data-quality monitoring, Power BI semantic model |

## TL;DR findings (simulated scenarios)

**1. Member retention cohorts**
<!-- P1_TLDR -->

**2. Appointment-reminder A/B test**
<!-- P2_TLDR -->

**3. Claims payment integrity**
<!-- P3_TLDR -->

**4. Contact-center forecast and staffing**
<!-- P4_TLDR -->

**5. SaaS revenue metric layer and data quality**
- Governed 2025 NRR is 104.0% (bootstrap 95% CI 102.0–105.8%), with GRR 89.0% and logo churn 11.5%. Sales reports 112.3%, Finance 101.2%, and Product 98.6%. Step-by-step bridges explain every gap with no residual; for example, one-time setup fees booked as ARR add 3.1 pp to the Sales number.
- Without the April +7% Mid-tier price increase, NRR would be 100.6%, so about 86% of net retention above 100% comes from one price action.
- Segment NRR runs from Enterprise 118.0% to SMB 91.0%, a 27.0 pp gap (95% CI 22.2–31.7 pp).
- A daily data-quality monitor flagged both planted incidents (a duplicated invoice export and a frozen FX feed) on the first day. The volume check had one false-positive day in 30 months.

## Skills-to-project matrix

● = demonstrated, ●● = a central focus of the project.

| Skill | P1 Retention | P2 A/B test | P3 Payment integrity | P4 Forecast | P5 Metric layer |
|---|:---:|:---:|:---:|:---:|:---:|
| SQL: window functions, CTEs, gaps and islands | ●● | ● | ●● | ● | ●● |
| SQL: recursive CTEs / hierarchies | | | | | ●● |
| KPI and metric definition | ● | ● | | | ●● |
| Experimentation and causal care | ● | ●● | | | |
| Statistics with effect sizes and confidence intervals | ●● | ●● | ● | ● | ● |
| Survival analysis | ●● | | | | |
| Anomaly detection, shrinkage | | | ●● | | |
| Forecasting and capacity planning | | | | ●● | |
| Data-quality monitoring and testing (pytest) | ● | ● | ●● | ● | ●● |
| Sizing / cost-benefit | ● | ●● | ●● | ●● | ● |
| Power BI star schema and DAX | ● | ● | ● | ● | ●● |
| Python (pandas, NumPy) | ● | ● | ● | ● | ● |
| Interactive dashboards (Plotly, self-contained HTML) | ● | ● | ● | ● | ● |
| Healthcare domain | payer | provider | payer claims | — | — |

## Stack

SQL (DuckDB, written to port to PostgreSQL), Python (pandas, NumPy, SciPy, statsmodels, matplotlib, Plotly, pytest), Power BI (star-schema CSV exports and DAX measures documented in each repo), and Make.

## Contact

Adedeji M. Olugboja — linkedin.com/in/adedeji-olugboja
