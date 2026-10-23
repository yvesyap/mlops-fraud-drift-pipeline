# End to End MLOps Pipeline for Transaction Fraud Detection

Automated drift monitoring, retraining, promotion and rollback for a fraud detection model.

**Status:** planning complete, FYP 1 in progress. This is a Final Year Project at Multimedia University.

## Problem

A deployed fraud model loses accuracy over time because fraud patterns keep changing. Most work focuses on building the model. This project focuses on keeping it reliable after deployment.

## What it will do

1. **Ingest and validate:** replay transactions in time order and quarantine invalid records.
2. **Train and serve:** train a baseline gradient boosting model, version it, and serve it through a containerised API.
3. **Monitor drift:** watch input and prediction drift over daily windows.
4. **Retrain and promote:** retrain on drift, and promote a candidate only if it is clearly better.
5. **Roll back:** return to the last known good version if the live model degrades.
6. **Evaluate:** compare the automated pipeline against a model that is never updated.

## Roadmap

- [ ] FYP 1, Objective 1: data replay and validation
- [ ] FYP 1, Objective 2: baseline model, registry and serving API
- [ ] FYP 2, Objective 3: drift monitoring
- [ ] FYP 2, Objective 4: automated retraining and promotion
- [ ] FYP 2, Objective 5: automated rollback
- [ ] FYP 2, Objective 6: evaluation against a static baseline

Numeric targets are provisional and will be calibrated after the first prototype.

## Planned tech stack

Python, XGBoost, LightGBM, MLflow, FastAPI, Docker Compose, GitHub Actions, pytest. Orchestration tool to be decided after a short spike.

## Dataset

[IEEE-CIS Fraud Detection](https://www.kaggle.com/c/ieee-fraud-detection) (Kaggle). The data is not redistributed here. A download script and checksums will be provided.

## Scope

In scope: the pipeline logic, injected drift scenarios, simulated label delay and a reproducible Docker setup.
Out of scope: improving model accuracy, live banking integration, production scale, and e-wallet scam detection (future work).

## Repository structure (planned)

```
src/        pipeline code
tests/      unit and integration tests
configs/    thresholds and parameters
docs/       architecture and design decisions
```

## Running it

Instructions will be added as each component is built.
