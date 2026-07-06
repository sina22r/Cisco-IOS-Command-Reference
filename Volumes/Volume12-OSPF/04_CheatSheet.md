# OSPF Cheat Sheet

---

**Volume:** 12 • OSPF

**Estimated Reading Time:** 20 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `router ospf PROCESS_ID` | Start OSPF process |
| `router-id A.B.C.D` | Configure Router ID |
| `network NETWORK WILDCARD area AREA` | Enable OSPF using network statements |
| `ip ospf PROCESS_ID area AREA` | Enable interface-based OSPF |
| `ipv6 ospf PROCESS_ID area AREA` | Enable OSPFv3 |
| `passive-interface INTERFACE` | Disable Hello packets |
| `no passive-interface INTERFACE` | Re-enable Hello packets |
| `auto-cost reference-bandwidth VALUE` | Change reference bandwidth |
| `ip ospf cost VALUE` | Configure interface cost |
| `default-information originate` | Advertise default route |
| `area AREA range NETWORK MASK` | ABR summarization |
| `summary-address NETWORK MASK` | ASBR summarization |
| `area AREA stub` | Configure Stub Area |
| `area AREA nssa` | Configure NSSA |
| `area AREA virtual-link ROUTER_ID` | Configure Virtual Link |
| `redistribute PROTOCOL` | Route redistribution |
| `ip ospf authentication` | Enable simple authentication |
| `ip ospf authentication-key PASSWORD` | Configure authentication password |
| `ip ospf message-digest-key ID md5 PASSWORD` | Configure MD5 authentication |
| `maximum-paths NUMBER` | Configure ECMP |
| `log-adjacency-changes` | Log neighbor changes |
| `distance ospf` | Modify administrative distance |
| `neighbor IP_ADDRESS` | Configure NBMA neighbor |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ip ospf` | Display OSPF process |
| `show ipv6 ospf` | Display OSPFv3 process |
| `show ip ospf neighbor` | Display neighbors |
| `show ipv6 ospf neighbor` | Display OSPFv3 neighbors |
| `show ip ospf interface` | Display interface information |
| `show ipv6 ospf interface` | Display OSPFv3 interfaces |
| `show ip ospf database` | Display LSDB |
| `show ipv6 ospf database` | Display OSPFv3 LSDB |
| `show ip route ospf` | Display OSPF routes |
| `show ipv6 route ospf` | Display OSPFv3 routes |
| `show ip protocols` | Display protocol configuration |
| `show running-config \| section router ospf` | Display OSPF configuration |
| `ping` | Test IPv4 connectivity |
| `ping ipv6` | Test IPv6 connectivity |
| `traceroute` | Trace IPv4 path |
| `traceroute ipv6` | Trace IPv6 path |
| `debug ip ospf adj` | Debug adjacency formation |
| `debug ip ospf hello` | Debug Hello packets |
| `debug ip ospf events` | Debug protocol events |
| `debug ip ospf spf` | Debug SPF calculations |

---

## OSPF Route Codes

| Code | Meaning |
|------|---------|
| `O` | Intra-Area Route |
| `O IA` | Inter-Area Route |
| `O E1` | External Type 1 |
| `O E2` | External Type 2 |
| `O N1` | NSSA External Type 1 |
| `O N2` | NSSA External Type 2 |

---

## OSPF Network Types

| Network Type | DR / BDR |
|--------------|----------|
| Broadcast | Yes |
| Non-Broadcast (NBMA) | Yes |
| Point-to-Point | No |
| Point-to-Multipoint | No |
| Point-to-Multipoint Non-Broadcast | No |

---

## LSA Types

| Type | Description |
|------|-------------|
| 1 | Router LSA |
| 2 | Network LSA |
| 3 | Summary LSA |
| 4 | ASBR Summary LSA |
| 5 | AS External LSA |
| 7 | NSSA External LSA |

---

## Default Values

| Parameter | Default |
|-----------|---------|
| Administrative Distance | 110 |
| Reference Bandwidth | 100 Mbps |
| Hello Timer (Broadcast/P2P) | 10 Seconds |
| Dead Timer (Broadcast/P2P) | 40 Seconds |
| Hello Timer (NBMA) | 30 Seconds |
| Dead Timer (NBMA) | 120 Seconds |

---

## Common Troubleshooting Commands

| Problem | Command |
|---------|---------|
| Neighbor issue | `show ip ospf neighbor` |
| Interface issue | `show ip ospf interface` |
| LSDB issue | `show ip ospf database` |
| Missing routes | `show ip route ospf` |
| Authentication issue | `show ip ospf interface` |
| SPF issue | `debug ip ospf spf` |
| Adjacency issue | `debug ip ospf adj` |
| Event troubleshooting | `debug ip ospf events` |

---

## Navigation

⬆️ [Back to Contents](#ospf-cheat-sheet)

⬅️ Previous: **[03_OSPF_Labs.md](03_OSPF_Labs.md)**

➡️ Next: **[Volume 13 – BGP](../Volume13-BGP/README.md)**
