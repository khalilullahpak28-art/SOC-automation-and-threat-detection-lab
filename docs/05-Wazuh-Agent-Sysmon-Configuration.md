# Wazuh Agent & Sysmon Configuration

## Objective

Configure the Wazuh Windows Agent to collect Sysmon event logs and forward them to the Wazuh Manager for centralized analysis and threat detection.

---

## Why Configure Sysmon?

Although Sysmon generates detailed endpoint telemetry, these events are stored locally on the Windows machine. To analyze them within the SIEM, the Wazuh Agent must be configured to monitor the Sysmon event channel.

---

## Configuration File

Location

```
C:\Program Files (x86)\ossec-agent\ossec.conf
```

---

## Configuration

The following configuration was added to the Wazuh Agent.

```xml
<localfile>
    <location>Microsoft-Windows-Sysmon/Operational</location>
    <log_format>eventchannel</log_format>
</localfile>
```

---

## Restart the Wazuh Agent

```powershell
Restart-Service WazuhSvc
```

---

## Verification

The Windows agent was verified as **Active** from the Wazuh Dashboard.

Navigation

```
Endpoints → Agents
```

The agent successfully reconnected to the Wazuh Manager after the configuration changes.

---

## Troubleshooting

During configuration, the Wazuh agent temporarily became inactive due to an incorrect configuration change.

The issue was resolved by restoring the previous working configuration and restarting the Wazuh service.

---

## Result

The Windows endpoint was successfully configured to forward Windows event channels to the Wazuh Manager. This configuration serves as the foundation for future Sysmon-based threat detection.
