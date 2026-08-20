# Alerting

## Overview

The SIEM generates alerts when authentication activity matches predefined detection rules.

Alerts are stored in the SQLite database and displayed in the React dashboard for analyst review.

---

## Severity Levels

The current alerting logic uses two severity levels:

### Medium

Generated when:

- 5 failed logins occur within 5 minutes

### High

Generated when:

- 10 failed logins occur within 5 minutes
- An account lockout event is detected

---

## Alert Types

The current alert types are:

- Repeated Failed Logins
- Account Lockout

---

## Alert Generation

When a detection rule is triggered, the SIEM stores an alert containing:

- timestamp
- username
- alert_type
- severity
- message

Example:

```text
Username: bob
Alert Type: Repeated Failed Logins
Severity: High
Message: 10 failed logins detected within 5 minutes
```

---

## Dashboard Alert Review

Generated alerts are displayed in the Recent Alerts section of the dashboard.

Analysts can filter alerts by:

- All Alerts
- High Severity
- Medium Severity
- Account Lockout
- Repeated Failed Logins

This allows analysts to focus on the most relevant security activity.

---
