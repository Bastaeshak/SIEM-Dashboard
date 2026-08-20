# Event Correlation

## Overview

The SIEM evaluates stored authentication events and applies detection rules to identify suspicious activity.

The current correlation logic focuses on repeated failed login attempts and account lockout events.

---

## Detection Rules

### Repeated Failed Logins

The SIEM checks failed login activity for each username within a five-minute window.

Rules:

- 5 failed logins within 5 minutes = Medium severity
- 10 failed logins within 5 minutes = High severity

The High severity threshold is evaluated before the Medium threshold so that 10 or more failed logins are not incorrectly classified as Medium.

---

## Account Lockout Detection

Windows Event ID `4740` represents an account lockout.

When an account lockout event is detected, the SIEM immediately creates a High severity alert.

---

## Event Grouping

Failed login events are grouped by username.

The detection engine retrieves failed login events for a specific user and counts how many occurred within the most recent five-minute window.

---

## Severity Assignment

### Medium

Generated when:

- 5 to 9 failed logins occur within 5 minutes

### High

Generated when:

- 10 or more failed logins occur within 5 minutes
- An account lockout event is detected

---

## Screenshot 1: High Severity Failed Login Alert

<img width="1225" height="388" alt="image" src="https://github.com/user-attachments/assets/2d0d30db-9a82-44bd-8978-03795d155570" />

---

## Screenshot 2: Account Lockout Alert

<img width="1217" height="388" alt="image" src="https://github.com/user-attachments/assets/74134898-bf27-453b-8e69-e1c657533c51" />
