# RIP Cheat Sheet

---

**Volume:** 10 • RIP

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `router rip` | Start the RIP routing process |
| `version 2` | Enable RIP Version 2 |
| `network NETWORK` | Advertise a network |
| `no auto-summary` | Disable automatic summarization |
| `auto-summary` | Enable automatic summarization |
| `passive-interface INTERFACE` | Stop sending RIP updates on an interface |
| `no passive-interface INTERFACE` | Re-enable RIP updates |
| `neighbor IP_ADDRESS` | Configure a RIP neighbor (unicast updates) |
| `default-information originate` | Advertise a default route |
| `default-metric HOP_COUNT` | Configure the default metric for redistributed routes |
| `timers basic UPDATE INVALID HOLDDOWN FLUSH` | Configure RIP timers |
| `offset-list ACL {in \| out} OFFSET [INTERFACE]` | Modify RIP hop-count metrics |
| `distance ADMINISTRATIVE_DISTANCE` | Change the administrative distance |
| `maximum-paths NUMBER` | Configure ECMP load balancing |
| `redistribute static` | Redistribute static routes into RIP |
| `ipv6 router rip PROCESS_NAME` | Create an RIPng process |
| `ipv6 rip PROCESS_NAME enable` | Enable RIPng on an interface |
| `ip rip send version {1 \| 2 \| 1 2}` | Configure transmitted RIP version |
| `ip rip receive version {1 \| 2 \| 1 2}` | Configure accepted RIP versions |
| `ip rip authentication mode {text \| md5}` | Configure RIP authentication mode |
| `ip rip authentication key-chain KEY_CHAIN` | Configure RIP authentication keys |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ip protocols` | Display RIP protocol information |
| `show ip route` | Display the routing table |
| `show ip route rip` | Display RIP-learned routes |
| `show ip rip database` | Display the RIP database |
| `show running-config \| section router rip` | Display RIP configuration |
| `show ipv6 protocols` | Display RIPng information |
| `show ipv6 route` | Display the IPv6 routing table |
| `show ipv6 route rip` | Display RIPng routes |
| `show ipv6 rip database` | Display the RIPng database |
| `ping` | Test IPv4 connectivity |
| `ping ipv6` | Test IPv6 connectivity |
| `traceroute` | Trace an IPv4 path |
| `traceroute ipv6` | Trace an IPv6 path |
| `debug ip rip` | Display RIP updates in real time |
| `debug ipv6 rip` | Display RIPng updates in real time |

---

## RIP Default Timers

| Timer | Default Value |
|-------|--------------:|
| Update | 30 seconds |
| Invalid | 180 seconds |
| Holddown | 180 seconds |
| Flush | 240 seconds |

---

## RIP Route Codes

| Code | Meaning |
|------|---------|
| `R` | RIP |
| `C` | Connected |
| `L` | Local |
| `S` | Static |
| `D` | EIGRP |
| `O` | OSPF |
| `B` | BGP |

---

## RIP Characteristics

| Feature | Value |
|---------|-------|
| Routing Protocol Type | Distance Vector |
| Metric | Hop Count |
| Maximum Hop Count | 15 |
| Hop Count 16 | Unreachable |
| Administrative Distance | 120 |
| Update Method | Periodic |
| Default Update Interval | 30 Seconds |
| Multicast Address | 224.0.0.9 (RIPv2) |
| Transport Protocol | UDP |
| UDP Port | 520 |
| IPv6 Version | RIPng |
| RIPng UDP Port | 521 |
| RIPng Multicast Address | FF02::9 |

---

## Frequently Used Commands

| Task | Command |
|------|---------|
| Enable RIP | `router rip` |
| Enable RIP Version 2 | `version 2` |
| Advertise a network | `network` |
| Disable summarization | `no auto-summary` |
| Configure passive interfaces | `passive-interface` |
| Verify protocol status | `show ip protocols` |
| Verify learned routes | `show ip route rip` |
| Display RIP database | `show ip rip database` |
| Verify RIPng | `show ipv6 route rip` |
| Test connectivity | `ping`, `ping ipv6` |

---

## Common Troubleshooting Commands

| Problem | Verification Command |
|---------|----------------------|
| RIP not running | `show ip protocols` |
| Networks not advertised | `show running-config \| section router rip` |
| Missing RIP routes | `show ip route rip` |
| RIP database issue | `show ip rip database` |
| Passive interface problem | `show ip protocols` |
| IPv6 RIP issue | `show ipv6 protocols` |
| RIPng route missing | `show ipv6 route rip` |
| Connectivity failure | `ping`, `traceroute` |
| Routing updates | `debug ip rip` |
| RIPng updates | `debug ipv6 rip` |

---

## Navigation

⬆️ [Back to Contents](#rip-cheat-sheet)

⬅️ Previous: **[03_RIP_Labs.md](03_RIP_Labs.md)**

➡️ Next: **[Volume 11 – EIGRP](../Volume11-EIGRP/README.md)**
