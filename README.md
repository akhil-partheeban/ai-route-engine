# AI Route Optimization Decision System

<<<<<<< HEAD
# This project explores ML-driven routing decisions on real OpenStreetMap road networks.

## Overview
# - Built edge-level ML travel-time model
# - Compared ML vs baseline routing behavior
# - Logged routing experiments using SQL
# - Evaluated tradeoffs across time and distance

## Tools
# Python, SQL, OpenStreetMap, graph routing

## Goal
# Study when predictive routing meaningfully changes decisions vs heuristic baselines.
# AI-Driven Route Optimization Engine

An edge-level machine learning routing system built on OpenStreetMap road 
networks.

## Overview

This project models travel-time cost at the road-segment (edge) level and 
routes deliveries using predicted travel time instead of raw distance.

The system:

- Converts an OSM road network into a structured edge dataset
- Defines a baseline travel-time cost model using road length + speed 
assumptions
- Trains a regression model to estimate edge travel time from road 
attributes
- Injects predicted travel times back into the graph
- Routes paths using ML-predicted time as the optimization objective
- Logs routing runs and decisions into a DuckDB warehouse for analysis

---

## Architecture

Data Pull  
→ Edge-Level Feature Engineering  
→ Baseline Travel Time Modeling  
→ ML Travel-Time Model  
→ Graph Cost Injection  
→ Shortest Path Routing  
→ SQL Logging & Evaluation  

---

## Key Design Decisions

- **Edge-level modeling** instead of stop-to-stop to reflect real routing 
cost structure.
- Baseline time computed as `length / speed` with highway-class defaults.
- ML predicts travel time per edge, not total trip ETA.
- Routing objective minimizes predicted time, not distance.
- SQL logging used for auditability and reproducibility.

---

## Tech Stack

- Python
- OSMnx / NetworkX
- Scikit-learn
- DuckDB
- Pandas

---

## What This Demonstrates

- Graph-based routing logic
- Cost-function engineering
- ML integration into decision systems
- Operational tradeoff evaluation
- SQL-based experiment logging

---

## Status

Current version includes:

- Edge-level ML travel-time model
- Baseline vs ML routing comparison
- SQL logging of routing runs

Future improvements may include:
- Scenario testing
- Reliability metrics
- Larger-scale experiments
- Production-style packaging
