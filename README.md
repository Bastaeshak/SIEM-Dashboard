# SIEM Dashboard

## Project Status

🚧 **Work in Progress**

This project is currently under active development. Features, detection rules, visualizations, and documentation will continue to be added and refined as development progresses.

---

## Overview

The SIEM Dashboard is a security monitoring platform designed to collect, normalize, correlate, and visualize security events from multiple log sources.

The system ingests logs through syslog receivers and file parsers, converts events into a standardized format, stores events in a centralized database, and analyzes activity using event correlation rules.

Security incidents are displayed through an interactive dashboard that allows analysts to monitor events, investigate alerts, identify trends, and pivot between related activities.

This project demonstrates the core functionality found in enterprise SIEM platforms such as Splunk, Elastic Stack, ArcSight, and Microsoft Sentinel.

---

## Objectives

- Collect logs from multiple sources
- Normalize different log formats into a common schema
- Store security events in a centralized database
- Detect suspicious activity through event correlation
- Visualize security events through an interactive dashboard
- Implement severity-based alerting
- Provide forensic investigation capabilities

---

## Features

### Log Ingestion

- Syslog receiver (UDP/TCP)
- File-based log parsing
- Support for multiple log formats
- Pluggable parser architecture
- Event normalization

### Backend API

- FastAPI backend
- REST API endpoints
- Event querying
- Statistical analysis
- Authentication and authorization

### Event Correlation

- Rule-based detection engine
- Multi-event pattern matching
- Risk scoring
- Configurable detection rules

### Data Visualization

- Event timelines
- Security dashboards
- Event distribution charts
- Activity heatmaps
- Geographic attack visualization

### Alerting

- Severity classification
- Threshold-based notifications
- Alert grouping
- Sensitivity tuning

### Time-Based Analysis

- Last-hour analysis
- Last 24-hour analysis
- Last 7-day analysis
- Custom time-range analysis
- Trend detection
- Anomaly identification

### Forensic Investigation

- Event pivoting
- Source IP investigation
- User activity investigation
- Full event inspection
- Search functionality
- CSV and JSON export

---

## Architecture

```text
                Log Sources
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼

    Syslog         Firewall        Application
     Logs            Logs             Logs

        └──────────────┼──────────────┘
                       │
                       ▼

               Log Ingestion Layer

                       │
                       ▼

               Normalization Engine

                       │
                       ▼

                    Database

                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼

   Correlation      REST API      Alert Engine
      Rules

                       │
                       ▼

                Interactive Dashboard
```

---

## Normalized Event Schema

All events are transformed into a standardized format.

```json
{
    "timestamp": "",
    "source": "",
    "severity": "",
    "event_type": "",
    "source_ip": "",
    "destination_ip": "",
    "username": "",
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
| Authentication | JWT |

---

## Installation

### Clone the repository

```bash
git clone https://github.com/your-username/siem-dashboard.git
```

### Create a virtual environment

```bash
python -m venv venv
```

### Activate the virtual environment

**Linux/macOS**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Start the backend server

```bash
uvicorn app.main:app --reload
```

### Start the frontend

```bash
npm install
npm run dev
```

---

## Example Correlation Rule

```yaml
failed_login_correlation:

  threshold: 5

  window: 5m

  severity: high
```

---

## Limitations

- Detection quality depends on the quality of ingested logs.
- Correlation rules require continuous tuning.
- False positives can occur when thresholds are not properly adjusted.
- Geographic mapping depends on accurate IP geolocation.
- SIEM effectiveness depends on both the quality of collected data and the quality of detection rules.

---

## SIEM Platform Comparison

| Platform | Description |
| --- | --- |
| Splunk | Commercial SIEM platform |
| Elastic Stack | Open-source analytics platform |
| ArcSight | Enterprise security monitoring platform |
| Microsoft Sentinel | Cloud-native SIEM platform |

---

## References

- RFC 5424 (Syslog Protocol)
- OWASP Logging Cheat Sheet
- MITRE ATT&CK Framework
- FastAPI Documentation
- React Documentation
- Chart.js Documentation
