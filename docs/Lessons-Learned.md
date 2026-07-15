# Lessons Learned

## Overview

Developing this SOC Automation Lab provided practical experience in designing, deploying, integrating, and validating a complete Security Operations Center using open-source security technologies.

The project emphasized hands-on implementation rather than theoretical concepts, strengthening both defensive security and incident response skills.

---

## Technical Skills Acquired

### Security Information and Event Management (SIEM)

- Successfully deployed and configured Wazuh.
- Connected Windows endpoints to the SIEM.
- Verified centralized log collection.
- Performed log analysis using Threat Hunting.

---

### Endpoint Monitoring

- Installed and configured Sysmon.
- Collected Windows Security Events.
- Improved endpoint visibility for threat detection.

---

### Detection Engineering

- Developed custom Wazuh detection rules.
- Modified `local_rules.xml`.
- Created Rule **100002** to detect Mimikatz execution.
- Tested and validated custom detections through attack simulation.

---

### Threat Intelligence

- Integrated VirusTotal into the automation workflow.
- Enriched security alerts using SHA-256 reputation analysis.
- Learned the importance of external threat intelligence during investigations.

---

### Incident Response

- Deployed TheHive locally using Docker.
- Automated incident creation.
- Learned how SOC analysts manage and investigate security incidents.

---

### Security Orchestration and Automation (SOAR)

- Designed a complete Shuffle workflow.
- Configured Webhook-based integrations.
- Automated alert processing.
- Reduced manual investigation tasks through workflow automation.

---

### SOC Workflow Understanding

This project provided practical experience with the complete SOC lifecycle.

```
Detection
      │
      ▼
Log Collection
      │
      ▼
Threat Detection
      │
      ▼
Threat Intelligence
      │
      ▼
Incident Creation
      │
      ▼
SOC Investigation
```

---

## Key Takeaways

Through this project, I learned how multiple security platforms work together to create an effective Security Operations Center.

Instead of viewing Wazuh, Shuffle, VirusTotal, and TheHive as separate tools, I gained experience integrating them into a unified incident response pipeline capable of detecting, enriching, and responding to security events automatically.

---

## Conclusion

Building this SOC Automation Lab strengthened my practical understanding of SIEM, SOAR, Detection Engineering, Threat Intelligence, and Incident Response while improving my troubleshooting, integration, and security automation skills through hands-on experience.
