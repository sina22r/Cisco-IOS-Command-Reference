# EIGRP Cheat Sheet

---

**Volume:** 11 • EIGRP

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `router eigrp AS` | Start Classic Mode EIGRP |
| `router eigrp NAME` | Start Named Mode EIGRP |
| `address-family ipv4 autonomous-system AS` | Configure IPv4 Address Family |
| `address-family ipv6 autonomous-system AS` | Configure IPv6 Address Family |
| `network NETWORK WILDCARD` | Enable EIGRP on matching interfaces |
| `eigrp router-id A.B.C.D` | Configure Router ID |
| `no auto-summary` | Disable automatic summarization |
| `passive-interface INTERFACE` | Disable Hello packets on an interface |
| `no passive-interface INTERFACE` | Enable Hello packets |
| `variance NUMBER` | Enable unequal-cost load balancing |
| `maximum-paths NUMBER` | Configure ECMP |
| `eigrp stub connected summary` | Configure Stub Router |
| `redistribute PROTOCOL` | Redistribute external routes |
| `ip summary-address eigrp AS NETWORK MASK` | Configure route summarization |
| `ip authentication mode eigrp AS md5` | Enable MD5 authentication |
| `ip authentication key-chain eigrp AS KEYCHAIN` | Configure authentication keys |
| `metric weights` | Configure EIGRP K-values |
| `ip bandwidth-percent eigrp AS PERCENT` | Limit EIGRP bandwidth usage |
| `af-interface` | Configure interface settings in Named Mode |
| `topology base` | Configure topology settings |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ip eigrp neighbors` | Display IPv4 neighbors |
| `show ipv6 eigrp neighbors` | Display IPv6 neighbors |
| `show ip eigrp topology` | Display IPv4 topology table |
| `show ipv6 eigrp topology` | Display IPv6 topology table |
| `show ip eigrp interfaces` | Display participating interfaces |
| `show ipv6 eigrp interfaces` | Display IPv6 interfaces |
| `show ip eigrp traffic` | Display packet statistics |
| `show ip protocols` | Display routing protocol information |
| `show ip route eigrp` | Display EIGRP routes |
| `show ipv6 route eigrp` | Display EIGRP IPv6 routes |
| `show running-config \| section router eigrp` | Display Classic Mode configuration |
| `show running-config \| section router eigrp NAME` | Display Named Mode configuration |
| `ping` | Test IPv4 connectivity |
| `ping ipv6` | Test IPv6 connectivity |
| `traceroute` | Verify IPv4 forwarding path |
| `traceroute ipv6` | Verify IPv6 forwarding path |
| `debug eigrp packets` | Debug EIGRP packet exchange |
| `debug eigrp neighbors` | Debug neighbor events |
| `debug ip eigrp` | Debug IPv4 EIGRP operations |

---

## EIGRP Default Values

| Parameter | Default |
|-----------|---------|
| Administrative Distance (Internal) | 90 |
| Administrative Distance (External) | 170 |
| Hello Timer (High-Speed Links) | 5 Seconds |
| Hold Timer (High-Speed Links) | 15 Seconds |
| Hello Timer (Low-Speed Links) | 60 Seconds |
| Hold Timer (Low-Speed Links) | 180 Seconds |
| Maximum Paths | 4 |
| Load Balancing | Equal Cost (Variance = 1) |

---

## K Values

| K Value | Function |
|---------|----------|
| K1 | Bandwidth |
| K2 | Load |
| K3 | Delay |
| K4 | Reliability |
| K5 | Reliability Scaling |

Default:

```text
K1 = 1
K2 = 0
K3 = 1
K4 = 0
K5 = 0
```

---

## Route Codes

| Code | Meaning |
|------|---------|
| `D` | EIGRP Internal |
| `EX` | EIGRP External |
| `C` | Connected |
| `L` | Local |
| `S` | Static |
| `R` | RIP |
| `O` | OSPF |
| `B` | BGP |

---

## Packet Types

| Packet | Purpose |
|---------|---------|
| Hello | Neighbor discovery |
| Update | Advertise routing information |
| Query | Search for alternate paths |
| Reply | Respond to queries |
| ACK | Acknowledge reliable packets |
| SIA Query | Stuck-In-Active detection |
| SIA Reply | Respond to SIA query |

---

## Common Troubleshooting Commands

| Problem | Verification Command |
|---------|----------------------|
| Neighbor not forming | `show ip eigrp neighbors` |
| Missing routes | `show ip route eigrp` |
| Topology issue | `show ip eigrp topology` |
| Interface problem | `show ip eigrp interfaces` |
| Authentication failure | `show ip eigrp neighbors` |
| Stub verification | `show ip protocols` |
| Named Mode verification | `show running-config \| section router eigrp` |
| Packet statistics | `show ip eigrp traffic` |
| IPv6 issue | `show ipv6 eigrp neighbors` |
| Real-time troubleshooting | `debug eigrp packets` |

---

## Navigation

⬆️ [Back to Contents](#eigrp-cheat-sheet)

⬅️ Previous: **[03_EIGRP_Labs.md](03_EIGRP_Labs.md)**

➡️ Next: **[Volume 12 – OSPF](../Volume12-OSPF/README.md)**
