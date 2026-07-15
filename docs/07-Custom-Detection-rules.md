# Custom Detection Rules

## Objective

Extend Wazuh's detection capabilities by creating custom rules to identify malicious activities that are not covered by the default rules.

---

## Why Create Custom Rules?

Default Wazuh rules provide extensive threat detection capabilities. However, organizations often require custom detections tailored to their own infrastructure and security requirements.

Custom rules allow security analysts to detect specific attacks, applications, or behaviors unique to their environment.

---

## Rule Configuration

Custom rules were created inside the following configuration file.

```
/var/ossec/etc/rules/local_rules.xml
```

---

## Custom Rule

A custom detection rule was created using the following Rule ID.

```
100002
```

The rule was designed to detect the execution of a malicious application within the SOC lab.

---

## Apply Configuration

After saving the configuration, restart the Wazuh Manager.

```bash
sudo systemctl restart wazuh-manager
```

---

## Verification

The Wazuh Manager successfully loaded the custom rule.

The custom rule became available for event matching and alert generation.

---

## Result

A custom Wazuh detection rule was successfully created and integrated into the SIEM platform, extending its ability to detect simulated attacks.
