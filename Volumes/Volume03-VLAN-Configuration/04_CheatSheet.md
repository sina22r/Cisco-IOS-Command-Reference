# VLAN Configuration Cheat Sheet

---

**Volume:** 03 • VLAN Configuration

**Estimated Reading Time:** 15 Minutes

---

## VLAN Configuration

| Command | Purpose |
|---------|---------|
| `vlan VLAN_ID` | Create a new VLAN |
| `name VLAN_NAME` | Assign a name to a VLAN |
| `switchport mode access` | Configure an interface as an access port |
| `switchport access vlan VLAN_ID` | Assign an access port to a VLAN |
| `switchport mode trunk` | Configure an interface as a trunk port |
| `switchport trunk allowed vlan VLAN_LIST` | Specify allowed VLANs on a trunk |
| `switchport trunk native vlan VLAN_ID` | Configure the native VLAN |
| `switchport nonegotiate` | Disable DTP negotiation |
| `switchport voice vlan VLAN_ID` | Configure a voice VLAN |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show vlan` | Display all configured VLANs |
| `show vlan brief` | Display a summary of VLANs |
| `show vlan id VLAN_ID` | Display information for a specific VLAN |
| `show interfaces switchport` | Display switchport configuration |
| `show interfaces trunk` | Display trunk interface information |
| `show interfaces status` | Display interface status and VLAN assignment |
| `show mac address-table` | Display the MAC address table |
| `show running-config interface INTERFACE` | Display the configuration of a specific interface |

---

## Common Troubleshooting

| Problem | Verification Command |
|---------|----------------------|
| VLAN does not exist | `show vlan brief` |
| Wrong access VLAN | `show interfaces switchport` |
| Trunk is not forwarding VLANs | `show interfaces trunk` |
| Device cannot communicate | `show mac address-table` |
| Incorrect interface configuration | `show running-config interface` |

---

## Navigation

⬆️ [Back to Contents](#vlan-configuration-cheat-sheet)

⬅️ Previous: **[03_VLAN_Labs.md](03_VLAN_Labs.md)**

➡️ Next: **[Volume 04 – Trunk](../Volume04-Trunk/README.md)**
