# KEMSA Supply Chain Intelligence Platform

An AI-powered decision-support platform for optimizing medical commodity distribution across Kenya's 47 counties — built to replace reactive, manual stock management with proactive forecasting and automated (human-approved) redistribution.

## The Problem

Public health facilities discover stockouts after the shelf is already empty. County-level payment risk is invisible until a county is already deep in debt. Surplus stock sits idle in one facility while another runs dry, because matching surplus to shortage is still a manual process.

## What It Does

- **Financial Risk Scorecard** — weighted scoring (40% days overdue, 35% debt amount, 25% payment history) ranks every county's payment risk, with a plain-language explanation attached to each score.
- **Stockout Forecasting** — recursive depletion forecasting across ~1,500 facility-commodity pairs, producing 30/60/90-day stockout dates with Critical / Warning / Watch / Healthy flags.
- **Redistribution Matching** — finds the nearest facility with surplus stock using real haversine distance (not a fixed placeholder radius), and proposes a transfer for human approval.
- **Four dashboards** — National, County, and Facility views, plus role- and scope-enforced access so a county user can't see another county's data.

## Proven on Real Data

Retrospective analysis of one quarter of real 2024 transfer data (1.16M-row historical dataset) shows **KES 49.2M** in commodity value across **85,115 recommended transfers** that proactive redistribution could have captured. Example: a real surplus-to-shortage match was found and approved end-to-end between two facilities 8.0 km apart.

## Architecture

- **Backend:** FastAPI (Python), connected to a SQLite analytics database with a proper star schema.
- **Frontend:** Next.js 14 (App Router, TypeScript, Tailwind), with server-side role/scope enforcement via middleware.
- **ML/Analytics:** feature-engineered stockout forecasting, weighted risk scoring, geographic distance matching.
- **Testing:** automated test suite covering all three backend modules (financial scoring, forecasting, redistribution) plus the request→approval workflow state machine.

## My Role

Modelling & ML Lead, working alongside a 4-person team, responsible for the financial risk scoring, stockout forecasting engine, and redistribution-matching logic, plus the National and County dashboard builds.
