# Day 01 - Backend Foundation

**Date:** August 17, 2026

## Overview

Today I built the initial backend foundation for the SIEM dashboard.

The goal was to establish a working pipeline that could ingest security events, store them in a database, detect repeated failed login activity, and generate alerts.

---

## Completed

* Set up the FastAPI backend
* Created the SQLite database
* Created the `events` table
* Created the `alerts` table
* Built event storage functionality
* Built event retrieval functionality
* Created file-based log ingestion
* Parsed and normalized sample Windows authentication logs
* Created the first detection rule
* Generated Medium severity alerts
* Created API endpoints for viewing events and alerts

---

## Current Data Flow

```text
Windows Log File
        ↓
Log Parser
        ↓
Event Normalization
        ↓
SQLite Events Table
        ↓
Detection Rule
        ↓
SQLite Alerts Table
        ↓
FastAPI Backend
```


<img width="1907" height="987" alt="image" src="https://github.com/user-attachments/assets/758965eb-fb6b-44a2-a9e3-747cfb958127" />


```text
GET  /
GET  /events
POST /events
GET  /alerts
```

---

## Detection Rule Implemented

```text
5 failed logins within 5 minutes
        ↓
Medium Severity Alert
```

The rule was successfully tested using repeated Windows Event ID `4625` failed login events.


<img width="1899" height="967" alt="image" src="https://github.com/user-attachments/assets/ac0fad72-5922-4571-8575-3f0419982b4e" />


```text
True
```

---

## API Endpoints

```text
GET  /
GET  /events
POST /events
GET  /alerts
```


<img width="1901" height="906" alt="image" src="https://github.com/user-attachments/assets/841cdb1f-6685-4337-825d-af2873142bfb" />


---

## Files Created

```text
backend/
├── main.py
├── database.py
├── event_model.py
├── alert_model.py
├── log_parser.py
├── detection_rules.py
├── test_detection.py
├── sample_windows_logs.txt
└── siem.db
```


<img width="302" height="442" alt="image" src="https://github.com/user-attachments/assets/c62d5ee2-f276-4cee-9b2f-dfb8e3fd7934" />


---

## Testing

The failed login detection rule was tested using five failed login events for the same user within a five-minute period.

The detection returned:

```text
True
```

A Medium severity alert was then stored in the SQLite `alerts` table.


<img width="1886" height="986" alt="image" src="https://github.com/user-attachments/assets/c9d9d592-a8d6-4f91-b4fd-2645f473aa72" />


---

## Next Steps

* Add the 10 failed logins within 5 minutes High severity rule
* Add the account lockout High severity rule
* Continue building the alerting functionality
