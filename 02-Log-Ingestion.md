# Log Ingestion

## Overview

The SIEM Dashboard imports Windows authentication logs from a text file.

Each log entry is parsed, normalized, and stored in a SQLite database before being analyzed by the detection engine.

---

## File Parsing

The log parser reads events from `sample_windows_logs.txt`.

Each log entry uses the following format:

```text
timestamp|username|source_ip|event_id|event_type|message
```

Example:

```text
2026-08-17 20:30:00|alice|192.168.1.100|4625|Failed Login|User authentication failed
```

---

## Event Normalization

Each event is normalized into the following fields:

- timestamp
- username
- source_ip
- event_id
- event_type
- message

---

## Database Storage

After normalization, events are stored in the `events` table inside `siem.db`.

Stored event fields:

- timestamp
- username
- source_ip
- event_id
- event_type
- message

---

## Screenshot 1: Log Import

<img width="1364" height="410" alt="image" src="https://github.com/user-attachments/assets/5fbf0fef-01c5-49be-b177-809a32d0d18e" />



## Screenshot 2: Database Verification

<img width="1239" height="405" alt="image" src="https://github.com/user-attachments/assets/9f81cb5e-3597-4cbc-ba11-0ed4cea12d27" />

