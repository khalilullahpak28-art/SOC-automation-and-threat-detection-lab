# Wazuh Installation

## Objective

Deploy the Wazuh SIEM platform to monitor Windows endpoints, collect security logs, and detect security threats in a controlled SOC lab environment.

---

| Component        | Value        |
|------------------|--------------|
| Operating System | Debian 12    |
| Wazuh Version    | 12.14        |
| Deployment Type  | Single Node  |
| Virtualization   | VirtualBox   |

---

## Installation Steps

### 1. Update the Operating System

```bash
sudo apt update && sudo apt upgrade -y
```

This ensures all system packages are up to date before installing Wazuh.

---

### 2. Download the Official Wazuh Installer

```bash
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
```

Downloads the official Wazuh installation script.

---

### 3. Install Wazuh

```bash
sudo bash wazuh-install.sh -a
```

The `-a` option installs the complete Wazuh stack:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

---

### 4. Verify the Installation

Check that the Wazuh services are running.

```bash
sudo systemctl status wazuh-manager
```

```bash
sudo systemctl status wazuh-indexer
```

```bash
sudo systemctl status wazuh-dashboard
```

---

## Verification

- Successfully accessed the Wazuh Dashboard through a web browser.
- Confirmed that all Wazuh services were running.
- Verified successful communication between the Dashboard, Manager, and Indexer.

---

## Result

The Wazuh SIEM platform was successfully deployed on Debian 12 and is ready to receive logs from monitored endpoints.
