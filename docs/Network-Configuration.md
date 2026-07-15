# Network Configuration

## Objective

Configure network communication between all virtual machines to enable secure log collection, attack simulation, and centralized monitoring within the SOC lab.

---

## Lab Network Topology

| Machine | Role | Network | IP Address |
|---------|------|---------|------------|
| Debian 12 | Wazuh Server | Internal Network | 192.168.100.10 |
| Windows 10 | Victim | Internal Network | 192.168.100.30 |
| Kali Linux | Attacker | Internal Network | 192.168.100.20 |

All virtual machines were connected to the same Internal Network to allow secure communication while remaining isolated from external networks.

---

## Network Adapters

### Debian

- Adapter 1 → NAT
- Adapter 2 → Internal Network

### Windows

- Adapter 1 → NAT
- Adapter 2 → Internal Network

### Kali

- Adapter 1 → NAT
- Adapter 2 → Internal Network

---

## Static IP Configuration

Static IP addresses were manually configured to ensure consistent communication between all machines.

### Verification

Connectivity between the virtual machines was verified using:

```bash
ping <IP Address>
```

Example

```bash
ping 192.168.100.10
```

Successful replies confirmed proper communication.

---

## Connectivity Tests

The following communication was verified.

✅ Kali → Windows

✅ Kali → Debian

✅ Windows → Debian

---

## Challenges

During deployment the following issues were encountered.

- Incorrect adapter mapping
- Wrong interface receiving the static IP
- Loss of connectivity after reboot
- Routing conflicts between NAT and Internal Network

These issues were resolved by correcting the network adapter assignments and applying static IP addresses to the appropriate interfaces.

---

## Result

All three virtual machines successfully communicated over the Internal Network, providing the required connectivity for Wazuh monitoring, attack simulation, and future SOAR automation.
