# Sysmon Installation

## Objective

Deploy Sysmon (System Monitor) on the Windows endpoint to generate detailed endpoint telemetry for advanced threat detection and forensic analysis within the SOC lab.

---

## Why Sysmon?

Windows Security logs provide basic information such as successful and failed logons. However, they do not offer sufficient visibility into endpoint activities.

Sysmon extends Windows logging by recording:

- Process creation
- Network connections
- File creation
- Registry modifications
- Driver loading
- DLL loading
- Process access
- Named pipes
- WMI events

This additional telemetry significantly improves detection capabilities in Wazuh.

---

## Installation

### Download Sysmon

Download Sysmon from the official Microsoft Sysinternals website.

---

### Extract the Files

Extract the downloaded ZIP archive.

---

### Install Sysmon

Run the following command as Administrator.

```powershell
Sysmon64.exe -accepteula -i
```

---

## Verify Installation

Verify that the Sysmon service is running.

```powershell
Get-Service Sysmon64
```

Expected Output

```
Status : Running
```

---

## Verify Event Generation

Open Event Viewer.

```
Applications and Services Logs
    └── Microsoft
        └── Windows
            └── Sysmon
                └── Operational
```

Successful installation should display continuously generated Sysmon events.

---

## Result

Sysmon was successfully deployed on the Windows endpoint and began generating detailed security telemetry for future threat detection and hunting activities.
