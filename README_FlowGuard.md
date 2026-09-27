# FlowGuard — Depot Turnaround & Demurrage Prevention

A production-oriented system built for the Inuka Hackathon (Stage 3, KPC PLC domain) that predicts customs/clearance delays at fuel depots and escalates bottlenecks before oil marketing companies incur contractual overnight-stay (demurrage) penalties.

## The Problem

Rerouting trucks between depots isn't actually viable — oil marketing companies (OMCs) hold contractually allocated storage at specific depots under their Transport and Storage Agreements. The real bottleneck is depot clearance time, not inter-depot routing, so the fix has to happen at the clearance step itself.

## What It Does

- Predicts customs/clearance delays before they happen, using ML inference (scikit-learn/XGBoost) on the live request path.
- Automates document pre-validation to catch issues before they stall a truck at the gantry.
- Escalates bottlenecks early, with an OR-Tools optimization solver handling batch/route scheduling decisions.
- Four dashboards for four audiences: Depot Operations (floor staff), OMC Clearance Center (dispatch), Autonomous Control Dashboard (system health/model performance), and an Executive Control Plane (KES saved in demurrage, throughput %).

## Architecture

- **Frontend:** Next.js
- **Backend:** FastAPI (Python), with pytest coverage
- **Database:** Postgres
- **Deployment:** Render, with GitHub Actions CI/CD

This project deliberately upgrades an earlier analytics prototype ("brain") into something that *acts* — wrapping the predictive models in production-grade APIs and an event-driven architecture rather than just surfacing alerts on a dashboard.

## Why It Matters

The team's own data (from an earlier project stage) showed that the wait between weighbridge and bay assignment — not loading time itself — was the largest driver of demurrage cost. FlowGuard targets that specific gap directly, with a quantified ROI case for KPC and Em-Tech executive leadership.
