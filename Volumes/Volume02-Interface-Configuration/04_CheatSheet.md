# Interface Configuration Cheat Sheet

---

**Volume:** 02 • Interface Configuration

**Estimated Reading Time:** 15 Minutes

---

## Interface Setup

| Command | Purpose |
|---------|--------|
| `interface GigabitEthernet0/0` | Enter interface configuration mode |
| `description TEXT` | Add description to interface |
| `ip address X.X.X.X MASK` | Assign IPv4 address |
| `ipv6 address PREFIX` | Assign IPv6 address |
| `no shutdown` | Enable interface |
| `shutdown` | Disable interface |
| `default interface` | Reset interface to default |

---

## Layer 2 Settings

| Command | Purpose |
|---------|--------|
| `speed` | Set interface speed |
| `duplex` | Set duplex mode |
| `negotiation auto` | Enable auto negotiation |
| `media-type` | Select interface media type |
| `encapsulation` | Set encapsulation type |

---

## Advanced Interface Control

| Command | Purpose |
|---------|--------|
| `bandwidth` | Set logical bandwidth value |
| `delay` | Configure interface delay |
| `mtu` | Set maximum transmission unit |
| `load-interval` | Configure traffic sampling interval |
| `keepalive` | Enable/disable keepalive messages |
| `clock rate` | Set clock rate on serial interfaces |

---

## Verification Commands

| Command | Purpose |
|---------|--------|
| `show interfaces` | Detailed interface information |
| `show ip interface brief` | Quick interface summary |
| `show interfaces status` | Switch port status |
| `show interfaces counters` | Traffic counters |
| `show interfaces counters errors` | Error statistics |
| `show interfaces switchport` | Layer 2 switchport info |
| `show interfaces trunk` | Trunk interface status |
| `show ipv6 interface` | IPv6 interface info |

---

## Quick Troubleshooting

- Interface is down → check `shutdown`
- No IP connectivity → check `ip address`
- No traffic → check duplex/speed mismatch
- VLAN issue → check switchport mode
- Errors → check `show interfaces counters errors`

---

## Navigation

⬅️ Previous: **[03_Interface_Labs.md](03_Interface_Labs.md)**

➡️ Next: **[Volume 03 – VLAN Configuration](../Volume03-VLAN-Configuration/README.md)**
