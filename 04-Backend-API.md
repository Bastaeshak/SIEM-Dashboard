# Backend API

## Overview

The FastAPI backend serves as the communication layer between the SQLite database and the React dashboard.

It provides API endpoints for storing, retrieving, and displaying security events and alerts.

---

## FastAPI Endpoints

### GET /

Returns the backend status.

Response:

```json
{
  "message": "SIEM Dashboard Backend Running"
}
```

---

### POST /events

Stores a new event in the SQLite database.

Example request:

```json
{
  "timestamp": "2026-08-17 20:30:00",
  "username": "alice",
  "source_ip": "192.168.1.100",
  "event_id": "4625",
  "event_type": "Failed Login",
  "message": "User authentication failed"
}
```

---

### GET /events

Retrieves all stored events.

---

### GET /alerts

Retrieves all generated alerts.

---

## Database Interactions

Events are stored in the `events` table.

Alerts are stored in the `alerts` table.

The React dashboard retrieves data through these API endpoints and displays the results to the analyst.

---

## Screenshot 1: Swagger UI

<img width="1899" height="892" alt="image" src="https://github.com/user-attachments/assets/0f96f82a-2930-4dcd-9741-e1552d58b8db" />

---

## Screenshot 2: Events API Response

<img width="1913" height="816" alt="image" src="https://github.com/user-attachments/assets/114b871d-9d98-4e0b-998e-cd94026fff73" />
