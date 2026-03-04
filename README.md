# MAC-ml-service
**Match Analytics Calculator – ML-powered ranking and match prediction service**

---

## Overview

MAC (Match Analytics Calculator) is a backend system designed to rank players and predict match outcomes using a combination of ELO rating algorithms and machine learning models.

The project simulates a production-oriented sports analytics service, combining backend engineering, statistical modeling, and MLOps practices.

---

## Problem Statement

In small amateur padel tournaments, team assignments are often random.  
This frequently results in unbalanced matches where one pair significantly outperforms the other.

The goal of this project is to:

- Dynamically rank players using an ELO-based rating system  
- Store and process match history  
- Predict match outcomes using machine learning  
- Suggest balanced team pairings  
- Provide a structured REST API for rankings and forecasting  

---

## Core Objectives

- Implement a dynamic ELO rating engine  
- Train an ML model to predict match outcomes  
- Expose predictions and rankings via FastAPI  
- Design a modular, production-ready backend architecture  
- Integrate CI/CD, model versioning, monitoring, and deployment  

---

## Tech Stack

### Backend
- Python 3.11+
- FastAPI
- Pydantic
- SQLAlchemy
- PostgreSQL

### Machine Learning
- scikit-learn
- pandas
- numpy
- MLflow (for experiment tracking & model versioning)

### Infrastructure
- Docker
- GitHub Actions (CI/CD)
- Prometheus (metrics)
- Optional: Kubernetes (future phase)

---

## System Architecture (High-Level)
graph TD
    A[Client] --> B(FastAPI - API Layer)
    B --> C[Service Layer]
    
    subgraph Services [Service Layer Components]
    C --> D[ELO Engine]
    C --> E[ML Inference Module]
    C --> F[Team Balancing Logic]
    end
    
    Services --> G[(Database - PostgreSQL)]
    Services --> H([Model Registry - MLflow])

---

## Data Strategy

To ensure meaningful model training, the system will leverage large historical tennis datasets as a proxy for padel matches.

Feature engineering may include:

- Rank difference  
- ELO difference  
- Recent performance metrics  
- Match frequency  
- Surface (optional extension)  

The dataset will be cleaned and transformed into structured training features.

---

## Status

Work in progress.
