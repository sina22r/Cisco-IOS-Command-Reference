# Trunk Configuration Cheat Sheet

---

**Volume:** 04 • Trunk Configuration

**Estimated Reading Time:** 15 Minutes

---

## Trunk Configuration

| Command | Purpose |
|---------|---------|
| `switchport mode trunk` | Configure an interface as a trunk port |
| `switchport trunk encapsulation dot1q` | Configure IEEE 802.1Q encapsulation (supported platforms only) |
| `switchport trunk native vlan VLAN_ID` | Configure the native VLAN |
| `switchport trunk allowed vlan VLAN_LIST` | Specify the allowed VLANs |
| `switchport trunk allowed vlan add VLAN_LIST` | Add VLANs to the allowed list |
| `switchport trunk allowed vlan remove VLAN_LIST` | Remove VLANs from the allowed list |
| `switchport nonegotiate` | Disable DTP negotiation |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show interfaces trunk` | Display trunk information |
| `show interfaces switchport` | Display switchport configuration |
| `show interfaces status` | Display interface status |
| `show vlan brief` | Display VLAN information |
| `show spanning-tree interface INTERFACE` | Display STP information for an interface |
| `show cdp neighbors` | Display directly connected Cisco devices |
| `show running-config interface INTERFACE` | Display interface configuration |

---

## Common Troubleshooting

| Problem | Verification Command |
|---------|----------------------|
| Trunk is not established | `show interfaces trunk` |
| Wrong native VLAN | `show interfaces switchport` |
| Missing allowed VLAN | `show interfaces trunk` |
| DTP negotiation issue | `show interfaces switchport` |
| Neighbor switch not detected | `show cdp neighbors` |
| Incorrect interface configuration | `show running-config interface` |

---

## Navigation

⬆️ [Back to Contents](#trunk-configuration-cheat-sheet)

⬅️ Previous: **[03_Trunk_Labs.md](03_Trunk_Labs.md)**

➡️ Next: **[Volume 05 – STP](../Volume05-STP/README.md)**
