# TheHive Integration

## Objective

Integrate TheHive with the SOC lab to centralize security alerts, create incident cases, and streamline the incident response workflow.

---

## Why TheHive?

Security analysts require a centralized platform to investigate alerts, manage cases, assign tasks, and document the complete incident response lifecycle.

TheHive provides:

- Case Management
- Alert Management
- Observable Tracking
- Task Assignment
- Incident Documentation

---

## Environment

| Component | Value |
|----------|------|
| Platform | Debian 12 |
| Deployment | Docker |
| Integrated With | Wazuh |

---

## Installation

TheHive was deployed using Docker.

Verify the deployment.

```bash
docker ps
```

Expected Result

TheHive container is running successfully.

---

## Initial Configuration

The following configuration was completed.

- Created an administrator account.
- Accessed the web dashboard.
- Verified connectivity.
- Prepared TheHive for future Wazuh integration.

---

## Verification

Successfully logged into the TheHive Dashboard.

Verified:

- Dashboard accessibility
- Case management interface
- Alert management interface

---

## Result

TheHive was successfully deployed and prepared for integration with the Wazuh SIEM platform.
