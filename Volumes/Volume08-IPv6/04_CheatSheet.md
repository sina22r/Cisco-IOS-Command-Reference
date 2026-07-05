# IPv6 Cheat Sheet

---

**Volume:** 08 • IPv6

**Estimated Reading Time:** 20 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `ipv6 unicast-routing` | Enable IPv6 routing globally |
| `ipv6 enable` | Enable IPv6 processing on an interface |
| `ipv6 address IPV6/PREFIX` | Configure a global IPv6 address |
| `ipv6 address PREFIX eui-64` | Generate an interface identifier using EUI-64 |
| `ipv6 address IPV6 link-local` | Configure a manual link-local address |
| `ipv6 address autoconfig` | Configure an address using SLAAC |
| `no ipv6 address IPV6/PREFIX` | Remove a configured IPv6 address |
| `ipv6 mtu BYTES` | Configure the IPv6 MTU |
| `ipv6 nd reachable-time MILLISECONDS` | Configure Neighbor Discovery reachable time |
| `ipv6 nd ra interval SECONDS` | Configure the Router Advertisement interval |
| `ipv6 nd managed-config-flag` | Set the Managed (M) flag for DHCPv6 |
| `ipv6 nd other-config-flag` | Set the Other Configuration (O) flag |
| `ipv6 nd prefix PREFIX/LENGTH` | Advertise an IPv6 prefix |
| `ipv6 nd suppress-ra` | Disable Router Advertisements |
| `ipv6 traffic-filter ACL_NAME {in \| out}` | Apply an IPv6 ACL |
| `ipv6 ospf PROCESS_ID area AREA_ID` | Enable OSPFv3 on an interface |
| `ipv6 rip PROCESS_NAME enable` | Enable RIPng on an interface |
| `ipv6 eigrp AS_NUMBER` | Enable EIGRP for IPv6 |
| `ipv6 router isis TAG` | Enable IPv6 IS-IS |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ipv6 interface brief` | Display a summary of IPv6 interfaces |
| `show ipv6 interface` | Display detailed IPv6 interface information |
| `show ipv6 neighbors` | Display the Neighbor Cache |
| `show ipv6 route` | Display the IPv6 routing table |
| `show ipv6 protocols` | Display active IPv6 routing protocols |
| `show ipv6 cef` | Display the IPv6 CEF table |
| `show ipv6 traffic` | Display IPv6 traffic statistics |
| `show ipv6 access-list` | Display IPv6 ACLs |
| `show running-config interface INTERFACE` | Display interface configuration |
| `ping ipv6 ADDRESS` | Test IPv6 connectivity |
| `traceroute ipv6 ADDRESS` | Trace the IPv6 path to a destination |

---

## Neighbor Discovery Commands

| Feature | Command |
|---------|---------|
| Reachable Time | `ipv6 nd reachable-time` |
| Router Advertisement Interval | `ipv6 nd ra interval` |
| Managed Flag | `ipv6 nd managed-config-flag` |
| Other Configuration Flag | `ipv6 nd other-config-flag` |
| Prefix Advertisement | `ipv6 nd prefix` |
| Suppress Router Advertisements | `ipv6 nd suppress-ra` |

---

## Frequently Used Commands

| Task | Command |
|------|---------|
| Enable IPv6 routing | `ipv6 unicast-routing` |
| Configure a global address | `ipv6 address` |
| Configure a link-local address | `ipv6 address ... link-local` |
| Enable SLAAC | `ipv6 address autoconfig` |
| Display interface status | `show ipv6 interface brief` |
| Display neighbors | `show ipv6 neighbors` |
| Display routing table | `show ipv6 route` |
| Test connectivity | `ping ipv6` |
| Trace a route | `traceroute ipv6` |

---

## Common Troubleshooting Commands

| Problem | Verification Command |
|---------|----------------------|
| Interface is down | `show ipv6 interface brief` |
| Incorrect IPv6 address | `show ipv6 interface` |
| Neighbor not reachable | `show ipv6 neighbors` |
| Missing IPv6 route | `show ipv6 route` |
| Router Advertisements not received | `show ipv6 interface` |
| ACL blocking traffic | `show ipv6 access-list` |
| Forwarding issue | `show ipv6 cef` |
| End-to-end connectivity failure | `ping ipv6`, `traceroute ipv6` |

---

## Navigation

⬆️ [Back to Contents](#ipv6-cheat-sheet)

⬅️ Previous: **[03_IPv6_Labs.md](03_IPv6_Labs.md)**

➡️ Next: **[Volume 09 – Static Routing](../Volume09-Static-Routing/README.md)**
