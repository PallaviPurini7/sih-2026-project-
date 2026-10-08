# Project name — AI-Powered MPLADS Fraud & Anomaly Detection

> Smart India Hackathon 2026 · Problem Statement SIH26102 · Software track
> Team [predators] ·

## Problem
 MPLADS fund monitoring is manual and fraud/delays are caught late. many projects will not be even go through by the audits aftermath of the delays . many projects will not be even verified , cause manually doing all these things is time taken .

## Our solution
so what we built is something that detects the anomalies and what kind are there like in funds misuse or in cost estimation or duplicate works or delayed projects .A web platform of portal that scores every MPLADS project for risk, flags anomalies,and routes alerts to the right stakeholders through a dashboard. the dashboard can be monitored all the time by  admin 
RR
we have a live score , where the project can be entered , and you can get the analysis in complete of that 

**Key features**
- Risk scoring (0-100) with severity levels for each project
- Detection of 6 anomaly types (including duplicate projects and delayed/stalled works)
- Alert lifecycle with role-based routing
  the dashboard features are : -projects
                               -funds
                               -anomalies
                               -transactions
                               -reports
                               -trend analysis
                               -test
                               -settings

## Architecture
[Diagram or short flow: data layer → ML detection engine → backend API → alerts → dashboard]

## Tech stack
- **Frontend / Backend:** [fill in]
- **ML:** Python, scikit-learn (Isolation Forest + rule engine)
- **Database:** SQL (projects, alerts, stakeholders tables)
- **Data:** data.gov.in MPLADS datasets


### My contribution (ML, data and documentation)
- **Data layer:** Built a synthetic dataset generator anchored on real
  data.gov.in MPLADS data (38-state expenditure, sector-wise cost share,
  state-wise unspent balances), then wrote a data dictionary and ran a
  data quality audit.
- **Detection engine:** Designed a hybrid system of a tuned rule engine,
  an Isolation Forest (contamination = 0.02) and a duplicate-project check
  (same MP + category, cost within 8%, start dates within 10 days).
  Reached 96% overall anomaly recall on the synthetic benchmark.
- **Bug fix:** Found that project status was assigned independent of
  elapsed time, which caused 1,078 false positives on the delay rule.
  Fixed it by making status time-coherent.
- **Integration:** Packaged the model as `get_risk_score.py` so the
  backend can call it directly.
- **Backend design:** Wrote and validated the SQL schema (projects,
  alerts, stakeholders).
- **Documentation:** Wrote the Technical Requirements Document and a
  17-issue Change Request & Alignment Report after reviewing the
  prototype against the problem statement.

## Results
| Metric | Value |
|---|---|
| Overall anomaly recall | 96% |
| Duplicate detection | 100% recall, 82.3% precision |
| Overall F1 | 0.64 |




## How to run
```bash
git clone [repo-url]
pip install -r requirements.txt
[commands]
```
