# Spanning Tree Protocol Cheat Sheet

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `spanning-tree mode {pvst \| rapid-pvst \| mst}` | Select the STP operating mode |
| `spanning-tree vlan VLAN_ID priority VALUE` | Configure the bridge priority |
| `spanning-tree vlan VLAN_ID root primary` | Configure the switch as the primary Root Bridge |
| `spanning-tree vlan VLAN_ID root secondary` | Configure the switch as the secondary Root Bridge |
| `spanning-tree cost COST` | Configure the interface path cost |
| `spanning-tree port-priority PRIORITY` | Configure the interface port priority |
| `spanning-tree link-type {point-to-point \| shared}` | Configure the RSTP link type |
| `spanning-tree vlan VLAN_ID hello-time SECONDS` | Configure the Hello timer |
| `spanning-tree vlan VLAN_ID forward-time SECONDS` | Configure the Forward Delay timer |
| `spanning-tree vlan VLAN_ID max-age SECONDS` | Configure the Max Age timer |
| `spanning-tree extend system-id` | Enable the Extended System ID feature |

---

## Protection Features

| Command | Purpose |
|---------|---------|
| `spanning-tree portfast` | Enable PortFast on an interface |
| `spanning-tree portfast default` | Enable PortFast globally |
| `spanning-tree bpduguard enable` | Enable BPDU Guard on an interface |
| `spanning-tree portfast bpduguard default` | Enable BPDU Guard on all PortFast interfaces |
| `spanning-tree bpdufilter enable` | Enable BPDU Filter on an interface |
| `spanning-tree portfast bpdufilter default` | Enable BPDU Filter globally for PortFast |
| `spanning-tree guard root` | Enable Root Guard |
| `spanning-tree guard loop` | Enable Loop Guard |
| `spanning-tree backbonefast` | Enable BackboneFast (Legacy) |
| `spanning-tree uplinkfast` | Enable UplinkFast (Legacy) |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show spanning-tree` | Display STP information for all VLANs |
| `show spanning-tree vlan VLAN_ID` | Display STP information for a specific VLAN |
| `show spanning-tree root` | Display the Root Bridge for each VLAN |
| `show spanning-tree summary` | Display STP summary information |
| `show spanning-tree interface INTERFACE` | Display STP information for an interface |
| `show spanning-tree blockedports` | Display blocked interfaces |
| `show spanning-tree detail` | Display detailed STP information |
| `show spanning-tree inconsistentports` | Display inconsistent interfaces |

---

## Common Troubleshooting

| Problem | Verification Command |
|---------|----------------------|
| Incorrect Root Bridge | `show spanning-tree root` |
| Blocked interface | `show spanning-tree blockedports` |
| Wrong port role | `show spanning-tree interface INTERFACE` |
| Frequent topology changes | `show spanning-tree detail` |
| Root Guard triggered | `show spanning-tree inconsistentports` |
| Loop Guard triggered | `show spanning-tree inconsistentports` |
| Verify STP mode | `show spanning-tree summary` |

---

## Navigation

⬆️ [Back to Contents](#spanning-tree-protocol-cheat-sheet)

⬅️ Previous: **[05_STP_Labs.md](05_STP_Labs.md)**

➡️ Next: **[Volume 06 – EtherChannel](../Volume06-EtherChannel/README.md)**
