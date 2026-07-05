# EtherChannel Cheat Sheet

---

**Volume:** 06 • EtherChannel

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `channel-group GROUP mode {active \| passive \| desirable \| auto \| on}` | Add an interface to an EtherChannel |
| `channel-protocol {lacp \| pagp}` | Select the EtherChannel negotiation protocol |
| `interface port-channel NUMBER` | Create or access a Port-Channel interface |
| `port-channel load-balance METHOD` | Configure the load-balancing algorithm |
| `lacp system-priority PRIORITY` | Configure the LACP system priority |
| `lacp port-priority PRIORITY` | Configure the LACP port priority |
| `pagp learn-method {aggregate-port \| physical-port}` | Configure the PAgP learning method |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show etherchannel summary` | Display all EtherChannel groups |
| `show etherchannel detail` | Display detailed EtherChannel information |
| `show etherchannel port-channel` | Display Port-Channel information |
| `show lacp neighbor` | Display LACP neighbors |
| `show pagp neighbor` | Display PAgP neighbors |
| `show interfaces port-channel NUMBER` | Display Port-Channel interface information |
| `show running-config interface port-channel NUMBER` | Display the Port-Channel configuration |

---

## EtherChannel Modes

| Mode | Protocol | Description |
|------|----------|-------------|
| `active` | LACP | Actively initiates LACP negotiation |
| `passive` | LACP | Responds to LACP negotiation requests |
| `desirable` | PAgP | Actively negotiates a PAgP EtherChannel |
| `auto` | PAgP | Passively waits for PAgP negotiation |
| `on` | None | Creates a static EtherChannel without negotiation |

---

## Common Troubleshooting

| Problem | Verification Command |
|---------|----------------------|
| EtherChannel not forming | `show etherchannel summary` |
| LACP negotiation failed | `show lacp neighbor` |
| PAgP negotiation failed | `show pagp neighbor` |
| Member interface suspended | `show etherchannel detail` |
| Port-Channel down | `show interfaces port-channel NUMBER` |
| Configuration mismatch | `show running-config interface port-channel NUMBER` |

---

## Navigation

⬆️ [Back to Contents](#etherchannel-cheat-sheet)

⬅️ Previous: **[03_EtherChannel_Labs.md](03_EtherChannel_Labs.md)**

➡️ Next: **[Volume 07 – IPv4](../Volume07-IPv4/README.md)**
