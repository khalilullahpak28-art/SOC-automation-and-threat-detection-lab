# Log Collection & Verification

## Objective

Verify that the Windows endpoint successfully forwards security events to the Wazuh Manager and ensure that collected logs are searchable through the Wazuh Dashboard.

---

## Why Verify Log Collection?

A SIEM is only effective if it continuously receives logs from monitored endpoints. Before creating detection rules or automating incident response, it is essential to verify that security events are successfully ingested.

---

## Verification Process

### Step 1 – Verify Agent Status

Open the Wazuh Dashboard.

Navigate to:

```
Endpoints → Agents
```

Expected Result

- Windows agent status: **Active**

---

### Step 2 – Verify Successful Logon Events

Navigate to:

```
Threat Hunting
```

Search for:

```text
data.win.system.eventID:4624
```

Event ID **4624** represents a successful Windows logon.

---

### Step 3 – Verify Failed Logon Events

Search for:

```text
data.win.system.eventID:4625
```

Event ID **4625** represents a failed Windows logon attempt.

---

## Event IDs Verified

| Event ID | Description | Status |
|----------|-------------|--------|
| 4624 | Successful Logon | ✅ Verified |
| 4625 | Failed Logon | ✅ Verified |

---

## Validation

The following checks confirmed successful communication between the Windows endpoint and the Wazuh Manager.

- Windows Agent connected successfully.
- Security events received.
- Events searchable from Threat Hunting.
- Alerts generated in near real time.

---

## Screenshots

- Windows Agent Status
- Event ID 4624
- Event ID 4625
- Threat Hunting Dashboard

---

## Result

The Windows endpoint successfully forwarded Windows Security logs to the Wazuh SIEM platform, confirming that log collection and event ingestion were functioning correctly.
