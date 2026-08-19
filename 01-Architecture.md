# SIEM Architecture

## Overview

The SIEM Dashboard is a cybersecurity portfolio project designed to simulate a Security Information and Event Management (SIEM) platform.

The project ingests Windows authentication logs, normalizes event data, stores events in a SQLite database, applies detection rules, generates alerts, and displays security events through a web-based dashboard.

---

## Data Flow

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

## System Components

### Windows Log Source

Provides authentication events, including:

- Failed login events
- Successful login events
- Account lockout events

### Log Ingestion

Imports log data from a text file and parses each event into individual fields.

### Event Normalization

Each event is normalized into the following format:

- timestamp
- username
- source_ip
- event_id
- event_type
- message

### SQLite Database

Stores normalized events and generated alerts.

### Detection Rules

Analyzes stored events and identifies suspicious activity based on predefined rules.

### Alert Engine

Generates Medium and High severity alerts when detection rules are triggered.

### FastAPI Backend

Provides API endpoints for retrieving events and alerts.

### React Dashboard

Displays security events, alerts, filtering options, and visualizations through a web interface.

---

## Technologies Used

### Backend

- Python
- FastAPI
- SQLite

### Frontend

- React
- Chart.js

---

## Project Structure

The project is separated into backend, frontend, and documentation components.

**Screenshot: VS Code project structure**

<img width="316" height="991" alt="image" src="https://github.com/user-attachments/assets/ab248b76-7289-47ac-8a97-b22c1d9eca84" />
