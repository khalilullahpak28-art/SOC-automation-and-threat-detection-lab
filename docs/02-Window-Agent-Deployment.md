# Windows Agent Deployment

## Objective

Deploy the Wazuh agent on a Windows 10 endpoint and establish secure communication with the Wazuh Manager for centralized log collection and monitoring.

---

## Environment

| Component | Value |
|----------|------|
| Endpoint | Windows 10 |
| Agent | Wazuh Agent |
| Manager | Wazuh Server (Debian 12) |
| Communication Port | 1514/UDP, 1515/TCP |
 
---

## Installation Steps

### 1. Download the Wazuh Agent

Download the latest Windows agent from the official Wazuh website.

---

### 2. Install the Agent

Run the installer as Administrator.

During installation, provide:

- Wazuh Manager IP Address
- Agent Name

---

### 3. Start the Wazuh Service

Verify that the service is running.

```powershell
Get-Service WazuhSvc
```

Expected Status:

```text
Running
```

---

### 4. Verify Agent Registration

Open the Wazuh Dashboard.

Navigate to:

```
Endpoints → Agents
```

Confirm that the Windows endpoint appears as:

- Status: Active

---

## Verification

Successfully received Windows Security events from the endpoint.

Verified Event IDs:

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

Confirmed that the Windows endpoint was successfully communicating with the Wazuh Manager.

---

## Result

The Windows endpoint was successfully onboarded to the Wazuh SIEM platform and is actively forwarding Windows Security logs for monitoring and threat detection.
