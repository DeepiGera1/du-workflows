# DU Dataform Curation Pipeline

This repository contains the **Workflow layer** for the Ducks Unlimited university chapters.

---

## Project Overview

The end-to-end solution is split into two parts:

1. **Ingestion Pipeline**
   - Built in Python
   - Fetches Ducks Unlimited university chapter data from the public API
   - Stores raw JSON in Google Cloud Storage (GCS)
   - Loads structured data into a BigQuery operational/raw table

2. **Curation Pipeline**
   - Built using **Dataform**/**dbt**
   - Reads from the BigQuery operational/raw dataset
   - Applies SQL-based transformations
   - Produces curated tables/views for downstream reporting and analysis

---

## Source Data

The source data comes from the Ducks Unlimited public API for university chapters.

Typical fields ingested include:

- `object_id`
- `chapter_id`
- `chapter_name`
- `city`
- `state`
- `longitude`
- `latitude`
- `ingestion_time`

These fields are first loaded into the BigQuery operational table and then transformed in Dataform.

---

## Repository Purpose

This repository is responsible for:

- provision of ingestion workflow
- provision of curation workflow
- provision of orchetration workflow

---

## Expected Flow

The expected pipeline flow is:

**API → GCS Raw JSON → BigQuery Operational Table → Curated Tables**

---

## Tech Stack

- **Dataform**/**dbt**
- **BigQuery**
- **SQLX / SQL**
- **Google Cloud Platform (GCP)**

---