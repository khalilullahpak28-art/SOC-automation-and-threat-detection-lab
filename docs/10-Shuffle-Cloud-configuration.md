# Shuffle Cloud Configuration

## Objective

Configure Shuffle SOAR to automate security operations by creating workflows capable of processing Wazuh alerts, enriching them with threat intelligence, and forwarding incidents to TheHive.

---

## Why Shuffle?

Modern Security Operations Centers (SOCs) rely on Security Orchestration, Automation, and Response (SOAR) platforms to automate repetitive security tasks.

Shuffle was selected because it supports workflow automation and integrates with Wazuh, VirusTotal, and TheHive.

---

## Environment

| Component | Value |
|----------|------|
| Platform | Shuffle Cloud |
| Deployment | Cloud Hosted |
| Purpose | Security Orchestration & Automation |

---

## Configuration Steps

### 1. Create a Shuffle Account

Create an account on the Shuffle Cloud platform.

---

### 2. Create a New Workflow

After logging in:

- Create a new workflow.
- Assign a descriptive name.
- Open the workflow editor.

---

### 3. Configure the Webhook Trigger

Add a **Webhook** trigger node.

The generated webhook URL will later be used by Wazuh to forward alerts into the workflow.

---

### 4. Save the Workflow

Save the workflow after creating the initial trigger.

---

## Verification

The following items were verified.

- Successfully logged into Shuffle.
- Workflow created successfully.
- Webhook generated successfully.
- Workflow ready for integration with Wazuh.

---

## Result

Shuffle Cloud was successfully configured and prepared to receive security alerts from the Wazuh SIEM platform.
