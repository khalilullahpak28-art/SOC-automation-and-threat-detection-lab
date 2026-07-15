# Mimikatz Attack Simulation & Detection

## Objective

Validate the effectiveness of the custom Wazuh detection rule by executing the Mimikatz credential dumping tool on the monitored Windows endpoint.

---

## Why Mimikatz?

Mimikatz is one of the most well-known post-exploitation tools used by attackers to extract credentials from Windows systems.

Detecting Mimikatz execution is an important capability for Security Operations Centers because it is commonly associated with credential theft and privilege escalation.

---

## Attack Preparation

Download the latest Mimikatz release from the official repository.

Copy the executable to the Windows endpoint.

---

## Attack Execution

Execute Mimikatz with administrative privileges.

Example:

```powershell
mimikatz.exe
```

*(Use the exact command you executed in your lab.)*

---

## Detection Process

Execution of Mimikatz triggered the custom Wazuh detection rule.

Detection Flow

```
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
Security Alert
```

---

## Verification

The generated alert was verified through:

- Threat Hunting
- Security Events
- Rule ID 100002

The alert confirmed successful execution of the custom detection rule.

---

## MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| OS Credential Dumping | T1003 |

---

## Result

The custom Wazuh rule successfully detected the execution of Mimikatz and generated an alert within the Wazuh Dashboard, validating the effectiveness of the detection rule.
