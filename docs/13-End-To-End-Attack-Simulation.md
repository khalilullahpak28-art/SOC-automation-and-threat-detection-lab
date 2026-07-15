# End-to-End Attack Simulation

## Objective

Validate the complete SOC automation pipeline by executing a simulated credential dumping attack and verifying that every security component functions as expected from detection to incident creation.

---

## Attack Scenario

A simulated attack was performed using **Mimikatz** on the monitored Windows endpoint.

The objective was to verify that the SOC automation pipeline could:

- Detect the attack.
- Generate a security alert.
- Trigger the automation workflow.
- Enrich the alert with threat intelligence.
- Automatically create an incident for the SOC analyst.

---

## Attack Workflow

```text
Mimikatz Execution
        │
        ▼
Windows Endpoint
        │
        ▼
Wazuh Agent
        │
        ▼
Wazuh Manager
        │
        ▼
Custom Rule (100002)
        │
        ▼
Alert Forwarded to Shuffle
        │
        ▼
SHA-256 Extracted
        │
        ▼
VirusTotal Reputation Lookup
        │
        ▼
TheHive Case Created
        │
        ▼
SOC Analyst Investigation
```

---

## Attack Execution

The Mimikatz executable was intentionally executed on the monitored Windows endpoint to simulate a credential dumping attack.

The activity generated Windows events that were forwarded to the Wazuh Manager through the Wazuh Agent.

---

## Detection

The custom Wazuh rule (**Rule ID: 100002**) successfully detected the execution of Mimikatz.

The alert was immediately generated within the Wazuh Dashboard.

---

## Automation

After the alert was generated:

- Wazuh forwarded the alert to Shuffle through the configured webhook.
- Shuffle automatically started the workflow.
- The workflow extracted the SHA-256 hash from the incoming alert.
- VirusTotal checked the reputation of the detected file.
- Shuffle automatically created an investigation case in TheHive.

---

## Validation

| Stage | Status |
|--------|--------|
| Mimikatz Executed | ✅ |
| Wazuh Detection | ✅ |
| Rule 100002 Triggered | ✅ |
| Alert Sent to Shuffle | ✅ |
| SHA-256 Extracted | ✅ |
| VirusTotal Reputation Retrieved | ✅ |
| TheHive Case Created | ✅ |

---

## Outcome

The complete SOC automation pipeline successfully detected a simulated attack, enriched the alert with external threat intelligence, and automatically generated an investigation case for the SOC analyst.

The successful completion of this simulation demonstrates the integration of SIEM, SOAR, Threat Intelligence, and Incident Response technologies within the SOC lab.
