# Custom Detection Rule Development

## Objective

Develop a custom Wazuh detection rule to identify the intentional execution of **Mimikatz** on a monitored Windows endpoint.

---

## Why Create a Custom Rule?

Although Wazuh provides a large collection of built-in detection rules, creating custom rules allows security analysts to detect organization-specific threats and strengthen detection capabilities.

To demonstrate detection engineering within this SOC lab, a custom rule was developed to detect the execution of the **Mimikatz** credential dumping tool.

---

## Configuration Files

The custom rule was created and managed using Wazuh's local rules configuration.

### Wazuh Manager

```
/var/ossec/etc/rules/local_rules.xml
```

### Wazuh Dashboard

```
Rules → Custom Rules
```

The rule was also managed through the Wazuh Dashboard to simplify future modifications and validation.

---

## Custom Rule Information

| Property | Value |
|----------|------|
| Rule ID | 100002 |
| Purpose | Detect Mimikatz Execution |
| Severity | *(Add your level)* |

---

## Apply Configuration

After creating the custom rule, the Wazuh Manager configuration was reloaded.

```bash
sudo systemctl restart wazuh-manager
```

This ensured the newly created rule became active.

---

## Verification

The rule was successfully loaded by the Wazuh Manager.

A Mimikatz execution test was later performed to verify that Rule **100002** generated an alert as expected.

---

## Result

A custom Wazuh detection rule (Rule ID **100002**) was successfully created and integrated into the SIEM to detect the execution of Mimikatz on the monitored Windows endpoint.
