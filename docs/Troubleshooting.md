# Troubleshooting

## Overview

Building the SOC Automation Lab involved several configuration and integration challenges. This section documents the major issues encountered during deployment and the solutions used to resolve them.

---

## 1. Windows Agent Became Inactive

### Problem

After modifying the Windows Agent configuration (`ossec.conf`) to collect Sysmon logs, the Windows agent stopped communicating with the Wazuh Manager and appeared as **Inactive**.

### Cause

An incorrect configuration inside `ossec.conf` prevented the Wazuh Agent from starting correctly.

### Solution

- Removed the incorrect configuration.
- Restored the previous working configuration.
- Restarted the Wazuh Agent service.

### Result

The Windows agent reconnected successfully and returned to the **Active** state.

---

## 2. Sysmon Logs Were Not Appearing

### Problem

Although Sysmon was installed and running, no Sysmon events appeared inside Wazuh.

### Cause

The issue was caused by an incorrect agent configuration and several unsuccessful troubleshooting attempts.

### Solution

The environment was restored to a stable configuration before continuing with further integrations.

### Result

Windows Security events continued to be collected successfully while the remaining SOC components were completed.

---

## 3. Static IP Configuration

### Problem

Virtual machines occasionally lost communication after rebooting.

### Cause

Incorrect network adapter configuration and missing static IP assignments.

### Solution

Configured static IP addresses for all virtual machines and verified connectivity using ping.

### Result

Stable communication was established between Debian, Windows, and Kali Linux.

---

## 4. Custom Detection Rule Not Triggering

### Problem

The custom detection rule failed to generate alerts for Mimikatz execution.

### Cause

The rule conditions were not matching the expected alert data.

One of the main challenges was identifying the correct field values to match. Several attempts using different values—including **"mimikatz"**—did not produce the expected results, requiring repeated testing and debugging before the correct rule logic was achieved.

### Solution

- Reviewed the generated Wazuh alerts.
- Updated the custom rule.
- Restarted the Wazuh Manager after each modification.
- Repeated testing until Rule **100002** triggered successfully.

### Result

The custom detection rule successfully detected Mimikatz execution.

---

## 5. Wazuh → Shuffle Integration

### Problem

Shuffle did not receive alerts from Wazuh.

### Cause

The webhook configuration inside the Wazuh Manager was incomplete.

### Solution

- Generated a webhook inside Shuffle.
- Updated the Wazuh `ossec.conf` configuration.
- Restarted the Wazuh Manager.
- Performed additional attack simulations to validate the integration.

### Result

Wazuh successfully forwarded alerts to Shuffle.

---

## 6. VirusTotal Integration

### Problem

The workflow could not retrieve file reputation.

### Cause

The VirusTotal node required API authentication.

### Solution

Generated a VirusTotal API key and configured it within the Shuffle workflow.

### Result

The SHA-256 hash was successfully enriched with VirusTotal reputation data.

---

## 7. TheHive Integration

### Problem

Shuffle was unable to create investigation cases.

### Cause

TheHive authentication had not been configured.

### Solution

- Created a dedicated TheHive user.
- Generated an API key.
- Configured the API key in the Shuffle TheHive node.

### Result

Shuffle automatically created investigation cases inside TheHive.

---

## Lessons from Troubleshooting

Every major configuration change was followed by:

1. Restarting the required service.
2. Executing Mimikatz again.
3. Verifying Wazuh detection.
4. Validating the Shuffle workflow.
5. Confirming automatic case creation inside TheHive.

Following this iterative approach made it possible to identify configuration issues quickly while validating each stage of the SOC automation pipeline.
