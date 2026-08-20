# SIEM Dashboard

## Overview

The SIEM Dashboard is a cybersecurity portfolio project designed to simulate the core workflow of a Security Information and Event Management (SIEM) platform.

The system ingests Windows authentication logs, normalizes event data, stores events in SQLite, applies correlation rules to identify suspicious activity, generates alerts, and presents the results through an interactive analyst dashboard.

The project focuses on demonstrating SOC analyst workflows rather than recreating a full enterprise SIEM.

---

## Objectives

- Ingest Windows authentication logs
- Normalize security events into a common schema
- Store events in a centralized database
- Detect suspicious activity through correlation rules
- Generate severity-based alerts
- Expose data through a REST API
- Visualize events and alerts through an analyst dashboard

---

## Features

### Log Ingestion

- File-based log parsing
- Windows authentication log ingestion
- Event normalization

### Event Correlation

- Rule-based detection engine
- Repeated failed-login detection
- Account lockout detection
- Event grouping by username
- Risk scoring through severity classification

### Alerting

- Medium-severity alerts
- High-severity alerts
- Alert storage in SQLite

### Backend API

- FastAPI backend
- REST API endpoints
- Event retrieval
- Alert retrieval

### Frontend Dashboard

- Dashboard metrics
- Recent alerts table
- Recent events table
- Event filtering
- Alert filtering
- Alert severity visualization using Chart.js

---

## Detection Rules

| Rule | Severity |
| --- | --- |
| 5 failed logins within 5 minutes | Medium |
| 10 failed logins within 5 minutes | High |
| Account lockout | High |

---

## SIEM Architecture

```text
Windows Logs
        ↓
Log Ingestion
        ↓
Event Normalization
        ↓
SQLite Database
        ↓
Detection Rules
        ↓
Alerts
        ↓
FastAPI Backend
        ↓
React Dashboard
```

---

## Normalized Event Schema

```json
{
  "timestamp": "",
  "username": "",
  "source_ip": "",
  "event_id": "",
  "event_type": "",
  "message": ""
}
```

---

## Technology Stack

| Component | Technology |
| --- | --- |
| Backend | FastAPI |
| Database | SQLite |
| Frontend | React |
| Visualization | Chart.js |
| Language | Python |

---

## Current Log Sources

- Failed login events
- Successful login events
- Account lockout events

---

## Installation

### Clone the repository

```bash
git clone https://github.com/your-username/siem-dashboard.git
```

### Backend Setup

```bash
cd backend
python -m venv venv
```

**Windows**

```bash
.\venv\Scripts\python.exe -m pip install fastapi uvicorn
```

### Frontend Setup

```bash
cd frontend
npm install
```

### Start the Backend

```bash
.\venv\Scripts\python.exe -m uvicorn main:app --reload
```

### Start the Frontend

```bash
npm.cmd run dev
```

---

## Repository Documentation

- 01-Architecture.md
- 02-Log-Ingestion.md
- 03-Event-Correlation.md
- 04-Backend-API.md
- 05-Frontend-Dashboard.md
- 06-Alerting.md
- Source-Code-Explanation.md
