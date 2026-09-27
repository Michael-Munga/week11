# Depot Flow Ops

An ETL pipeline and analytics dashboard analyzing fuel depot throughput and turnaround time across 5 depots in Kenya, built for the Inuka Hackathon (Stage 1: Data Engineering).

**Live:** depot-flow-ops.onrender.com

## The Problem

Fuel depots were losing time to demurrage costs, but it wasn't clear where in the process the time was actually going — loading itself, or something upstream of it.

## What It Does

- Full ETL pipeline processing 5,530 raw depot records (5,500 after deduplication) across 5 depots: Kisumu, Nairobi, Mombasa, Eldoret, Nakuru.
- Data validation via Great Expectations to catch quality issues before they reach the dashboard.
- Interactive dashboard (FlowMaster) visualizing throughput and turnaround time by depot, in KSh throughout.

## Key Finding

The wait between weighbridge and bay assignment averaged **92–106 minutes** — well above the actual fuel loading time of **59 minutes**. The bottleneck was assignment delay, not loading capacity, which directly shaped the follow-on project (FlowGuard)'s focus on clearance-time prediction rather than physical throughput.

## Architecture

- **Frontend:** TanStack Start, Vite, React, Recharts
- **Database:** better-sqlite3
- **Data Quality:** Great Expectations
- **Deployment:** Render.com (`nitro: { preset: "node-server" }` was the key fix for a working Node deployment)
